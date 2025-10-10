[[Observatory Home]]

When entering the observatory to initialise the equipment for an observing session, the following text describes the workflow. You must be at the observatory to do all the following things, it takes about 10-15 minutes once you've done it a few times. Once the setup is done, all functions can be controlled remotely - see [[Remote session management]].

**Power**
During 2025, I started to use the victron phoenix 12 | 500 inverter to power the computer, usb hub and sxH814C camera. The stable power seemed to help the camera and the connection problems went away on the new lenovo m720Q computer. The monitor is also powered from the inverter whilst in the observatory. Turn on the inverter at the back panel - do not use eco mode.
**Other equipment**
Connect the Main 12 volt battery., by closing the switch connected to the positive 12V battery lead. The circuit is protected by a 5 amp fuse which you can see near the switch. Closing this switch provides power to the following:
 
- Sitech Telescope controller (rocker switch on side of controller)
- Microtouch Focuser
- The MOSFET switch box which provides power for the Cameras & Rotator see later for how to activate this to provide power for the camera & Rotator.
Note all the above have their own on / off switch too !
The USB hub has  push switches for all connections. A good visual indication that the USB  hub is powered on is that the Master Radio Arduino box LCD screen lights up. This is right in front of you if you sit with your back to the observatory door.

**Shutter Power**
At the base of the shutter, there's the motor box which opens and closes the shutter. This has its own Arduino Mega2560 and you need to insert its USB cable into the epever solar controller in order to provide power to the Arduino. The blue plastic control box has a clear lid, so you can see a dim red glow of the Arduino LED when the power is connected. It's good (and absolutely vital) at this point to release the shutter clamp lock, just above and to the left of the control box. Otherwise if you use the hand controller or software to open the shutter, it will rip the chain and pulleys to bits :(

**Dome Power**
On the floor under the computer screen, is a 12V battery and this needs to be powered on so that the Dome Drive will turn the dome in synchrony with the telescope movement.

Be careful if the battery terminals are removed from the batteries - ensure the polarity is observed when replacing the terminals - they are colour coded red 12Volt positive, black 0 Volt negative.

That's all for power - a quick summary:
1. Turn on main Battery switch
2. Turn on inverter
3. Turn on Shutter arduino power at epever controller
4. Release the shutter clamp lock so that the shutter can open / close.
5. Power on the Dome drive (battery on floor under computer screen)
6. Make sure all the devices which have their own on/ off switches are turned on - NUC, USB hub, focuser, computer screen.
7. Power for the guide camera, main imaging camera and the camera rotator is described below.

**Computer connections**
The computer has a password which is 3633. Connect it as follows power lead, HDMI to monitor, USB cable to USB hub. USB keyboard, mouse. Power up and enter the password. It's windows 11

**Power for the rotator and focuser**
The power on / off is controlled in software, so that the devices can be powered off until such times as they are required to take images, which saves battery power. 
In order to turn on, the program called 'Monitor' ( see [[Remote session management]] ) must be run on the computer in the observatory. This is a windows program I wrote which allows remote monitoring of some key aspects of the observatory functions from home, in conjunction with the remote session management software called Anydesk - see below. You can run the observatory from Pitton Mill Cottage or any computer that has an internet connection and runs Anydesk.

Once the monitoring program is running, you'll see the following:

![[Monitoring.png]]

First click the orange ellipse shaped button to connect to the microcontroller. It should say connected on 'port number' under the button. If it doesn't connect, see [[Troubleshooting]].
Just below half way down, you can see 'camera and rotator power' click the toggle button to make the 'turn on' button available. Now click 'turn on'  you will hear the immediate sound of the camera rotator executing its homing procedure  If you don't hear these sounds see [[Troubleshooting]].

There is nothing else to do with the monitor program at present, note that it's a handy visual for the dome azimuth, which we're interested in because we need to manually align and initialise the telescope. 

## Anydesk - remote operation
In conjunction with the Monitor program mentioned above, in order to remotely manage the observatory from home, run [[Anydesk]] on both computers. Anydesk is free for personal use

## Initialising the telescope
The point of this is to ensure the telescope electronic controller is aligned with the sky. A rough initialistaion can be done as below and is good enough to send the scope to an object which can then be platesolved to get an accurate sky position:

**Rough Inititialisation**
With the telescope pointing due west and horizontal, align the shutter opening so that the telescope can 'see' out of the Dome aperture. Now, without moving the Dome manually turn the stepper motor drive wheel (which has the encoder attached) so that the Dome Azimuth indicates 255 degrees. You can see the azimuth value in the monitoring program. Now you need to initialise the Sitech Controller. See here  [[Telescope Initialisation]]

Process for a nights imaging using NINA

**Outside of NINA**
rough initialise, Set park, Park

Park

**NINA manual** (or sequence start area)
Sync dome to scope
**NINA main area**
Goto Target
Autofocus
Start Guiding
PS & Initialise (sync)
Goto target & centre
Resume guiding
capture images

**Things to find out in NINA**
1. How to PS as a one off 
2. How to nudge/ move mount > imaging tab top right scope control looks like a Plus sign and toggles apane in the imaging tab
3. How to go to a target quickly in case of failed PS
4. How to move focuser
5. How to capture a single image for focus inspection


return to [[Observatory Home]] home page
