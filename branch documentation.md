[[Observatory Home]]

**Control Box & Monitoring branches**
**Control Box**
The current in use branch is master and this has been updated and tested at home on the CB simulator with encoder. It can be uploaded to the Observatory Control box in conjunction with the updated Monitor software (lenovo)

The current branches in use  for testing new code are:
- test-AI-direction-and-countdown-to-target
	- this is still based on moving until the encoder value reaches the target value (the original system).
- merged -test-master-and degrees
	- this is the new idea of calculating the number of motor steps required to reach the target azimuth. Once tested, the branch below can be deleted. Or merge this branch into drive using degrees (done 18-12-25)
-  drive using degrees

**Monitor program**
the master branch is current and has been updated. It can be updated on the observatory PC in conjunction with to control box master code
