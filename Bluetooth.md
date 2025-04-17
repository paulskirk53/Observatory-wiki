Archived - HC05 Master- SLave Configuration

Now maintained on wiki JS as of November 2023

 
## Overview

This text describes the process for setting up two HC05 devices for bi directional text transmission via the Bluetooth protocol. These are brilliant devices, so easy to use. 
- Note that master and slave is about address linking and pairing and does not constrain one or other devices to only send or only receive. Both Tx and Rx Comms are bi directional. 

- The procedure below was followed with two HC05 devices on 3/12/21 and the devices attached to two different computers, one with mega2560 and another with Arduino UNO. Messages successfully sent and received from both devices.

## Good resources

#### Showing how to connect and configure as master and slave

youtube vid:

[https://www.youtube.com/watch?v=BXXAcFOTnBo](https://www.youtube.com/watch?v=BXXAcFOTnBo)

#### Straightforward send / receive arduino code

See my github pages

#### HC05 datasheet

[https://components101.com/sites/default/files/component_datasheet/HC-05%20Datasheet.pdf](https://components101.com/sites/default/files/component_datasheet/HC-05%20Datasheet.pdf)

## TO CONFIGURE SLAVE

### Important

Note that to configure a board Tx and Rx pins are NOT cross connected so Tx->Tx and Rx -> Rx use TX0 and RX0 (i.e the USB interface on Arduino)

Mark the board as S (for slave) with a marker pen. Once configuration is over, Tx and Rx need to be pulled out of the MCU and swapped to their normal crossed roles.

### Entering config mode

Note that to enter the config mode, the reset button on the HC05 must be held down while the device is powered up. The LED blink mode is slow ~ 1 hz

### Also Note the baud rate

For Configuration, the baud rate is predefined and therefore the arduino serial monitor must be set to 38400 for the AT command set to transmit and receive. The normal mode of operation of the device i.e. when it is not in config mode, uses baud rate 9600.
### Sequence of commands to configure SLAVE

AT
AT+ROLE=0      // SET TO SLAVE
AT+ROLE?        // TO CONFIRM ROLE HAS BEEN SET AS 0
AT+ADDR?       // GET THE SLAVE ADDRESS - For our test it’s 2017,10,94951 note change the colons to commas for pasting into MASTER later

That’s the end of process for SLAVE config

To query the baud rate and comms params use AT+UART?
I have not changed the slave baud rate.
See useful config commands [here](https://docs.google.com/document/d/1PcaVwZz6y6u536EqB1_0mtG2qM2KPeTKPuQKpwwnAH0/edit#heading=h.yxggq4lgtrl8)

## TO CONFIGURE MASTER

Same pin config note as SLAVE and the same method to enter config mode - see above.
### Sequence of commands to configure MASTER

AT   //COMMS TEST - SHOULD GET BACK OK
AT+ROLE?    // TO CHECK ROLE - 1= MASTER, 0 = SLAVE
AT+ROLE=1
AT+CMODE?  //CHECK the addressing mode 1= connect to any address, 0 =  just the one, so set CMODE=0
AT+CMODE=0
AT+BIND=2017,10,94951    //THE slave’s address from the slave config - note commas

Note default baud is 9600, 1 stop, no parity can check with AT+UART?
Note default password is 1234 - I have not changed it

That’s the end of the configuration. Note that the AT commands seem to work in lower case too.

## To test the devices

Use another Arduino and:
Remove the 3.3V EN pin

Cross the Tx and Rx lines from HC05 to arduino as they now transmit/ receive across the two BT devices.

Run a test sketch which validates bi directional comms:

- MASTER  receives a text string from the MASTER sermon and transmits it to the SLAVE which prints it on SLAVE Sermon - see github here
    
- SLAVE receives a text string from the SLAVE sermon and transmits it to the MASTER which prints it on MASTER Sermon
- Check the device range
## Useful Config Commands HC-05

AT+UART=9600,1,0
AT+CMODE? SET TO 1 FOR CONNECT TO ANY DEVICE
AT+ROLE? SET TO 1 FOR MASTER ROLE, ZERO FOR SLAVE
AT+STATE? TO CHECK WHETHER INITIALISED, PAIRED ETC
AT+RNAME? TO GET NAME OF REMOTE BT DEVICE
AT+NAME? TO GET NAME OF THE HC05 MASTER DEVICE NEEDS 5V
ON THE EN PIN
AT+ORGL RESTORES FACTORY SETTINGS
AT+RESET SWITCH OUT OF AT MODE WITHOUT DISCONNECTING PWR
AT+PSWD? ENQUIRE PASSWORD 

  
  
Old stuff from 2018 below:

HC05 and 6

HC05

  

AT+UART=9600,1,0 WORKED WITH THE hc05 SET AS SLAVE

  

tested with Arduino IDE serial monitor as com5

sent various text to acer termite

  

ACER Termite settings - COM3 9600, 1 stop, no parity

  

need to investigate setting as master and connection to HC06 slave

  
  

HC06

2-2-18 currently receiving messages printed from arduino - these are displayed on com5 on Acer termite

  

HC06

  

Tried this on the HC05 board to do a comm send and receive test and it can receive from the boiler pc arduino ide com5 to acer termite and transmit from termite via com5 to boiler PC arduino ide so the bluetooth recive from acer works

  

WHAT IS KNOWN

The orange circuit is wired correctly as the HC06 works fine in 2 way comms acer to PC

THE HC-05 WORKS IN TWO WAY COMMS ON THE ORANGE BOARD, but not in MASTER mode  the acer can’t find it and i suspect that is what MASTER means - the MASTER does the connecting and pairing


[[Observatory Home]]

