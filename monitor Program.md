This is a C# program I wrote, it's on github [here](https://github.com/paulskirk53/Monitoring-Observatory-MCUs) I use Visual Studio as the IDE

**Jan 2026 changes**
In vs an event driven serial receiver has been created and trialled with an arduino mega. It works fine
Idea is to reduce usb traffic by polling for data packets only once every 20 seconds when the mount is not moving
in order to do this the MCU has to send "slew-start" and "slew-end" with dollar sign terminators which obsidian can't cope with
the data packet polled from the c# monitor program inside a timer tick is also 

The program pulls data from the dome control box, described here [[Control Boxes]] 


[[Observatory Home]]
