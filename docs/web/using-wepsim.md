
# Getting Started

* [Executing a WepSIM example](#1-steps-to-execute-a-wepsim-example)
* [Changing the default configuration](#2-steps-to-change-the-wepsim-configuration)
* [Workflow on building your own experiment](#3-typical-workflow-to-modify-an-existing-example-or-build-your-own-experiment)
* [How to check what changes in the execution](#4-typical-steps-to-use-the-state-management-in-wepsim)


## 1. Steps to execute a WepSIM example

1. First, we need to load WepSIM in your favorite web browser. Then click on the Examples button to open the Examples dialog:
   ![screen:example1](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/simulator021.jpg)
2. In the Examples dialog, please click on the colored 'title' of the example and WepSIM will load and compile the associated microcode and assembly code:
   ![screen:example2](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/simulator022.jpg)
3. In the simulator workspace you can execute step by step and analyze the state of the components. It is possible to work both, at assembly level or at microcode level:
   ![screen:simulation1](https://raw.githubusercontent.com/wepsim/wepsim/master/images/welcome/simulation_xinstruction.gif)

## 2. Steps to change the WepSIM configuration

+ From the general toolbar, the configuration button allows users to personalize several options:
  ![screen:configuration](https://raw.githubusercontent.com/wepsim/wepsim/master/images/welcome/config_usage.gif)
+ From the general toolbar, please use the left-upper slider to change the CPU/CU size:
  ![screen:configuration](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/simulator013.jpg)

## 3. Typical workflow to modify an existing example or build your own experiment

1. First, we need to load WepSIM in your web browser. Then you should go to the microcode editor workspace:
   ![screen:firmware1](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/firmware001.jpg)
2. You can load an existing microcode or edit a new one. You have to microcompile the microcode to load the binary into the CPU's control memory:
   ![screen:firmware2](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/firmware002.jpg)
3. Next, you could go to the assembly editor workspace. In the editor workspace you can load an existing assembly code or edit a new one:
   ![screen:firmware3](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/assembly002b.jpg)
4. The instructions set defined in the previous microcode is used to create your assembly code. You have to compile the assembly code to load the binary into the main memory:
   ![screen:assembly1](https://raw.githubusercontent.com/wepsim/wepsim/master/images/simulator/assembly003.jpg)
5. Finally, go back to the simulator workspace, and you can execute step by step and analyze the state of the components.
   It is possible to work at assembly level or at microcode level:
   ![screen:simulation cpu](https://raw.githubusercontent.com/wepsim/wepsim/master/images/welcome/simulation_xinstruction.gif)

## 4. Typical steps to use the "State Management" in WepSIM

+ The value of every visible hardware element is the state in a clock cycle. WepSIM has also a 'state management' dialog where users can see the current state, and check the differences between the two states.
+ From the execution toolbar, please click over the 'state' button to show the state manager dialog:
  ![screen:configuration](https://raw.githubusercontent.com/wepsim/wepsim/master/images/welcome/states_usage.gif)


