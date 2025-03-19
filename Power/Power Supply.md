Everything in the observatory is powered by 12 v batteries.

This buck boost [converter](https://kunkune.co.uk/shop/dc-to-dc-converters/250w-10a-boost-converter-step-up-module-8-48v-to-12-50v-adjustable/) has been purchased and it operates at 160 KHz so ask AI how to create an LC filter to suppress any noise problems there might be. Using a metal case is also a good idea to stop radiated noise interference.

Battery Voltage monitoring

See [here](https://www.re-innovation.co.uk/docs/accurate-voltage-measurment/)

basic diagram from the link above:

![[Voltage divider circuit.png|500x600]]

The main battery which powers the mount, camera, focuser and rotator is connected to the Photonic Universe solar charge controller. So that battery gets charge during daylight hours. An equipment test in March 2025 made me decide to add in a buck boost converter to stabilise the battery voltage at say 13.5 volts. I hope this will stabilise the equipment, especially cameras, but also the minimum voltage requirement for the Sitech Controller is 11.5 volts - this is an absolute minimum and in the test mentioned above, Sitech's Servoconfig software indicated the voltage at the controller to be 11.7, this was with a battery that had been solar charged for many days.

The other battery for the dome drive is connected to a buck boost device to convert the voltage from 12v to 24 V this is connected to the [[DM860I Stepper controller]] . The battery doesn't get charged directly, so the options for charging are take it home (they weigh a ton) or connect it to the Photonic Universe solar charger. This can only be connected to one battery at a time.





return to [[Observatory Home]] home page
