# Trius 814c and OAG
 [[#814C manual]]
 [[#USB Cable]]
[[#USB Isolation]]

[[#Power]]

[[#OAG - setup]]

[[#Backfocus]]

[[#Camera Spacer calculation]]

[[#Focus position]]


[[#Camera connection problems log]]

[[#Problems with the camera.]]

[[#Things to try re connection]]

[[#All below Archived on 22-4-23]]

[[#Sub exposure calculation]]


## 814C manual

file:///C:/Trius%20814C%20documents/Trius-H814C%20handbook.pdf

## USB Cable

USB cable info from Terry P:

Cables are difficult, as they rarely specify anything about the construction. The best ones have a ‘wound’ screen (like microphone cables), but many have a simple foil screen with a drain wire. The cables with a braided outer cover are generally better for easily bending without kinks and cracks, so perhaps [this one](https://www.amazon.co.uk/Printer-Cable-10FT%E3%80%91USB-Braided-Scanner-Grey/dp/B08C2FV3VV/ref=sr_1_33?c=ts&keywords=USB+Cables&qid=1643549544&s=computers&sr=1-33&ts_id=430473031) is worth a try - [](https://www.amazon.co.uk/Printer-Cable-10FT%E3%80%91USB-Braided-Scanner-Grey/dp/B08C2FV3VV/ref=sr_1_33?c=ts&keywords=USB+Cables&qid=1643549544&s=computers&sr=1-33&ts_id=430473031)

## USB Isolation

This [article](https://www.analog.com/en/analog-dialogue/articles/digital-isolators-in-medical-and-industrial-apps.html) is good and there are many isolators based on the [ADUM4160](https://www.analog.com/media/en/technical-documentation/user-guides/EVAL-ADuM4160EBZ-UG-043.pdf) or 3160 (no difference apparently)

This device from [HiFime](https://hifimediy.com/product/hifime-high-speed-usb-isolator-v2/) looks as though it works at 480 Mb/ s

## Power

From Terry P re power:

As far as power goes, the camera is capable of tolerating 15v, but it would stress the cooler. I recommend that you set it at 12.5 volts, if you can, but 12 – 13v is fine.

The connector is a 2.1 mm version

All the best,

Terry

## OAG - setup

 see [here](https://www.firstlightoptics.com/zwo-accessories/zwo-off-axis-guider-oag-v2.html#about_this_product) for manufacturer’s details, also to note that I set this up visually on 8th Jan ‘23 by pointing the C11 during daytime - horsebox image and the OAG is inserted just far enough so that the HB image can be seen- i.e. minimum insertion into the image cone.

## Problem when installing

The OAG cam would not get ‘in’ enough in the holder to achieve focus when the 814C is in focus. Both would focus but at different positions - the 814c was at 13300 and the OAG at 12000

So the situation is that the FP needs to be moved OUT into the Lodestar body, since the lodestar cannot move in any more. This also means of course that the 814C CCD will need to move back by the use of a spacer between it and the OAG body. Trying to work this out 12-9-23 All worked out to get things parfocal. In the Starlight Xpress H814C blue box, is a plastic bag with a note about spacers. When the camera is mounted on the 'scope, the spacers are fitted, when the camera is dismounted, the fittings and spacers are in the polybag in the H814C box.

## Backfocus:

Back focal distance: The 814C CCD is approximately 17mm from the barrel front.

Thread into trius body is 42mm diameter

Use with the 0.8x reducer:

The working distance to the chip is 97,5mm. (from TS optics)  Measured from where????? Face of the reducer I guess.

The sequence of components is c14, 0.8x reducer, rotator, spacer, OAG, Trius 814C, so the working distance of 97.5mm is made up of:

Rotator uses 11 mm - this is the optec statement, but it is not true see below ++, so the new value is 36.25 mm

Trius backfocus uses 17mm

OAG uses 16.5 mm (from flo web) checked with rule

## Camera Spacer calculation 

Space = 97.5 - 36.25 - 16.5 - 17 = 27.75mm

Check 27.75 +16.5 + 17+ 36.25 =  97.5 

  

Checks - looking at the pyxis, just check the optical surface of the reducer to see that it is flush with the wall of the pyxis i.e. there is no extra length - otherwise the pyxis 11mm is not true and the calculation above will need to be redone with the correct value. It just looks wrong when looking from the outside, but may be ok once checked. Update when measured it is apparent that the optical surface of the reducer lies 1.75mm inside the Pyxis wall.

  

- NB - the new spacer for the camera side needs to be such that the camera is touching the pyxis rotating inner wall to ensure the optical distance is accurate. 
    
- Also, there is an unaccounted for distance between the reducer optical surface and the pyxis 11mm rotating centre - See the diagram in squared book - update - Now accounted for by external measurement of the adapters and the pyxis.

++ careful measurement of the pyxis externally shows that the pyxis introduces a distance of 36.25mm described as follows. From the front face of the reducer (which sits 1.75mm inside the pyxis) to the edge face of the Trius is measured as 36.25mm

## Focus position 
March 2025 - the focuser has been set at 30,000 when at the focus position, just so it is midway on the scale
Focus using the above image train was found at SGP/ Microtouch position = 16375 whilst focusing on a house near the foot of Rhossili downs. (Daytime image 22-4-23 at 13:30)

The spreadsheet [here](https://docs.google.com/spreadsheets/u/0/d/1v8Hg5aNnxRuQZh3xVUaXHrOCD4nP9vMGMGENeRVEr9M/edit) shows how many physical coarse knob turns out this relates to, in case this information is useful in future - 7.7 turns out from the fully screwed in position.

Notes

1. that the house image can easily be seen 800 steps either side of focus - it’s not difficult to find focus in daytime.
    
2. the exposure time of 0.001 seconds IS critical, anything longer causes white out and the pulsar dome shutter needs to be only one third open on a cloudy day to get an image.
    
## Camera connection problems log

### Problems with the camera.

The camera has been plagued with problems which manifest as pure black images - most of the time. So If I’m taking images of the black sky, there will be a mix of black and white (stars). If you’re not in focus you won’t see the stars and I’ve virtually gone mad trying.

Progress - So on 21st May, I found that images I had taken at 8 second exposure times just after sunset (9.30pm 21st May) were in focus around 17000 microtouch scale. Then they went black and only a computer restart allowed images to be taken again.

The lodestar also had a problem running from the 814C hub - error polling camera.

August 18th 2023

1. MPPT controller disconnected from the battery at the breaker. As it might be introducing RF noise (amateur radio article)
2. Battery voltage measured as 12.5 V
3. The hub USB3 cable was connected into the front blue USB socket on the NUC. Hub was powered after the NUC boot. 
4. Monitor program connected on COM3 and used to provide power to the camera/ rotator 
5. rotator allowed to home    
6. Run SGP and Connected all kit - Sitech, focuser, Rotator, dome, camera    
7. Took images of rhossili down on a 0.001 sec exposure, focus position 17000 as before.    
8. Cycled power three times to all kit and repeated the above without any error    
9. Next step - repeat the above for a week
    

  
  
  

Note that as of 17th August the two power connectors on the 814C are now supplied with power from the barrel splitter (as supplied with the 814C)

  

July 28th 2023 update
The dome functions (drive, encoder, monitoring) have now been remodelled into a ‘[control box](https://docs.google.com/spreadsheets/u/0/d/1RLFg1F5WgP97Ck7IOUJbF8Lhts_1J4T0fl-OKxMCbDc/edit)’ system which uses only two USB cables - one for ASCOM and one for monitoring. There is only one MCU. The system has been tested at home with a stepper controller connected to a small stepper motor. The encoder also connected, so a good simulation of the dome systems. All functions worked.

On July 27th, the box was installed and tried in the observatory. Both cameras connected and took images (814c in SGP and lodestar in PHD2) (not real focused images, just went through process).

Next steps for camera tests.

- Point at Rhossili down again. The camera should be in focus as nothing has changed. Replicate the image.
    
- Do the same in PHD2 and mark the camera body position if possible
    
## Things to try re connection

    
- Provide 12 V via a completely separate battery - note though that there is obviously a gnd connection between the camera USB and the Camera power supply, as evidenced by the fact that the fan speeds up when USb is inserted.
    
- Check the PSU [MOSFET](https://docs.google.com/document/u/0/d/1QGRNmt8xVuf5a18wCtlqQW1RWmkwY5kylFkkX924eAQ/edit) box for low resistance between Gnd input (i.e. battery 0V input) and the 0V output to the camera - done and fine Aug ‘23
    
- Opto isolator so that the MOSFET switch can be used to switch in an external battery for camera power if external power works.
    

  
  

## All below Archived on 22-4-23

Some of the stuff related to eyepieces and focus knob positions may be useful so I’ve kept it. The big problem with not being able to find focus with the 814C was that although the USB was connected, the 12V power was not, so the camera kept downloading blank images. Best not to think about the time I spent at night trying to focus….

Back focus measurement validation

I had been struggling to get a focus position with the C14 and C11 with the above image train in place. So on 8th Jan 2023, I set up the C11 with the train attached and pointed it out of the boiler room window at the horsebox in the field. Using a 90 deg prism and 40mm eyepiece, focus was achieved at 13 turns out (anticlockwise looking at the focus knob from the rear and with the eyepiece fully inserted into its holder).

  

With the 90 deg prism and  eyepiece moved out of the holder by 25mm, focus was achieved at 17.5 turns out, so that gives us

-  4.5 turns difference for a difference in eyepiece position of 25mm, from which we can work out that :
    
- 1 turn of the black focuser knob (not the fine focus) provides 5.5mm of mirror travel.
    

  

Without the 90 deg prism focus was 8 turns out. This is more useful as it is possible to measure from the edge of the final spacer to the eyepiece lens where the eye is placed and this was 50mm.

  

Knowing that the eyepiece alone (no prism) focused at 8 turns out and this was a measured distance from the shoulder of the spacer of 50mm, it’s possible to calculate the number of turns out (i.e. the rough focus position) for the 814c as follows

  

From the data in this doc, OAG uses  16.5mm backspace and 814C uses 17mm, so 33.5 mm total (from the edge / shoulder of the spacer). This is ~ 34mm and we know 1 Turn of focus = 5.5mm. 

- So focus position for the 814C is 34 /5.5 = 6 turns . 
    

  

This will inevitably be roughly the same as the backfocus allowance of the C14 is the same as the C11 from memory.

  

C14 specific focus

Focus on a telegraph pole with an eyepiece is 12 turns out from fully in clockwise position. With eyepiece fully in the holder. 

- If the eyepiece is moved out of the holder, the focus knob must be turned out.
    
- With the eyepiece fully in the distance from rear of Ali spacer to eyeball is 6 cm.
    

  

- With eyepiece at 7 cm, need to turn out by half a turn so one turn for 2 cm eyepiece movement
    

Focus position help

1. In the notes here, all measurements are taken from a fixed point on the back surface of the OAG receiver.
    
2. With an eyepiece inserted, measure carefully the human eye position from the receiver and compare this to the position of the 814c sensor. From the difference in cm, work out the number of turns out or in for the 814C
    
3. Perhaps do this process using a webcam rather than an eyepiece.
    

  

The above was measured on 13-3-23 and results shown below

  

Receiver to eyeball position = 46mm  (focus on telegraph pole using eyepiece 12 turns out)

Receiver to webcam ccd = 28mm

Receiver to 814C ccd = 19mm

  

Turns per cm of focus knob = 1 turn for 2 cm or 1 for 20mm

Half a turn of the COARSE knob for 1 cm ccd position difference

  

So where focus is achieved by eye at 46mm, removing the eyepiece and replacing it with the 814C causes a focus plane difference of 46 -19 = 25mm inwards, so this is 1.25 turns of the focus knob inwards from the 12 turns out i.e. 10.75 turns out from the fully in position.

Focus summary

- The image train which consists of the 0.8x reducer, rotator, spacer, OAG and camera takes up most of the C11/ 14’s backfocus, so the focus position is about 10.75 coarse turns out from the fully in (clockwise) position. When using the 814C.
    
- Scan in and out from this position USING THE FINE FOCUS KNOB ONLY until focus is found. Use the moon perhaps.
    
- NB the number of turns per mm of the COARSE focus knob is 1/20 = 0.05, SO ONLY USE THE FINE FOCUS CONTROL when adjusting the focus around the rough (10.75 turns out) focus mark. 
    
- Note that in SGP, when IN is clicked (coarse or fine), the C14 focuser moves OUT. This could be corrected by clicking the box ‘reverse focuser direction’ in SGP
    

  

focus - initial process for achieving - C14 and 814C

- Set the coarse focus knob at 10.75 turns out.
    
- Install the microtouch, data and power cables
    
- Note that a value of 300 (IN /OUT) in SGP equals one turn of the microtouch cogged drive wheel. Set coarse to say 100 and fine to 30 Focus run:
    

- Repeat until focus position obtained or 1 coarse turn of movement: (coarse step,  take 10 sec exposure)
    
- If focus found end, else repeat step a) in opposite direction.
    

Practical focus session Notes:

- 26-3-23 No Success. With the settings above, 30 SGP coarse steps (in / out) is equal to one coarse feathertouch (not microtouch) rotation.
    
- If the initial 10.75 turns out is fairly accurate, 30 IN / OUT should find focus, but as focus was not found, need to rethink
    
- Travelled in and out to 28871 and 29531 (one of these numbers must be incorrect) from the initial focus of 25511 with stepsize 150 coarse. So i’m concluding that the initial focus position of 10,75 turns out must be incorrect.
    

  

Preparation for next session

What we know:

Focus on telegraph pole with lens was at 12 coarse turns out. Replacing the eyepiece with the camera means the ccd is closer to the back of the C14 and the explanations above arrive at a position of approx 10.75 turns out. However I don’t know how the eyeball factors into this, so the 10.75 may be wrong.

  

Look at the spreadsheet [here](https://docs.google.com/spreadsheets/d/1v8Hg5aNnxRuQZh3xVUaXHrOCD4nP9vMGMGENeRVEr9M/edit#gid=0)  in order to get a strategy for scanning the potential focus range.

1. Use SGP value of 400 as per sheet and scan IN from 25511 taking an image at each step. If no focus found, step OUT once by half the original step (i.e. 400/2 = 200) and continue OUT with SGP step value of 400. This process essentially scans the entire range in steps of 200.
    
2. Repeat step 1 above in the opposite direction and back
    

  

Outcome of session on 3-4-23

…..no focus found on scans at every 400 steps from 25511 to 6711, and 26091 to 54091

  

Next - use the lodestar with the sensor at the same position as the 814C’s to find the focus on the lamp post.

  

19-4-23

Used lodestar with exposure time of 0.002 sec and obtained focus on distant house @ 16200 microtouch/ SGP scale indication. Now need to measure the lodestar chip distance from the back of the camera receiver, in order to get par focus with the 814C.

- Coarse step was 400 and from the focus point, 2 x 400 steps still gave a blurred image on either side of focus
    
- Clear focus obtained at 16200 on the SGP / microtouch scale
    

  

GIF focus animation for SCT

https://www.cloudynights.com/topic/467365-sct-backfocus-animations-fratio-vignettingetc/

## Sub exposure calculation

How to calculate sky background electron rate:

[https://tools.sharpcap.co.uk/](https://tools.sharpcap.co.uk/)

  

For use in Robin Glover’s formula:

  

Subexposure calculator from Robin Glover's work, 

  

Sub exposure in seconds =  10 x RN^2/p, where RN is the read noise in electrons RMS, and p is the light pollution rate in e/pixel/second).

  

The value of p (using the link above to calculate it for scope @f8) is :

  

And the read noise of the 814C is :

  

So the optimum sub exposure is