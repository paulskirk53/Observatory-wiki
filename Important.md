
This is a list of useful stuff
[[Observatory Home]]

**If the Mount loses Sync during remote observing.**
Sometimes if there's an error, Sitech loses sync. You can tell by taking an image - say 15 seconds and look for star trails. Also on the Sitech interface it will indicate 'Stopped'

**If this happens t's important not to park or do a goto** Instead start tracking and do a platesolve to resync and recover the mount.

If the mount is parked it goes to a crazy unknown position and is not recoverable except by visiting the observatory and setting the mount counterweight down and scope horizontal facing west (the usual park position).

**Focuser Backlash**
Try about 150 steps - from AI Direction IN works best with SCT apparently
**Autofocus**
#### use 2 x2 binning - essential
- get best focus possible manually (could look at HFR in image stats as adjusting)
- use star icon on first 8 second 2 x2 binned 'take one' image
- note the HFR value in 'image statistics' as 'X'
- note focuser position
- use start now to take a sequence of images and note when HFR is 4 x larger than 'X'
- Calculate step size subtract initial focus position from the current focus position multiply by 2 and divide by eight (as we have nine focus points set). Enter this value in the AF settings field.
- #### Save to equipment profile and to current sequence.
- #### all the above summarised from the SGP guide [here](https://help.sequencegeneratorpro.com/UnderstandingAutoFocus.html) 


**PHD2 settings**
- In camera tab, set 2 x 2 binning as If guide stars are **faint**, **2x2 binning** will improve tracking reliability. **Also note according to AI** that the pixel size for the camera now changes to double (17.2) the previous value of 8.6 - **this is not true**
- ** recalibrate**
- star mass detection is deprecated
- For the **Mesu 200 Mk II**, which is a **friction-drive mount**, backlash is minimal, but enabling **Declination Compensation** can still help refine guiding accuracy. - **careful** as there's a Sitech config setting for it too - don't enable both.
