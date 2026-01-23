This is a C# program I wrote, it's on github [here](https://github.com/paulskirk53/Monitoring-Observatory-MCUs) I use Visual Studio as the IDE

**Jan 2026 changes**
In vs an event driven serial receiver has been created and trialled with an arduino mega. It works fine
Idea is to reduce usb traffic by polling for data packets only once every 20 seconds when the mount is not moving
in order to do this the MCU has to send "slew-start" and "slew-end" with dollar sign terminators which obsidian can't cope with
the data packet polled from the c# monitor program inside a timer tick is also terminated with $

22-1-26 todo
- change from ascom utilities serial to system.io.ports
	- done a lot of this get and set park and home need attention now - done
- Because we aim to move to event driven serial comms, each packet sent back by the MCU will need to be prefixed, so that it can be routed to a routine which carries out the actions associated with the response.
	- note that blocking comms is best for MCU discovery, so leave checkformcu as is, and once the port is open, switch to event driven comms by:
	- placing this line in the code, probably at the end of connect() : control_box.DataReceived += ControlBox_DataReceived;
	- there are only five routes : Get home, Get park, DataPacket, slew-start, slew-end (the latter two for setting the timer interval for polling datapackets)
	- note that all data terminators will meed to be the same, so change the datapacket to comma delimited with a '#' as the packet terminator. This makes all terminators consistent. The parsing will need to change to accommodate , delimited instead of '#' delimited.
- strip the code out of timer tick and place in handleDataPacket(string msg) - this is the parsing stuff
- create private void handleSlewStart() which sets the timer tick interval to 1500 mS
- create private void handleSlewEnd() which sets the timer tick interval to 20000 mS
-  create private void routeMessage(msg) as per line 62 of the minimal-event-driven-serial c# code
- 





The program pulls data from the dome control box, described here [[Control Boxes]] 


[[Observatory Home]]
