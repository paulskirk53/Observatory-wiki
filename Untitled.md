```div.markdown-preview-view pre {
  background-color: #000000 !important; /* Black background */
  color: #FFFFFF !important;           /* Bright white text */
}

```

```cpp

  

if (SRAMToggle == 1 )

  {

    /*software resets execute the line below, which preserves the dome azimuth at point of reset.*/

    A_Counter = ticksperDomeRev / (360.0 / float(SRAMAzimuth) );  // set the azimuth to the value stored in EEPROM

  }

  else

  {

    // initial power cycled starts execute the line below

    A_Counter = ticksperDomeRev / (360.0 / 270.0); //  the position of due west

  }

  

  PowerForCamera(off); // camera power is off by default

  

  stepper.stop(); // set initial state as stopped

  

  // Change below to suit the stepper

  

  Slewing = false;

  StepsPerSecond = 300.0;              // changed following empirical testing Oct 2020

  normalAcceleration = 140.0;          // changed following empirical testing October 17th 2020 - changed from 40 to 20 for trial

  stepper.setMaxSpeed(StepsPerSecond); // steps per second see below -

  stepper.setCurrentPosition(0);

  stepper.setAcceleration(normalAcceleration); // steps per second per second.

  // initialise
```