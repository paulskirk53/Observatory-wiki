One control box services the [[Sitech Telescope]] and [[Dome  Automation]] and another one services the [[Dome Shutter]] open / close function.

Picture of Dome control box:


**Function of the box**
The box hosts an AVR4809 microcontroller which is custom programmed by PK via a jtag2UPDI interface - I use an Arduino UNO with the jtag2updi code on it as a programmer for the AVR4809, but any updi programmer will do if ever the contoller needs reprogramming.
The software is on github here.

AVR4809 layout:
look at the markdown below to add a link to a SS in the assets folder
[Link to Excel Spreadsheet](./Assets/mydata.xlsx)




return to [[Observatory Home]] home page