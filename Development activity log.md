[[Observatory Home]]
**Updating the current control box** code to include get and set home/ park azimuth
the azimuth seems to be remembered after connecting e.g. was 266 after setting it with the encoder wheel, then disconnect and reconnect - still 266 - needs investigation error in code 'kkepaz' now fixed







**the control box - move using degrees project** 
- for summer 2026 trial, test and implementation.

one thing we need for the code in this branch is the number of motor steps for one degree of dome movement. Now that the shaft encoder is attached to the motor shaft, the ticks per dome revolution can be used to work out the number of encoder (& thus stepper shaft) rotations per dome rev.

The encoder ticks per dome rev in the master branch is 20700 and the number of shaft encoder ticks per rev =600, so 20700/ 600 =34.5 the number of motor (and now encoder as its attached) shaft rotations per dome rev. Now all we need is to look at the DM860I controller to see the steps per rotation and we're done. - steps per motor shaft rotation is set as 800 on the DM860I

So, one full dome rotation = 34.5 motor shaft rotations per dome rotation, so this is 34.5 x 800 motor steps per dome revolution = 27600 
Motor steps per degree is therefore 27600/ 360 = 76.666666 see the code file.

Testing can be done on the control box sim at home.
SA999# and SL work fine so far. See github
