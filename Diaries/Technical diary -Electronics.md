
13-3-25
## Dome drive
The field test showed the dome drive motor turned in the wrong direction so needs a field pair swapping e.g. swap A+ and A- (done & worked)
Also the encoder wiring - one lead had broken. - now repaired.

12-3-2025
## Dome drive
Finally the dome drive is functional in as far as when its connected to power and the NUC, it will drive the stepper motor with torque such that it cannot be stopped by hand. Using an arduino sermon issuing commands Sl# (slew status) and SA270# (slew to azimuth) worked fine with acceleration and deceleration. Power supply was two 100AH batteries in series and a DM860I controller borrowed from the shutter. The above was at home, so now need to take it all back to observatory and use ASCOM Device hub to connect and slew to a target. Do some in daylight to check out positioning.

20-3-2025
**Dome Drive**
Following the above post re testing the dome tracking the scope, it was great to see it work really well today, following the correct identification of dome origin and scope origin. I attached a plumb bob to the dome top on a horizontal stick - a bit of a palava as the dome origin is slightly obstructed by the sitech mesu mount. So I had to move the plumb bob attachment point south by 42mm it's no big deal, just account for that when measuring the distance between the scope RA/ Dec intersection and the dome origin. The E-W location point was not obstructed so the measurement was pretty easy.
the figures obtained were as follows:
scope origin north of dome origin by 120mm
scope origin East of dome origin by 10mm (a very small amount)
scope origin Above dome origin by 163mm
GEM offset 452mm
**tests**
Today I used the ASCOM device hub connected to SItech and the Dome. I set the Dome to slave the scope and then sent Sitech to M77 (located southish in Cartes Du ciel), then to an object west, then east then North. I had the dome adjustment slider in ASCOM Device Hub in the centre. All slews worked well in that the dome slit aligned with the scope. That was really great to see. :) :)
The only slight downside is that the dome seems to do two movements in order to get to target and I'm not sure why that might be. It also needs more weight to pull the drive belt in tighter to the rack.





[[Observatory Home]]
