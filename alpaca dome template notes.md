go to the alpaca VS solution directory c:\alpaca\gowerdome2025 and open a command prompt as admin. The enter dotnet run - this runs the VS2022 alpaca dome driver and starts the web service
note that .net run does not work.

27/11/25
 alpaca dome driver just need to retrieve the comports from the profile store and display in setup.razor something like :
	port last used for shutter : COM4
	port last used for control box  : COM17
code will look like UI var = shuttercomport (note this Get reads from xml profile)
