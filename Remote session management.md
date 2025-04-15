To access the observatory computer from home (or anywhere) we use  [[Anydesk]] software. Install it on both machines. Does not require any special router config, free for personal use.

Part of being able to run the observatory remotely is the monitor program written by PK. Screenshot below:

![[Pasted image 20250414230611.png]]

This application is built in C# it runs on the Observatory computer and synthesises useful information.

So for instance when the Client (SGP currently) requests a computer and dome slew, the target azimuth for the **dome** is shown on the UI along with the movement direction and degrees to target. The monitor program has to be connected to the microcontroller control box hence the connect button.

There are also buttons to turn on the camera power when ready to use the camera. The idea was that the observatory could be visited to set up the computer in the afternoon, but be able to turn on the camera power remotely from home, thereby saving 5 amps for a few hours.







[[Observatory Home]]

