
# To-Do -Current, tick when complete
- [ ] Check voltage at the USB Hub power lead.
- [ ] shutter ssr40dd only shows its light for two seconds then goes off. no power supplied to dome stepper. this was testing the already open feature when power comes on. **I suspect from testing with the simulator, that the open position is not set - use queryop and setop and try again. Check the emergency stop button on the HC too**  A value of zero for open position in the simulator seemed to reproduce the problem.
- [ ] 
- [ ] usb hub failure - the monitor would not connect but would connect when the control box was directly connected to nuc port. The on / off switch has stopped working too.
- [ ] Take some daytime images with the lodestar connected to see if it stays connected in PHD2, and also that the image quality is good.  Then - see next item below:
- [ ] Connect the SX camera USB directly to the NUC - this can be done by removing the mouse USB transmitter to the HUB
- [ ] Try increasing the GEM offset by 50 mm to cure the N misalignment. **Tried on 16-4-25.** It had the desired effect when looking E, more testing req'd
- [x]  Upload the control box code
- [x]  Upload the shutter code
- [ ] Set up the rotator & check it connects
- [x]  **Take a saw to saw off the plywood back** of stepper  motor support.
- [ ]  Retry the dome slew & sync to scope tests with a client connected e.g. Cartes du Ciel, the scope and dome. Check NSEW alignment.
- [ ] 
- [x] tonight target is around 140 deg azimuth ra 12 dec 32 - align the scope
- [x] connect up the chain
- [ ] connect battery power to shutter
- [x] run anydesk
- [ ]  **Don't do this until the new toothed wheel arrives** check the ticks per dome rev accuracy by rotating the dome through 360 and check if the misalignment is consistently over or under. There are 44 ticks per degree, so mod the code as req'd.


**11-4-2025**
* Take the jtag2updi programmer and upload the code to the control box - **does not work** - the problem has now been fixed on the NUC - incorrect version of avrdude which did not support updi. The code has now been tested on the simulator box
* Check the new driver amendments re dome geometry and sync to azimuth. Hopefully the dome positioning will be more accurate. Try positions at NSEW - **awful result** , but new information from Bob Denny on ascom developer talk, points out that you MUST have a client connected as well as the scope & Dome. **Re try the test**
* Check the radio box works - tested at home fine - a new switch has been installed on the box which has a normal and override position. In the override position the shutter is always reported to ascom driver as open. It's a way of being able to keep going with imaging if the bluetooth or something shutter related goes awry. Shutter must be opened and closed manually by hand. **Worked fine at Observatory**
* take up some drawing pins
* Paint the walls of the building

**6-4-2025**

recheck the dome geometry: - **done 10th April 2025 new values here** [[Dome  Automation]]
things to take
string
tape measure with lock facility
spirit level
long timber about 90 cm to 1 metre
fishing weight
paper clip to mark 1.1 metre point on string for U/D measurement
procedure:
- # first - move the dome by hand through 360 to check azimuth is consistent - done and a complete rotation was perfect - 1 or 2 degrees out.
	- Move scope horizontal
	- install plumb line
	- measure with tape & level to ensure plumb is centred in dome NESW and also to measure accurately how much offset there is due to plumb/ mount interference if necessary
	- make sure the measurements taken are in NESW directions
	- scope east of dome O is +
	- scope north of dome O is +

**March 2025**
1. Install the buck boost for the dome drive **done** Apr 2025
2. Ditto for the main equipment battery when it arrives. **done**
3. Get a box for the new buck boost device **done**
4. Try out the dome drive to see if it syncs with the telescope, following the updates to the GEM  offsets - done in ASCOM device hub and also in SGP. done, pretty good except N direction.


[[Observatory Home]]

