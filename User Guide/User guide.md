When entering the observatory to initialise the equipment for an observing session, the following text describes the workflow. You must be at the observatory to do all the following things, it takes about 10-15 minutes once you've done it a few times. Once the setup is done, all functions can be controlled remotely - see [[Remote session management]].

**Power**
Connect the Main 12 volt battery., by closing the switch connected to the positive 12V battery lead. The circuit is protected by a 5 amp fuse which you can see near the switch. Closing this switch provides power to the following:
NUC 
Sitech Telescope controller (rocker switch on side of controller)
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

Be careful if the battery terminals are removed from the batteries - ensure the polarity is observed when replacing the terminals - they are colour coded red 12Volt positive, black 0 Volt negative.

That's all for power - a quick summary:
1. Turn on main Battery
2. Turn on Shutter arduino power at epever controller
3. Release the shutter clamp lock so that the shutter can open / close.
4. Power on the Dome drive (battery on floor under computer screen)
5. Make sure all the devices which have their own on/ off switches are turned on - NUC, USB hub, focuser, computer screen.
6. Power for the guide camera, main imaging camera and the camera rotator is described below.

**Computer connections**
The NUC computer has a password which is 3633. Connect it as follows power lead, HDMI to monitor, USB cable to USB hub, USB cable to four port (non powered hub). USB keyboard, mouse. Power up and enter the password. It's windows 11

**Power for the Cameras and rotator**
The power on / off is controlled in software, so that the devices can be powered off until such times as they are required to take images, which saves battery power. 
In order to turn on, the program called '[[Remote session management]]' must be run on the NUC in the observatory. This is a windows program I wrote which allows remote monitoring and control of all the observatory functions from home - Pitton Mill Cottage or anywhere that has an internet connection and [[Port Forwarding]] set up on the house internet router.

Once the monitoring program is running, you'll see the following:

![[Monitoring.png]]

First click the orange ellipse shaped button to connect to the microcontroller. It should say connected on 'port number' under the button. If it doesn't connect, see [[Troubleshooting]].
Just below half way down, you can see 'camera and rotator power' click the toggle button to make the 'turn on' button available. Now click 'turn on'  you will hear the immediate sound of the camera rotator executing its homing procedure and also the fan start up on the camera. If you don't hear these sounds see [[Troubleshooting]].

There is nothing else to do with the monitor program at present, note that it's a handy visual for the dome azimuth, which we're interested in because we need to manually align and initialise the telescope. 

[[Telescope Initialisation]]
With the telescope pointing due west and horizontal, align the shutter opening so that the telescope can 'see' out of the Dome aperture. Now, without moving the Dome manually turn the encoder wheel so that it indicates Azimuth 245 degrees. You can see the azimuth value in the monitoring program. Now you need to initialise the Sitech Controller. See here  [[Telescope Initialisation]]




return to [[Observatory Home]] home page
