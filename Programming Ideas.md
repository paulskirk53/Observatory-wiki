[[Observatory Home]]

[[West]] informs this idea.

Currently the dome azimuth is hard coded and can't be user initialised. So for instance if we park the scope at az 270, the control box mcu is hard coded with the equivalent dome azimuth (found empirically) of 255 degrees which is initialised in setup() function.

So what if we wanted to park the scope at 90 (stop the grease flowing in one direction). We can set park and park the scope no problem. How to setpark and park the dome at the correct dome azimuth AND have that azimuth initialised when the system is next powered up? 
**Ideas:**
- Will need the use of EEPROM 
- As long as the scope and dome are synced - e.g