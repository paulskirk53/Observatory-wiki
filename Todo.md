
# To-Do -Current, tick when complete
link to [[Fault & Problem log]]
Immediate todo below:            [[Long term todo]]     [[Observatory Home]]

- [ ] finalise the OAG and set the prism across a corner of the SXH814C chip - adjust the Astro Frog adapter screws to achieve this.
- [ ] When connecting via devicehub on the lenovo, devicehub reported shutter closed irrespective of the switch position on the master radio box. When i brought the box home and tried it it reported shutter open. Why is this?
	- [x] Perhaps a loose switch connection? - No
	- [x] Device hub connected to Dome so USB comms ok.
	- [x] Master radio s/w Software is on box - same as when used at home
	- [x] dome driver on lenovo - this just sends SS# so SHOULD be same
	- [ ] Solution - There was un unhelpful coding error, but see see master radio github for solution to that.  BT was connected in the observatory but the shutter did not open - no fuse in the motor control!!!!
- [x] Check the master radio code and perhaps write to the lcd for one/ two seconds when the switch position is being changed - at least this will be an indicator that the switch change is happening.
	- [ ] implemented a write to lcd on switch change
- [ ] download ASCOM 7 to lenovo - BUT DEVICEHUB WILL NOT WORK STAND ALONE
- [ ] pull the new dome driver code onto lenovo and check in NINA
- [x] download ASCOM 7 to NUC - done 3-11-25
- [ ] check NUC with USB2 cable before taking up to Observatory
	- [ ] still not good - long download time. Points to NUC fault. Also the previous cables in use WERE USB2.
- [x] ensure anydesk runs on NUC for remote testing of camera
- [x] check dome rotates under power and request to move e.g. ASCOM Device Hub - done 26-10-25 checked 100 degrees of movement in both directions and the encoder matched exactly 254 -> 154 and 154 -> 254
- [x] Check a 180 or 360 degree movement of dome and check that the dome physically moves through 360/ 180 yes with an error of two degrees.
- [ ] Battery updates - see [[Lifepo4 batteries]] 
- [x] update the Pyxis 2 universal driver [here](https://www.optecinc.com/downloads/rotators/universal/) in the lenovo & Nuc machine
- [ ] find psu for Sitech controller
- [x] get vaseline for battery terminals
- [ ] pick optec pyxis Universal ASCOM for the connection in PHD2 and in NINA and see if the connection will share
- [x] Make / find a gnd cable 35cm long for connection between gnd and the dome power MOSFET box.
- [x] find out why no power at the DM860I controller - the dome did not move when requested and it looks like there was no power....gnd cable missing
- [x] can't connect phd2 and nina to the rotator - posted in nina help - see above
- [ ] At the Pyxis, we have a tube (at home) with a dovetail at one end and an M54 thread at the other. It looks like FLO have an adapter that will adapt this to M48 male which will then fit the M48 female end of the new spacer stack, 
- [ ] Install new cam and test focus
- [ ] find shims?
- [x] Upload the code update for the encoder - now on the stepper shaft.
- [x] install plugns in NINA - powerup, PHD2 tools, Hocus Focus, target scheduler, scope control
- [x] install new guider cam in phd2 on obs machine and create dark library
- [x] Take up some wire to attach the large solar panel to the building - to stop it blowing in wind. about 75 cm is fine.
- [x] Make a dual cable - need to bring the existing cable back. It needs spade terminal loops on one end of both pieces. the other ends are just bare wire to fit the epever solar screw in cable fix and the new voltage doubler - the connections on the board are obvious, but just in case +12V supply to doubler is red, 12v Gnd is black.
- [x] Take up staple gun & some staples or pins
- [ ] Peppermint spray is best
- [x] Take up the stepper motor and plate, install & test
- [x] fibreglass job - do it done 31 Aug 2025
- [x] cut off corners of stepper drive plate 
- [x] measure diameter of pipe used as drive plate pivot
- [x] drill hole in plate
- [ ] 
- [ ] 
- [ ]  OCt '25 the board worked but there's a small gap at the base. There is a very significant focus travel before any change in focus is detected, so this method isn't really helpful. Probably best to detect backlash on the focus curve. Need to do some focus backlash tests during the daytime. It's so light that a restricted aperture is needed - a sheet of ply 15 inches square with some lugs on the periphery to hang on the scope and a small  - say 8 inch square hole in the centre. Could also may an overlay so if 8 inch sq lets in too much light a six inch sq overlay might work. I guess the hole has to be larger than the central obstruction. The board in garage with plane hole cutout may be perfect.  - 
- [ ] ~={red}On the night of 17th May, guiding was good then bad with no star seemingly available and focussing half flux radius in SGP was all over the place, with masses of 'stars' so do the following=~
	- [x] check dome and scope alignment with some slews in daytime - done and was good
	- [x] check oag fixing as it wobbles - tighten the grub screw
	- [x] check oag depth into image cone
- [ ] - 
- [x] set 2x2 binning in camera tab
- [x] take up some drawing pins
- [x] paint the observatory walls
- [ ] Check the meridian flip settings in Sitech don't conflict with SGP - that may have been the problem on 5-5-25
- [ ] 



[[Observatory Home]]

