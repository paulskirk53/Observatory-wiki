nina connect fine. nina disconnect fine, **BUT** reconnect fails wit exception at line 410 of connect()
 2nd connection error - the port com4 has not been properly shutdown / disposed before it is re setup in setupPorts

use the two code windows to insert the exception code into connect() / setupPorts()



go to the alpaca VS solution directory c:\alpaca\gowerdome2025 and open a command prompt as admin. The enter dotnet run - this runs the VS2022 alpaca dome driver and starts the web service
note that .net run does not work.

7-12-25 when clicking identify mcu ports, clear the fields prior to refilling them
27/11/25 - done
 alpaca dome driver just need to retrieve the comports from the profile store and display in setup.razor something like :
	shutter MCU last found on port  : COM4
	control box last found on port   : COM17
code will look like UI var = shuttercomport (note this Get reads from xml profile)

a working driver is now connecting to NINA. Currently hosted by Visual studio by running the driver code in VS and running NINA, picking gowerdome 2025 and connecting. Erse
