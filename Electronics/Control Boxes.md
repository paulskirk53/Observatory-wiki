One control box services the [[Sitech Telescope Controller]] and [[Dome  Automation]] and another one services the [[Dome Shutter]] open / close function.

Picture of Dome control box:


**Function of the box**
The box hosts an AVR4809 microcontroller which is custom programmed by PK via a jtag2UPDI interface - I use an Arduino UNO with the jtag2updi code on it as a programmer for the AVR4809, but any updi programmer will do if ever the contoller needs reprogramming.
The software is on github here.

AVR4809 layout:
look at the markdown below to add a link to a SS in the assets folder
[Link to Excel Spreadsheet]("C:\Observatory\Observatory wiki\Assetscontrol_box_pinout.xlsx")

AVR4809 40 pin variant [pinout](https://github.com/MCUdude/MegaCoreX?tab=readme-ov-file) on Megacorex website



Archived - Control Box 

Now maintained in Obsidian as of April 2025

## Update September 2023. 

The whole of this document remains valid. This update refers to a software branch called ‘drive-using-degrees’ which at present is a development branch to explore the idea of moving away from using non intuitive ‘steps’ which is motor related, to the idea of using target degrees to define the steps required by stepper.moveto(). So the dome revolution of 360 degrees will be a certain number of steps, say stepsForOne Rotation and therefore a slew to position x degrees will require (stepsForOne Rotation /360 *x ) steps to be moved. stepsForOne Rotation / 360 is a constant, so calculate that in setup()

The advantage of this approach

- Acceleration and deceleration happens automatically with the stepper library stepper.moveto() commands
    
- No need for ‘dothedeceleration routine
   - No need for withinFiveDegrees routine
- The code is much more intuitive, so maintenance should be easier
    
**The disadvantage** of this approach

- The code will need extensive testing via a working model stepper and encoder
- Development time is required, but it can be done in parallel with a working system, no rush to change.
## Introduction July 2023

For Dome control - the one chip implementation including stepper and encoder modelled as one MCU, replaces the former ‘integrated control’ and now uses only two USB cables, one for all ASCOM data comms and one for Monitoring data comms. The box is enclosed, but a heartbeat LED inside flashes at 20 second intervals when code is running.
## Programming

The control box’s AVR4809 chip is programmed using an Arduino Uno as a jtag2updi programmer via Platformio see [[Programming the control box with jtag2updi]] The control box has two banana sockets (Gnd/ UPDI ) for programming connections. 

## Testing

The control box has been extensively tested during June and July ‘23. Installed in the observatory in late July, tests of all ASCOM connections except the Sitech controller were acceptable - images taken on both cameras simultaneously, monitoring program working to show slews, encoder azimuth etc. **Working well April 2025**


    
    ### Modelling

Table 1 below describes the pins and functions. The spreadsheet [here](https://docs.google.com/spreadsheets/u/0/d/1RLFg1F5WgP97Ck7IOUJbF8Lhts_1J4T0fl-OKxMCbDc/edit) describes how the chip is modelled.

**Table 1**

|   |   |   |   |
|---|---|---|---|
|Function|4809 <br><br>arduino <br><br>pin|Multi way<br><br>Conn’ pin|Notes|
|Motor Step control|11|1|The connector blocks are 4 pin multi way|
|Motor DIR control|10|2||
|Dome Power MOSFET Gate|2|3||
|Camera power MOSFET gate|6|4|Currently a banana plug|
|Hall sensor - for:<br><br>- West synching the dome <br><br>- park position  <br><br>- homing|29|5|Hall sensor was scrapped|
|||||
|Encoder A Phase|4|6||
|Encoder B Phase|5|7||
|5V power Out|n/a|8|encoder,  DM860I , Hall Sensor|
|ground||Banana|encoder,  DM860I , Hall Sensor|
|UPDI programmer||Banana||
|Updi Gnd||Banana||
|5V Power out||Banana|Used to hold DM860I pins high|

## Box Pinout

1 Stepper drive
2 Stepper Direction
3 Dome power MOSFET
4 Camera/ Rotator MOSFET
5 Dome Sync
6 Encoder A
7 Encoder B
8 5V Power out

## Encoder details

Note this is one type and may not be the one in use in the observatory we use 600 ticks per rev. More is fine, but code will need adjustment in control box.

See [here](https://sharvielectronics.com/product/e38s6g5-600b-g24n-photoelectric-incremental-rotary-encoder/)

## Software

See github for control box software

### EEPROM

[This](https://teslabs.com/openplayer/docs/docs/prognotes/EEPROM%20Tutorial.pdf) is good for EEPROM read / write

  Appendix 1 - how the former integrated box was remodelled. See [here](https://docs.google.com/document/d/1atwApJ2Rd58Dv2i7JQ5XCE-euWsRQEW1fJAKeIhEzwI/edit)



return to [[Observatory Home]] home page