I have employed Solid State relays of the type SS40DD (*solid State, 40 Amp DC to DC* ) the device datasheet never came with the devices I bought so I've downloaded it and included as part of this wiki here [[Electronic switches]]

The device is specified for up to 40 Amps DC - in my view it would get nowhere near that kind of performance, but our dome drive stepper motors only draw 5 Amps Maximum (specified by the dip switches on the [[DM860I Stepper controller]] ), so the SS40DD is used well within its limits.

The switches are controlled by an output from the electronic control boxes - the software I wrote for these looks to keep power use to a minimum, so an output from the [[Control Boxes]]  to the SS40DD gate is made when the motor is needed to run. When the motor target position has been reached, the SS40DD is switched off which cuts power to the stepper motor.


Click to go back to [[Observatory Home]]