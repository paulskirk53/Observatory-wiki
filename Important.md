
This is a list of useful stuff
[[Observatory Home]]

**If the Mount loses Sync during remote observing.**
Sometimes if there's an error, Sitech loses sync. You can tell by taking an image - say 15 seconds and look for star trails. Also on the Sitech interface it will indicate 'Stopped'

**If this happens t's important not to park or do a goto** Instead start tracking and do a platesolve to resync and recover the mount.

If the mount is parked it goes to a crazy unknown position and is not recoverable except by visiting the observatory and setting the mount counterweight down and scope horizontal facing west (the usual park position).

**Focuser Backlash**
Try about 150 steps - from AI Direction IN works best with SCT apparently

**PHD2 settings**
In camera tab, set 2 x 2 binning as If guide stars are **faint**, **2x2 binning** will improve tracking reliability.
star mass detection is deprecated
For your **Mesu 200 Mk II**, which is a **friction-drive mount**, backlash is minimal, but enabling **Declination Compensation** can still help refine guiding accuracy. - careful as there's a Sitech config setting for it too - don't enable both.
