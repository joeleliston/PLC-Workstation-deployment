# PLC Workstation deployment
***
### Video
https://youtu.be/9WlUBiXszV0
***

### Introduction
The goal of this project was to deploy a workstation using a Programmable Logic Controller a vacuum and a conveyor belt to move some cubes. This will explain our different routines making the program work. The logic was developed, for the manual operation and the automatic operation.

### Routines
1. **Main Routine**: It is composed of three (3) routines which are : the production routine, the reset routine and the flashers routine. The main routine starts with a Start Push button that is the green one on the workstation. When it is pushed, all the inputs are at 0 and at the Home position. The program starts and the production routine is energized as well as the flashers routine. Anytime the stop push button (red button) is energized while the main routine is operating, everything stops. The Reset button (blue button)puts all the inputs and outputs back at their home position.
2. **Production Routine**: The production routine is where most of the operations take effect in our workstation. Every step is one at a time and two steps can’t operate at the same time.
The steps are as follows : A box is ejected from the tube. The vacuum lowers its head and then turns the air on to pick up the cube. Once the cube is secured, The vacuum head is lifted up and rotates clockwise. It then heads to the conveyor. From there, the cube is placed on the conveyor once the box is dropped off , the servo motor runs for a few seconds. The cubes head in the direction of the proximity sensor. While this is happening, the vacuum head goes back to the magazine to pick up another cube using the same operation. We put a timer on the conveyor belt so the first cube would be waiting for the second cube before triggering the proximity sensor. Once two of the cubes have passedthrough the proximity sensor, the operation stops, the vacuum head goes back to the magazine and resets. This is only for the manual mode. Then, we can put it in automatic mode. In this case, the operation will be in a loop and there is nothing that we can do except pressing the physical stop button or reset to stop everything. The start push button does not have much importance in the case of the automatic mode.
3. **Reset Routine**:The reset routine is the program that will stop everything. When the reset button (blue push button) is energized , the steps are as follows : 
The air in the vacuum is turned off, the box ejector is then retracted, the vacuum head is retracted then rotates counter clockwise. It can then head back to the magazine. The bar stopping the cube after the bar code goes back to its home position, as well as the vacuum head and all that while the conveyor is stopping.
4. **Flasher Routine**:The flashers routine is the simplest of our routine. It is used by the stack light in our station. While the workstation is operating, the green light stays on. When it is stopped, the red light comes on and the green light comes off. the Amber light is flashing while the system is resetting.
