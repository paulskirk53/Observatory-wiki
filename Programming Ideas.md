[[Observatory Home]]

[[West]] informs this idea.

When trying to implement the ideas below it became apparent that the setup dialog in the dome driver is a separate insatnce from the driver and UNLESS values are persisted in the ASCOM Profile, they are lost when the dialog is dismissed with 'OK'
This seems counter intuitive as you can do this:
Dome.Parkplace = ((int)numericUpDownParkAzimuth.Value).ToString();

in the setup dialog, which implies that the 




Currently the dome azimuth is hard coded and can't be user initialised. So for instance if we park the scope at az 270, the control box mcu is hard coded with the equivalent dome azimuth (found empirically) of 255 degrees which is initialised in setup() function.

So what if we wanted to park the scope at 90 (stop the grease flowing in one direction). We can set park and park the scope no problem. How to setpark and park the dome at the correct dome azimuth AND have that azimuth initialised when the system is next powered up? 
**Ideas:**
1
- Will need the use of EEPROM ?
- As long as the scope and dome are synced - e.g. during a live session and the scope is set parked and parked, the Dome azimuth will be correct, so a set park and park for the dome should:
	- Write the new dome park position to the ASCOM Profile
	- Send a command to the controlbox mcu to write the new park position to eeprom. The current session variable for Dome Azimuth will be correct.
	- When the Control box MCU is shutdown/ reset it should read the initialisation value for Dome Azimuth from EEPROM
- There is a risk that if the scope and dome are not BOTH parked at the same place that although they are synced in client software at session start, the sync will of course be incorrect, Dome aperture will not coincide with scope pointing.
- How do we set park and park the dome in NINA?

2 - probably better:

The park Azimuth is available in the dome driver setup dialog. It is editable at runtime when the driver properties are accessed and saved to the ASCOM profile explorer.

So, when ok is clicked on the setup dialog, a STA (sync to azimuth) command could be sent to the control box MCU. This would set the control box azimuth variable to the value requested in the setup dialog.

Note - there may be a bug in the current trial implementation of the above. The sta is issued on connection and uses the park azimuth by reading the profile, but the new value from the setup dialog is not written to the profile until the setup() dialog is dismissed. So the previous value of the park position will be used. Try using the variable that's used to write the profile on 'ok', as that will contain the changed park place if it is accessible.

use this when converting the numericupdown value tostring in the setupdialogform.cs
ToString("0.##");
same for homeplace.

