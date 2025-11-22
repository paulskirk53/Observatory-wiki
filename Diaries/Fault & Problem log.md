**Newest entries at top**     see here for [[Todo]]  and here for [[Long term todo]]
[[Observatory Home]]
**22nd November 2025**
There were three nights clear, but rain showers later in night a possibility, so needed shutter to close, but there was a problem

**Leaks Aug 2025**
30th August 2025 a rainy day so I decided to goto observatory to check where the leak is:
- Fibreglass on outside has not bonded to the collar, so water collects on top of the fibreglass and runs onto and underneath the collar. Requires a fibreglass fix as PU sealant will not bond to Fibreglass. You can press down on FG to detect the problem area - 8 inches left of the collar join looking from outside. On the inside water in quite large volume can be seen between the collar and the wood base.
- there was a small drip on the collar join left of the aperture join (when aperture is in south orientation) - this needs investigation of the seam outside.
- All other dome joins were watertight - no evidence of water on shelf or inside of dome anywhere
- serious 'dampness' at the base of the aperture not sure why

Get the log of **night of 16th**  too as focuser error and centring error when aborting centre operation - the dialog stays open and the only option is to kill SGP. Session finished at  23.34 probably started at 22:00 
from AI re guiding becoming erratic when autofocus runs - as star shapes change, guiding errors creep in. Best to pause guiding. Also dithering conflicts - probably dithering after each autofocus image.

**night of 15th and a.m. of 16th May**
Get the sgp log for night of 15th as focuser error : obtained half flux radius of zero twice something must be wrong



28-4-25
I finally decided that the SXH814C has to go. It wouldn't connect when run from a 12V battery (no DC boost), so that's it. But see below...
I intend to go back to the Canon EOS for now the backfocus is 44mm compared to SX 17mm, so the focus position will be 27 mm further in and this means the  lodestar will be further out - it may not be able to get out by  27mm, so an axtension tube may be necessary.

When I bought the lenovo machine ( which had to be powered from the victron inverter) the camera connection problem has gone - completely. So its either the computer, or powering the computer from the mains which made the difference. Download speeds are about 10 seconds.

The other thing was that the toothed wheel was not a T10, so it didn't work on the toothed belt, so reverting back to friction wheel for now.

**27-4-25**
The shutter code persists in being problematic. The fix applied which noted that the wdt was updated before the timer was enabled seems to have been a red herring. The shutter still does not work. Needs more brain power.


**19-4-2025**
see the [[Todo]] page for problems found recently e.g. 
- failed USB hub leading to lodestar lost connection - I connected the SX H814C hub with a different cable directly to NUC and took some daylight pictures using PHD2 0.02 sec exposures. The camera kept its connection and images were good if a little out of focus as to be expected.
- the shutter code needs debug due to power failure.
- 
[[Observatory Home]]
**16-4-2025**
A clear night PA looks good as a 30 sec main cam image showed nice round stars.  Remote management worked, I plate solved from home, but the Lodestar failed to download images - an error was posted by PHD2 - see the snip on NUC desktop. End of observing session.
The other irritting probelm is that when platesolving using control panel in SGP, SGP complains that binning is incorrect (!) and scraps the values of scale factor, so I have to enter the FL and pixel size for the main Camera again and click the calc button to get the scale - which is the same as it was before of course. See NUC desktop for snip of error. See [[Todo]] for actions related to this post.


**3-4-2025**
A lot has happened, in the period since the last entry on 18th March an update below
It has been a frustrating time as the night sky has been clear for about three weeks due to high pressure. Here's the problems:

- Camera would not work 814C would not connect. Discussions with Terry Platt tried install of drivers, no joy. Decided to try installing the drivers on the WIN 10 dev m/c and the camera connected and continued to connect when transferred back to the NUC where there had beenn no changes. I have no idea what's going on. Greg is phasing out the SX cams and using the ZWO aps cmos chips instead. Good idea. So camera now working :) .....
- I have now accurately determined the offsets dome/ RA & Dec and added these to ASCOM device hub and SGP In tests the dome seemed to position properly when slewing to various daytime targets. However it would not track when used in SGP and today by chance I found in the SGP forum that there's a bug in the observatory panel - clicking slave here does not work, it has to be done in control panel.
- **The focuser position is not shown in SGP** - it just stays at 30,000 although the focuser can be heard to move when in/ out coarse /fine is clicked in SGP Latterly though clicking in / out did not make the focuser move.
- **Auto focus curves** are a mess and the scope will not autofocus
- **Polar alignment** was out and I redid this on the night of 1st April 2025
- Added a boost converter set to 13.5 volts for the main equipment (MESU, rotator, 814C, NUC, USB hub, Focuser)
- Installed a boost converter for dome drive - this is 12v boost to 24 V
- Bought another voltage converter for use with the canon EOS this converts 12V DC down to 7.4V and is in a black plastic box awaiting install.
- I have used AI copilot extensively to ask about gear issues
- Trying now to upgrade to **latest version of SGP** enquiring about cost.
- **Charging the two 12v 110AH batteries** in parallel from the Solar charger now, following advice from Copilot AI
- Using anydesk for remote access.
- There are too many spiders...
- 


**18-3-2025**
**Cameras**
Tuesday - a lovely blue sky day and same at night. h814C Camera connected but a 90 second image of a starry sky was jet black. Lodestar would not connect.
I think this is a battery voltage issue. I used Sitech  servoconfig to check the battery volts at the controller and it was 11.7. This is too low for Sitech really.

So I bought a buck boost [device](https://kunkune.co.uk/shop/dc-to-dc-converters/250w-10a-boost-converter-step-up-module-8-48v-to-12-50v-adjustable/) after talking with copilot AI. I can set this at 13.5v o/p and it will provide a stable voltage up to 10 A current. I think the max current spike we'd get is around 6 amps.

[[Observatory Home]]

