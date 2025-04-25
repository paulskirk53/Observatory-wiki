A strange name for an obsidian note, but it's not as simple as it seems.

So for instance when te dome and scope are both pointing West (Azimuth 270 degrees), the scope won't be aligned with the aperture. Why ? Because of the GEM offsets.

What are GEM offsets? Why am I writing this as the only reader is probably going to be me?

GEM offsets describe the difference  in the positions of the Dome Origin (DO) and Telescope Mount origin. The telescope mount origin (TMO). Ideally, these two points would occupy the same point in space, but unless you're a precision engineer, the likelihood is that they won't, and in our case and many others, they don't. The added complication of a German Equatorial Mount (GEM) also means that even if your TMO and DO occupy the same point in space, there is still an offset due to the mechanical structure of the GEM mount which means that the optical axis is ALWAYS offset from the TMO. Easy stuff of nightmares. So here's what you have to do to set up the GEM offsets for a GEM mount like [[MESU200 mount]] 
- find the DO (use string and the DO is where two diameters at rt angles cross)
- The TMO is the intersection of the RA axis and the DEC axis. Generally it's not an easy spot to define and brain power is needed.
Our process is described here [[Dome  Automation]] and the page identifies the GEM offsets required for our setup with the Pulsar Dome and [[MESU200 mount]]. 

Why am I writing this? To try to get my own head around it. When is west not west? when its affected aby a GEM offset. 

**Key Part**
So if we set the scope counterweight down and scope pointing due west and levelled with a spiritual level, the scope azimuth will be due west 270 degrees. If we arrange the dome aperture to align with the scope so that the scope 'sees' out of the aperture, what is the dome azimuth ? I have no idea, but it's not due west 270 degrees. Empirical testing has shown that the software which controls the dome positioning taking into account the scope azimuth - software such as [[Sequence Generator Pro]] or [[ASCOM Device hub]] requests the dome to move to Azimuth position 255 degrees. There is no way to know what are the equivalent azimuth positions for the scope and dome, but they are NOT the same due to the GEM offsets.

**Why is this so tiresome?** Well, the answer lies in two places. 
- One is the dome 'park position' - which is set in the ASCOM dome driver setup dialog which also of course relates to a physical position of the dome, 
- and the other is that an azimuth figure has to be set in the control box microcontroller software and this also equates to a position of the dome.
So I think the solution is to position the scope due west and initialise it there, set park and park. Then physically align the dome aperture with the scope so the scope can 'see' out of the aperture. This is dome azimuth 255 de 



