[[Observatory Home]]
There is an **ascom Dome device driver** I wrote (   [[Dome Driver]]  ), it is called pauldomeinC. Load visual studio on the NUC or Dev machine at home to access it. It's pretty specialised stuff and took me about eighteen months elapsed time to get to grips with the ASCOM context for drivers. You can find it on Github under paulskirk53 The driver inplements everything required for operating a GEM mount. It will not work for an altaz mount - it would need amending.
There are also programs which receive data (commands and requests) from the ASCOM driver and carry them out. e.g. the ASCOM dome driver might get a request from the SGP client to slew to a particular azimuth. It passes this request to the microcontroller which drives the stepper motor and monitors the shaft encoder. All these programs reside on microcontrollers - Arduino Mega2560 and AVR4809
All the code is on github remote and also on the local machines (NUC  & Dev) I have kept them all up to date and the Master branch is always the current version.

**GEM Offsets**
For the automation to work properly in terms of syncing the dome aperture with the telescope pointing direction, there are offsets. This concept arises because the telescope centre is very unlikely to be the same as the Dome origin. To really tangle up your brain, see this note ( [[West]] ) which refers the reader back to this note for the GEM offset identification process described below....

So on 10th April 2025, I set up strings inside the dome tied to sticks clamped onto the dome perimeter. I used two at right angles and where they cross is the Dome origin.
The other point of relevance is the intersection of the RA and DEC axes. This isn't easy to pinpoint as it's inside the intersection point of the RA and DEC shafts. You need to estimate carefully.

I took four readings, two with a carefully centralised plumb bob hanging down from the top of the dome aperture. It coincided nicely with the cross strings. The readings need to be averaged.

Here are the pairs of measurements - DO is Dome Origin and Point 'A' is the RA/ DEC intersection. All measurements in mm, but it matters not as long as the same measurement unit is used throughout...

First pair:
1. 'A' is 90 North of DO
2. 'A' is 10 West of DO
Second Pair
3. 'A' is 100 North of DO
4. 'A' is 5 West of DO
Third pair - measured against plumb bob line
5. 'A' is 100 North of DO
6. 'A' is 10 West of DO
Fourth Pair - measured against plumb bob line
7. 'A' is 105 North of DO
8. 'A' is 10 West of DO

**Averages**
North figure 395/4 = 99
West figure 35/4 = 9 - as this is 'A' West of DO, the value entered will be minus, see below.

There is also the Up / Down figure for which two measurements were taken from the roof of the dome down to point 'A' (in mm)
1. 960
2. 970
Average 965

The dome Origin for vertical measurement is 1100mm from the top down vertically, so point 'A' is 1100- 965 = 135 UP from the DO

**Summary**
in SGP and also in the ASCOM device hub (which we sometimes use ) enter the following figures in mm
N/S enter 99 (north +ve)
E/W enter -9  (minus 9 as west is defined as -ve)
U/D enter 135 Up defined as +ve
There is also the optical axis offset for a GEM Mount and empirically, it seems good alignment is obtained with a value of 500 (added Nov '2025)

[[Observatory Home]]

**Use of SGPro Sync function** in Observatory panel:

Sometimes the dome is not correctly synced so I asked Copilot AI about use of the sync function:
**Q**
So if my telescope is correctly pointing at an object but the dome aperture is misaligned by 15 degrees how can the sync function help me?
**A**
If your telescope is correctly pointing at an object but the dome aperture is misaligned by 15 degrees, the **Sync** function in Sequence Generator Pro's Observatory panel can help by aligning the dome's reported azimuth with its actual physical position. Here's how you can use it:

1. **Manually Adjust the Dome**:
    
    - Rotate the dome manually so that the aperture aligns perfectly with the telescope's field of view. (PK addition - have to unslave to do this or ASCOM will realign)
        
2. **Use the Sync Function**:
    
    - Once the dome is correctly aligned with the telescope, click the **Sync** button in the Observatory panel.
        
    - Enter the dome's current azimuth angle (as it should be based on its physical position). For example, if the dome is physically pointing at 0° (north), input 0°.
        
3. **Update the Dome's Azimuth**:
    
    - The Sync function will update the dome's internal azimuth reading to match its actual position. This ensures that the software and the dome are in sync.
        
4. **Enable Slaving**:
    
    - If you have the "Slave to Telescope" option enabled, the dome will now move correctly to follow the telescope's movements, keeping the aperture aligned.
        

By syncing the dome's azimuth to its true position, you correct any discrepancies between the dome's reported position and its actual orientation. This ensures accurate alignment for the rest of your session. Let me know if you'd like further clarification!


possible query to ascom developer hgroup
Hi All,

I think I need to know the formula used to calculate dome azimuth from scope azimuth so that I can properly initialise the dome in the right place.

For example, at the start of an imaging session, I roughly initialise my scope (GEM Mount) counterweight down and scope optical axis horizontal looking at azimuth 270 degrees. I can physically align the dome aperture with the scope, no problem, but what azimuth is that? It's not 270, mostly because of the GEM axis offset, which on my setup is 500mm (14 inch SCT).

Is the formula used available anywhere ?

I'm using a workaround which is to use an initial dome azimuth of 270 and then sync the dome to the scope. As part of the sync, the dome receives a request to move to 255 degrees, at which point I manually align the dome aperture with the scope without changing the shaft encoder which measures dome azimuth. I could hard code 255 into my microcontroller but that wouldn't be a good idea....


return to [[Observatory Home]] home page