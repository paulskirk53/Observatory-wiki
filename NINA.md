[[Observatory Home]]

good tutorial on the sequencer - scroll along
https://www.youtube.com/watch?v=VqfAg2AoPYE&t=921s

**Simulating guiding in PHD2**

the following equipment profile is required:
Camera - choose 'simulator'
Mount - choose 'On-camera'  (phd2 chooses this for you if you pick 'simulator' as the camera.)
Aux Mount choose 'Telescope Simulator for .NET (ASCOM)'

The profile I created on 27th September 2025 is called Test

**Setting up:**

Equipment > go through the tabs and select the equipment from dropdown.
See **Options** below for setting up Dome geometry

There's a connect all button at bottom left.

**Options**
**Plate solve :**

Options > Plate solving - set up ASTAP

**Dome** > Dome Geometry

**Imaging** > file paths, image formats
Note - focus has option for NINA or Hocusfocus
**Autofocus** - The kind of options req'd in sgp - step size, Number of steps etc
**read up on hocusfocus / NINA option** which is best for SCT
How to ensure Hocus Focus is the AF in use: Nina -> Options -> Imaging -> 'Image options' -> Star Detector, Star Annotator, Autofocus 

**Equipment :**
spec details for camera, mount, scope, planetarium etc


**Sequencer**
startup sequence for observatory:

**Assumptions**
- Mount is initialised at 270 and parked
- Camera is roughly focused

connect:
- Camera, autoguider, PHD2, Rotator, Dome, Sitech, focuser.

Sync:
- Dome to mount

Move to target:

Autofocus:
- for best platesolve and image results


Plate Solve - if it works, or
Move away, but close to target and Plate Solve
Move to target

see here for AI help [[NINA PS]]

