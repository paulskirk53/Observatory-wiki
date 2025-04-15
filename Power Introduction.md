
# Overview
The Observatory has no mains supply, so over a five year period things have evolved. It is challenging and a number of things have been tried including providing mains power from batteries using a Victron inverter. The problems were twofold - one is that the inverters are not very efficient in reality so the batteries discharge quite quickly and second the observatory floor fills with water so the risk of electrocution is too high. So I've settled on two 120 AH batteries in parallel charged by a solar panel & Controller as the base supply. 

For the shutter, which is of course on the rotating upper part of the Dome, two 12v 8AH batteries are connected in series to provide 24V for the [[DM860I Stepper controller]] which controls the shutter stepper motor - an 8.9 nM monster.  The one 12v battery is charged by the Epever controller and so I think at some point a DC boost from 12V to 24V as per the one used for dome power, will be used here. That will mean all the batteries are charged via solar and controllers.

- ### 'Main Battery 120AH'
	- Charged by two solar panels & an MPPT controller on the Observatory wall. Inline switches are provided for the panels and also the battery.
	- The output circuit to the DC booster has a 5 amp blade fuse.
	- Connected in parallel with the Dome drive battery for charging purposes and to a DC boost device which provides 13.6 volts to all the following gear:
	- [[Focuser]]
	- [[Sitech Telescope Controller]]
	- [[NUC]]
	- [[Camera]](s) Via an electronic switch activated by the [[monitor Program]]
	- [[Camera Rotator]] Via the same electronic switch activated by the [[monitor Program]]

- ### Dome driver Battery 120AH
	- Uses a DC boost to 24 Volt for supply to the [[DM860I Stepper controller]].
	- Connected in Parallel with the 'main' battery for charging purposes.
	- The output circuit to the DC booster is protected with a 5amp blade fuse.
	- Provides power to the [[DM860I Stepper controller]] for the dome rotation drive only.
	
- ### Shutter Driver Batteries
	- Two 12v 8AH batteries in series which powers the [[DM860I Stepper controller]]
	- Currently not fused - needs to be done
	
[[Observatory Home]]

Tags
#battery #12volts #DC #Boost #power 