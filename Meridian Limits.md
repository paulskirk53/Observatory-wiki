## Contents

## [[#Terms]]
[[#Purpose]]
[[#Preamble]]
[[#Considering the Meridian Limit East]]
[[#Considering the Meridian Limit West]]
[[#Setting the Limits]]
[[#Setting the Meridian Limit East]]
[[#Setting the Meridian Limit West]]
[[#Other things to consider]]
[[#Meridian and Mesu - Sitech Forum]]
[[#Explanation about limits in Sitech]]
[[#Further advice on limits 18-4-21]]

## Terms
In the following description M denotes the meridian, LE denotes the Sitech Meridian limit East and LW denotes the Sitech Meridian limit West.
## Purpose

The purpose of the limits is to optimise telescope pointing for viewing/ tracking purposes, and to avoid pier collisions.
## Preamble

Taking into consideration the restrictions on movement of the mount due to constraints which a pier or tripod etc may impose, and being mindful of other constraints such as observatory obstruction to the optical axis of the telescope, the following describes the operation of Over Pole goto commands in the context of the meridian limits set in Sitech config.
## Considering the Meridian Limit East:

If a goto is commanded into the region defined by LE and LW, Sitech orients the scope to pointing west, so that tracking can continue from that point without a pier flip. So to prolong the amount of time the scope is tracking without having to flip, it seems logical to set LE to a large value, but be careful as the scope may end up counterweight up

If a goto is commanded to the East of LE, Sitech will orient the scope looking East. If tracking continues with the scope looking East and the ‘track past meridian overlap’ is reached, at this point, depending upon whether ‘GEM Autoflip Track’ is checked, Sitech either stops tracking OR flips the mount to ‘looking West’, where tracking can continue up to the ‘track past meridian overlap’ value, where it stops.

## Considering the Meridian Limit West:

If a goto is commanded into the region West of LW, Sitech orients the scope to ‘looking west’. Tracking can continue in this configuration, unaffected by the  ‘track past meridian overlap’ value as the scope is looking West. (CHECK THIS)

## Setting the Limits

It may be optimal to look at things in the following way, but there are many options.

### Setting the Meridian Limit East:

This point can be defined by the physical capabilities of the mount/ pier. In order to set LE to the most easterly point allowed by the physical constraints of scope/ pier (i.e. the limit is set so that a pier crash is avoided), the following process can be followed and only work if the mount has been initialised::

Set the mount with the scope on the east side as close to the pier as possible, such that when rotating the Dec axis, the scope will not contact the pier. Note the Scope Azimuth value from the Sitech interface. Enter this value into ‘Meridian Limit East’ in Sitech config.  

### Setting the Meridian Limit West:

The same procedure can be followed, but with the scope on the west side of the pier.

The limits are easy to change, so they can be tailored to a specific session.
## Other things to consider

Sometimes session management software may be used in conjunction with Sitech. Such software often allows configuration criteria to be used to inform pier flips, so it is important that the two systems (Sitech and the Session manager) are set to work in harmony. For instance, if Sitech LW is set to 5 degrees and Sitech track past meridian limit is set to 5 degrees, if the session management software requests a pier flip at 15 degrees past the meridian, that’s a conflict.

## Meridian and Mesu - Sitech Forum 

### Explanation about limits in Sitech

Hi Paul,
I will try to answer all your questions.  First, these settings are all dependent on your mount being properly initialized.  In other words, if the mount is NOT initialized, then these settings are meaningless and strange things can happen.

Under the German Equatorial Parameters you have checked GEM Auto Flip GoTo - this means the mount will do a flip from looking East to Looking West when you command a GOTO to a target west of the meridian limit (west).  That means your setting of 5 degrees (over Pole) is where your mount will do a MF for any target west of 5 degrees west of the meridian.  

The setting of -05 degrees for Meridian Limit East works the same way, but going in the opposite direction - GOTO toward the east.  This is a neat capability if you want to start tracking a target before it gets to the meridian, and continue tracking it past the meridian and toward the West (without a meridian flip).

Tracking limits are different.  Tracking limits are the combined value of the Meridian Limit West AND the Track Past Meridian Overlap.  So your settings would allow the tracking to  continue to 5° + 5° = 10° past the Meridian Limit.  Since you do not check the GEM Auto Flip Track box, when the mount gets to the meridian limit (looking East), the mount will simply STOP Tracking when it gets to the limit.

You are at a high Latitude, so there are many targets under the pole.  SiTech works the same way for the Under Pole targets, but tracking will be West to East.  i have never used SiTech for Under Pole operation, so I won't try to explain that.

### Further advice on limits 18-4-21

Hi Paul,

For "ordinary GEMs" the meridian limits should be small, including the Track Past setting.   There are so many mount designs and telescope designs that there is no ONE recommendation.  Generally you want to avoid any possibility of hitting the pier.  So you should know what that limit is and avoid ever exceeding it.

The  meridian limit is easy to change, so I tailor it to the local conditions.  For instance if I am imaging a target in the east, and I want to avoid a delay in the last image (waiting for a meridian flip) I may change the west limit, especially on a low Dec target where my long refactor won't come close to the pier. That simply allows a short time imaging with counter weight UP.

Recently Dan added the capability in 095M and later to use negative limits.  This allows the user to set the limit BEFORE the meridian.  Josh asked if he could set the limit to 3 degrees before meridian to avoid a cable problem.  Now you can.

So there are many reasons to change the settings, but keeping them near or ON the meridian is the safest procedure.
Don W

[[Observatory Home]]
