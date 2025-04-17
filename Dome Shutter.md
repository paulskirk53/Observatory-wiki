The dome shutter is controlled by an arduino Mega 2560 which has two interfaces,  bluetooth and the normal serial connection.

Bluetooth
This connection handles all the ASCOM commands which are 
- OS# - Open Shutter
- CS# - Close Shutter
- SS# - Shutter status

The Shutter control box communicates via an HC05 pair of bluetooth transmiter / receivers which are paired. The other one of the pair is in the [[Master Radio control box]].

Pairing the Bluetooth devices can be found here [[Bluetooth]]




return to [[Observatory Home]] home page