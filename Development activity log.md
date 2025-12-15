Updating the current control box code to include get and set home/ park azimuth
the azimuth seems to be remembered after connecting e.g. was 266 after setting it with the encoder wheel, then disconnect and reconnect - still 266 - needs investigation






**the control box - move using degrees project** 
- for summer 2026 trial, test and implementation.

one thing we need for the code in this branch is the number of motor steps for one degree of dome movement. Now that the shaft encoder is attached to the motor shaft, the ticks per dome revolution can be used to work out the number of encoder (& thus stepper shaft) rotations per dome rev.

The ticks per dome rev in the master branch is 20700 and the number of shaft encoder ticks per rev =600, so 20700/ 600 =34.5 the number of shaft rotations per dome rev. Now all we need is to look at the DM860I controller to see the steps per rotation and we're done.

Testing can be done on the control box sim at home.