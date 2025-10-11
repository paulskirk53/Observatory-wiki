[[Observatory Home]]

22-4-2025
a better way to set the switch up if the shutter returns CONNECTED to the Master radio request for connection, set a bool BTConnected= true;

what we want to achieve is if the BT is not working the master radio can return shutter 'open' so that the dome can connect and imaging can continue.

So in the if clause which tests if the dome driver has requested shutter status, test if BTConnected=false and if so sendviascom open



SAT 15-3-25
Shutter code testing
created new branched called testing to facilitate tests
1. I simulated the shutter bluetooth by naming it Serial so commands could be accepted from KB. Added a lead between pin 21 and gnd to simulate the shutter close microswitch
2. also added a openposition statement in setup in case the value read from eeprom is incorrect on the test arduino
3. The routine cjeckmotorstatus would benefit from the addition of the following in the conditio
	1. current condition is: if ((stepper.distanceToGo() == 0)
	2. new proposed condition is  if ((stepper.distanceToGo() == 0)  )&& (powerOnFlag == on) ) this would ensure the poweroff() routine is not repeatedly called when power is already off
4. I checked the status of power_pin by adding the following line in checkmotorstatus(): 
	1. Serial.println("four second check, distance to go is " + String( stepper.distanceToGo() ) + "Power state is " + String(digitalRead(power_pin))  );
5. I added the following code to signal a bluetooth connection:
	1. if (receipt.indexOf("CONNECT", 0) > -1)
         {
            masterBluetooth.print("OK#");
         }
       So there will need to be change in the master radio routine to send CONNECT# and accept the returned OK#
6. Results
	1. Apart from the item in 3.1 which needs change for efficiency sake, it all seemed to work ok. So Suspect the Bluetooth connection is not there?
	2. in the MAIN branch add in the line in item 4 and have it returned to a cable connection on Serial rather than BT, then it can be monitored on site
	3. Also ensure the openposition variable is set to say 5000. If it's a tiny value or zero, the motor will be stopped and power will go off very quickly.

## todo 15-3-2025
connect nuc at home & pull the github changes
take up the small 12 v battery, nuc kb mouse
upload programs to shutter and to master radio and check the bluetooth connection works.
install obsidian on the NUC and integrate it with Git

[[Observatory Home]]
