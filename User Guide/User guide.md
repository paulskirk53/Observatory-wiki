When entering the observatory to initialise the equipment for an observing session, the following text descibes the workflow.

**Power**
Connect the Main 12 volt battery., by closing the switch connected to the positive 12V battery lead. The circuit is protected by a 5 amp fuse which you can see near the switch. Closing this switch provides power to the following:
NUC 
Sitech Telescope controller 
USB Hub
Microtouch Focuser
The monitor screen used by the NUC
Note all the above have their own on / off switch too !
The MOSFET switch box which provides power for the Cameras & Rotator see later for how to activate this to provide power for the camera & Rotator.

The USB hub has a push switch on the front panel. A good visual indication that the USB  hub is powered on is that the Master Radio Arduino box LCD screen ligts up. This is right in front of you if you sit with your back to the observatory door.

**Shutter Power**
At the base of the shutter, there's the motor box which opens and closes the shutter. This has its own Arduino Mega2560 and you need to insert its USB cable into the epever solar controller in order to provide power to the Arduino. The blue plastic control box has a clear lid, so you can see a dim red glow of the Arduino LED when the power is connected. It's good (and absolutely vital) at this point to release the shutter clamp lock, just above and to the left of the control box. Otherwise if you use the hand controller or software to open the shutter, it will rip the chain and pulleys to bits :(

**Dome Power**
On the floor under the computer screen, is a 12V battery and this needs to be powered on so that the Dome Drive will turn the dome in synchrony with the telescope movement.

That's all for power - a quick summary:
1. Turn on main Battery
2. Turn on Shutter arduino power at epever controller
3. Release the shutter clamp lock
4. Power on the Dome drive (battery on floor under computer screen)
5. Make sure all the devices which have their own on/ off switches are turned on - NUC, USB hub, focuser, computer screen.
6. Power for the guide camera, main imaging camera and the camera rotator is described below.

**Power for the Cameras and rotator**

The power on / off is controlled in software, so that the devices can be powered off until such times as they are r


[[Port Forwarding]]





return to [[Observatory Home]] home page
