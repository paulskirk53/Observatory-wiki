 12 v batteries are the base source of power.

The archived section below shows how power was supplied prior to summer 2025. Because the camera could not be made to work from a battery supply (you'd think it would be the ultimate stable supply), I installed the Victron Inverter which powers th



**Archived:**
This buck boost [converter](https://kunkune.co.uk/shop/dc-to-dc-converters/250w-10a-boost-converter-step-up-module-8-48v-to-12-50v-adjustable/)  operates at a frequency of 160 KHz so using a capacitor across the o/p terminals will filter any noise problems there might be. Using a metal case is also a good idea to stop radiated noise interference. The leads from the main battery feed into a wooden box which houses the boost device. There is one input (from the 12 V battery) and three outputs. The boost device has a potentiometer inside which allows adjustment of the output voltage. Only adjust this **if the devices are not connected** as over voltage is easily applied and the devices will be destroyed.

Another boost device I used in the past has a current rating of 5A. 
I gave copilot the device number and it returned this:
Yes, the device with the number **YH11057D** appears to be a **DC-DC boost converter**
It is designed to step up a lower DC voltage to a higher DC voltage. For example, it can take an input voltage range of **6-32V** and output a voltage range of **6-42V**, with a maximum current of **5A**

**Current demand**
The devices in the observatory draw 4.5 A , as measured with a clamp meter, when the monitor is on and 4 A when the monitor is off.
The devices powered are Sitech controller, H814c and Lodestar Cameras, Microtouch focuser, Pyxis rotator, USB hub, Intel NUC & screen, AVR microcontrollers via USB hub

**Battery Voltage monitoring**
There is no voltage monitoring at present, but see [here](https://www.re-innovation.co.uk/docs/accurate-voltage-measurment/)

**The resistor values for our system are R1 = 18k and R2 = 10K** - see diagram below

basic voltage divider diagram from the link above:

![[Voltage divider circuit.png|500x600]]

The main battery which powers all the equipment mentioned above is connected to the Photonic Universe solar charge controller. So that battery gets charge during daylight hours. An equipment test in March 2025 prompted me to add in a buck boost converter to stabilise the battery voltage at say 13.5 volts. I hope this will stabilise the equipment, especially cameras, but also the minimum voltage requirement for the Sitech Controller is 11.5 volts - this is an absolute minimum and in the test mentioned above, Sitech's Servoconfig software indicated the voltage at the controller to be 11.7, this was with a battery that had been solar charged for many days.

See [[Programming useful snips]] for some sample code to obtain the supply voltage value using a voltage divider and arduino analog pin.



return to [[Observatory Home]] home page
