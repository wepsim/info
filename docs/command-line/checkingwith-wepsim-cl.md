
# Checking with WepSIM

* [Run and save the final state](#run-and-save-the-final-state)
* [Run & check end state (example when o.k.)](#run--check-end-state-example-when-ok)
* [Run & check end state (example when k.o.)](#run--check-end-state-example-when-ko)


### Run and save the final state

+ From the command line it is possible to 'run' the 's1e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode, and print the final state:
  ```bash
  ./wepsim.sh -a run -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e5.asm > cl-s1e5.txt
  cat cl-s1e5.txt
  ```
  Output:
  <html>
  <pre>
  register R9 = 0x1; register R10 = 0x2; register R29 = 0x100000; memory 0x8000 = 0x9200001; memory 0x8004 = 0x9400002; memory 0x8008 = 0x412a0004; memory 0x800c = 0x30000004; memory 0x8010 = 0x52a0000; memory 0x8014 = 0x9200001; memory 0x8018 = 0x9400002; memory 0x801c = 0x3d2a0004; memory 0x8020 = 0x52a0000; memory 0x8024 = 0x9200001; memory 0x8028 = 0x9400002; memory 0x802c = 0x3d2a0004; memory 0x8030 = 0x30000000; memory 0x8034 = 0x57e00000; 
  </pre>
  </html>


### Run & check end state (example when o.k.)

+ You can check if the state at the end of the execution is the same as the one stored on file 'cl-s1e1.txt'. You can 'run' the 's1e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode (**and if it matches the expected state, then the output is going to be**):
  ```bash
  ./wepsim.sh -a check -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e1.asm \
              -r ./repo/checklist/mips/cl-s1e1.txt
  ```
  Output:
  <html>
  <pre>
  OK: Execution: no error reported
  </pre>
  </html>


### Run & check end state (example when k.o.)

+ You can check if the state at the end of the execution is the same as the one stored on file 'cl-s1e1.txt'. You can 'run' the 's1e1.asm' assembly for the 'ep' architecture with the 'ep_base.mc' microcode (**and if it fails to match the expected state then the output is going to be**):
  ```bash
  ./wepsim.sh -a check -m ep \
              -f ./repo/microcode/mips/ep_base.mc \
              -s ./repo/assembly/mips/s1e1.asm \
              -r ./repo/checklist/mips/cl-s1e2.txt
  ```
  Output:
  <html>
  <pre>
  ERROR: Execution: different results: cpu[R1]='0' (expected '0xf'), cpu[R2]='0x2' (expected '0xf'), cpu[R3]='0' (expected '0x1'), cpu[R29]='0x100000' (expected '0xfffff'), cpu[PC]='0x8078' (expected '0x8018'), memory[0x1000]='0' (expected '0xa07ff0f'), memory[0x1004]='0' (expected '0x10061'), memory[0x1008]='0' (expected '0x7ffff'), memory[0x100c]='0' (expected '0x61000a'), memory[0x1010]='0' (expected '0xf'), memory[0x1014]='0' (expected '0xffffffff'), memory[0x1018]='0' (expected '0x7'), memory[0x101c]='0' (expected '0x12345678'), memory[0x1020]='0' (expected '0x61'), memory[0x1024]='0' (expected '0x6c6c6568'), memory[0x1028]='0' (expected '0x726f776f'), memory[0x102c]='0' (expected '0x646c'), memory[0x8000]='0x8400002' (expected '0x20201000'), memory[0x8004]='0x8600001' (expected '0x10601010'), memory[0x8008]='0xa21809' (expected '0x820000f'), memory[0x800c]='0x8400002' (expected '0x24201000'), memory[0x8010]='0x8600001' (expected '0x840000f'), memory[0x8014]='0xa2180a' (expected '0x14401010'), 
  </pre>
  </html>


