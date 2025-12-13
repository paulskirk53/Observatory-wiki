**the control box - move using degrees project** 
- for summer 2026 trial, test and implementation.

one thing we need for the code in this branch is the number of motor steps for one degree of dome movement. Now that the shaft encoder is attached to the motor shaft, the ticks per dome revolution can be used to work out the number of encoder (& thus stepper shaft) rotations per dome rev.

The ticks per dome rev in the master branch is 20700 and the number of shaft encoder ticks per rev =600 so 20700/ 600 - number of shaft rotations per dome rev