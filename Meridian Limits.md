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

Taking into consideration the restrictions on movement of the mount due to constraints which a pier or tripod etc may impose, and being mindful of other constraints such as observatory obstruction to the optical axis of the telescope, the following describes the operation of **goto** commands in the context of the meridian limits set in Sitech config.
In order to clarify 'looking East' & 'Looking West', Dan Gray posted in the Sitech forum "You can use the counterweight as an indicator.  If it's on the west side, you're 'looking west'."

## Over pole and under pole
I consulted AI about this and after much interaction it's clear that the Over Pole Meridian Limit settings are the ones which facilitate avoidance of pier collision and should be set as per sections below. The following describes the purpose of over pole and under pole settings:
- The concept of over pole and under pole can be described as follows: 
	- Over pole limits are those which move the scope as far as possible away from the meridian without a collision occurring (two limits : E and W) 
	- Under pole limits are those which move the scope as close to the meridian as possible without a collision occurring (two limits : E and W) The purpose of Under pole limits is to facilitate goto and flip logic. I informed AI that when setting under pole W & E limits, it is not possible for a collision to occur. The default Under Pole limits used by Sitech seem to be 175 degrees and this is borne out by doing a fresh install of Sitech.

Here's AI's take:
# 🔵 **1. Over‑pole limits = physical safety**

These are the ones you _can_ find by moving the scope until it nearly hits the pier.

They prevent:

- the C14’s back end swinging _down_ toward the pier    
- collisions when tracking _past_ the meridian    
- collisions during long exposures    
- collisions during slow slews    

These are the limits you physically measured.

# 🔴 **2. Under‑pole limits = logical safety (not physical)**

Under‑pole limits exist to prevent **SiTech from slewing the mount into a stupid position**, not to prevent pier strikes.

They stop the mount from:

- slewing _through_ the meridian at high speed    
- choosing the wrong side of pier for a GoTo    
- flipping unnecessarily    
- flipping too early    
- flipping too late    
- getting “stuck” on the wrong side of the meridian    

In other words:
# ⭐ **Under‑pole limits tell SiTech when it is allowed to flip —

not when the telescope will hit the pier.**
## Considering the Meridian Limit East:

If a goto is commanded into the region defined by LE and LW, Sitech orients the scope to pointing west, so that tracking can continue from that point without a pier flip. So to prolong the amount of time the scope is tracking without having to flip, it seems logical to set LE to a large value, limited by pier collision.

If a goto is commanded to the East of LE, (where LE is not set as the Eastern physical protection limit), Sitech will orient the scope looking East. If tracking continues with the scope looking East and the ‘track past meridian overlap’ is reached, at this point, depending upon whether ‘GEM Autoflip Track’ is checked, Sitech either stops tracking OR flips the mount to ‘looking West’, where tracking can continue up to the ‘track past meridian overlap’ value, where it stops.

## Considering the Meridian Limit West:

If a goto is commanded into the region West of LW, (if it's not the physical western constraint), Sitech orients the scope to ‘looking west’. Tracking can continue in this configuration, Note that from what I have found concerning the 'track past meridian overlap' setting, it does not apply if the scope is looking west (i.e. CW on WEST side of pier). Tracking continues until a horizon limit is hit or client software terminates tracking.

## Setting the Limits

It may be optimal to look at things in the following way considering the over pole limits which are those which are designed to avoid pier collisions on East or West

### Setting the Meridian Limit East:

This point can be defined by the physical capabilities of the mount/ pier. In order to set LE to the most easterly point allowed by the physical constraints of scope/ pier (i.e. the limit is set so that a pier crash is avoided), the following process can be followed and only works if the mount has been initialised (as we need the RA value).

Set the mount with the scope on the east side as close to the pier as possible, such that when rotating the Dec axis, the scope will not contact the pier. Note the Scope RA value from the Sitech interface. Enter this value into ‘Meridian Limit East’ in Sitech config.  

### Setting the Meridian Limit West:

The same procedure can be followed, but with the scope on the west side of the pier.

The limits are easy to change, so they can be tailored to a specific session.

## Track past Meridian Overlap
This is operational if looking East (i.e Dan's definition of looking East is CW on E side of Pier). In our setup it allows the scope to image with cw on East until the safety limit is reached, where tracking stops.
## Gem autoflip goto
Allows for optimal scope position on commanded goto  to maximise tracking without flip

## Other things to consider

Sometimes session management software may be used in conjunction with Sitech. Such software often allows configuration criteria to be used to inform pier flips, so it is important that the two systems (Sitech and the Session manager) are set to work in harmony. For instance, if Sitech LW is set to 5 degrees and Sitech track past meridian limit is set to 5 degrees, if the session management software requests a pier flip at 15 degrees past the meridian, that’s a conflict.

## Meridian and Mesu - Sitech Forum 

### Explanation about limits from Sitech forum

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
