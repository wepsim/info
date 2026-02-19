
# Getting Started

* [Run and print the final state](#run-and-print-the-final-state)
* [Run step by step](#run-step-by-step)
* [Run microstep by microstep](#run-microstep-by-microstep)
* [Run microstep by microstep with verbalized output](#run-microstep-by-microstep-with-verbalized-output)


### Run and print the final state

+ From the command line it is possible to 'run' the 's1e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode, and print the final state:
  ```bash
  ./wepsim.sh -a run -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e5.asm
  ```
  Output:
  <html>
  <pre>
  register R9 = 0x1; register R10 = 0x2; register R29 = 0x100000; memory 0x8000 = 0x9200001; memory 0x8004 = 0x9400002; memory 0x8008 = 0x412a0004; memory 0x800c = 0x30000004; memory 0x8010 = 0x52a0000; memory 0x8014 = 0x9200001; memory 0x8018 = 0x9400002; memory 0x801c = 0x3d2a0004; memory 0x8020 = 0x52a0000; memory 0x8024 = 0x9200001; memory 0x8028 = 0x9400002; memory 0x802c = 0x3d2a0004; memory 0x8030 = 0x30000000; memory 0x8034 = 0x57e00000; 
  </pre>
  </html>


### Run step by step

+ It is also possible to 'run' 'step by step' the 's1_e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode, and print for each assembly instruction the state elements that modify its value:
  ```bash
  ./wepsim.sh -a stepbystep -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e1.asm
  ```
  Output:
  <html>
  <pre>
  pc,				instruction,		changes_from_zero_or_current_value
  pc = 0x8000,	li $2 2,			register R2 = 0x2; register R29 = 0x100000; register PC = 0x8004
  pc = 0x8004,	li $3 1,			register R3 = 0x1; register PC = 0x8008
  pc = 0x8008,	add $5 $2 $3,		register R5 = 0x3; register PC = 0x800c
  pc = 0x800c,	li $2 2,			register PC = 0x8010
  pc = 0x8010,	li $3 1,			register PC = 0x8014
  ...
  </pre>
  </html>


### Run microstep by microstep

+ And to 'run' 'microstep by microstep' the 's1e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode, and print for each microinstruction the state elements that modify its value:
  ```bash
  ./wepsim.sh -a microstepbymicrostep -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e1.asm
  ```
  Output:
  <html>
  <pre>
  micropc,			microcode,													changes_from_zero_or_current_value
  micropc = 0x0,		T2 C0,
  micropc = 0x1,		TA R BW=11 M1 C1,
  micropc = 0x2,		M2 C2 T1 C3,												register PC = 0x8004
  micropc = 0x3,		A0 B=0 C=0,
  micropc = 0xd3,		SE OFFSET=0 SIZE=10000 T3 LC MR=0 SELC=10101 A0 B C=0,		register R2 = 0x2; register R29 = 0x100000
  micropc = 0x0,		T2 C0,
  micropc = 0x1,		TA R BW=11 M1 C1,
  micropc = 0x2,		M2 C2 T1 C3,												register PC = 0x8008
  micropc = 0x3,		A0 B=0 C=0,
  micropc = 0xd3,		SE OFFSET=0 SIZE=10000 T3 LC MR=0 SELC=10101 A0 B C=0,		register R3 = 0x1
  ...
  </pre>
  </html>


### Run microstep by microstep with verbalized output

+ And finally, it is possible to execute microstep by microstep but with a more verbose description:
  ```bash
  ./wepsim.sh -a microstepverbalized -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e1.asm
  ```
  Output:
  <html>
  <pre>
  Micropc at 0x0.	Activated signals are: T2 C0. Associated actions are: Copy from Program Counter Register to Internal Bus value 0x8000. Load from Internal Bus to Memory Address Register value 0x8000.
  Micropc at 0x1.	Activated signals are: TA R BW M1 C1. Associated actions are: Copy from Memory Address Register to Address Bus value 0x8000. Memory output = 0x8400002 (Read a word from 0x8000). Select the full Word. Copy from from Memory to Input of Memory Data Register value 0x8400002. Load from Input of Memory Data Register to Memory Data Register value 0x8400002.
  Micropc at 0x2.	Activated signals are: M2 C2 T1 C3. Associated actions are: Copy to Input of Program Counter Program Counter Register plus four with result 0x8004. Load from Input of Program Counter to Program Counter Register value 0x8004. Copy from Memory Data Register to Internal Bus value 0x8400002. Load from Internal Bus to Instruction Register value 0x8400002. Decode instruction.
  Micropc at 0x3.	Activated signals are: A0 B C. Associated actions are: Copy from Input ROM to Input microaddress value 0x67. Copy from Output of MUX C to A1 value 0x0. Copy from Wired Zero to Output of MUX C value 0x0.
  Micropc at 0x67.	Activated signals are: SE OFFSET SIZE T3 LC MR SELC A0 B C. Associated actions are:  Copy from Instruction Register to Input of T3 Tristate value 0x2 (copied 16 bits from bit 0).  Copy from Instruction Register to Input of T3 Tristate value 0x2 (copied 16 bits from bit 0).  Copy from Instruction Register to Input of T3 Tristate value 0x2 (copied 16 bits from bit 0). Copy from Input of T3 Tristate to Internal Bus value 0x2. Copy to Register 2 the value 0x2. Copy from IR[SelA], from IR[SelB], and from IR[SelB] into RA, RB, and RC. Copy from Input Fetch to Input microaddress value 0x0. Set A1 with value 0x1 (Logical NOT of MUXC_MUXB). Copy from Wired Zero to Output of MUX C value 0x0.
  Micropc at 0x0.	Activated signals are: T2 C0. Associated actions are: Copy from Program Counter Register to Internal Bus value 0x8004. Load from Internal Bus to Memory Address Register value 0x8004.
  Micropc at 0x1.	Activated signals are: TA R BW M1 C1. Associated actions are: Copy from Memory Address Register to Address Bus value 0x8004. Memory output = 0x8600001 (Read a word from 0x8004). Select the full Word. Copy from from Memory to Input of Memory Data Register value 0x8600001. Load from Input of Memory Data Register to Memory Data Register value 0x8600001.
  ...
  </pre>
  </html>


