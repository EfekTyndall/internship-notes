- Unstable/ lost connection between the robot controller and Mirai controller
	1. First Solution: Reinitialize connection between Mirai controller and FANUC controller.
			- On the FANUC Teach Pendant select **MENU>SETUP>KAREL Config**
			- Select **MIRAIMON** and press **OPRT** then **ABORT** and press **YES** to confirm selection
			- Select **MIRAIMON** and press **OPRT** then **RUN** and press **YES** to confirm selection
	2. Second Method: Restart both Mirai controller and FANUC controller
			- Cold start both the robot controller and Mirai controller by switching them off and on manually though their physical switch 
			- Connect the the training tablet and Mirai controller. See [[How to Connect Training Tablet to The Mirai Controller]]
- Training tablet doesn't have connection to the Mirai controller
	- Make sure that the training tablet connected with the Mirai Controller through Wi-Fi. See [[How to Connect Training Tablet to The Mirai Controller]]