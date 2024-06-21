# SAFEMOVE_CHECK_HOME

1. The robot checks if it is in the home position and whether the door components are ready.
2. If a worker indicates a part is ready on the left side:
	1. The robot scans the left side for any workers.
	2. It waits until the scanning process is complete.
	3. Calls AA_PREPOSLH program to turn to the left side
3. If a worker indicates a part is ready on the right side:
	1. The robot scans the right side for any workers.
	2. It waits until the scanning process is complete.
	3. It calls the AA_PREPOSRH program to turn to the right side.
4. If parts are ready on both sides, the robot prioritizes the left side processing.
5. If no parts are ready, the robot checks again from the beginning.

# SAFEMOVE_CHECK_LEFT

1. The robot checks if it is in the pre-position for the left-hand side (LH) and if the left-hand side is not currently being processed.
2. If both conditions are true:
	1. The robot scans the environment for any workers.
	2. It waits until the scanning process is complete.
	3. Calls AA_HOME program to turn back to home position.

# SAFEMOVE_CHECK_RIGHT

1. The robot checks if it is in the pre-position for the right-hand side (RH) and if the right-hand side is not currently being processed.
2. If both conditions are true:
	1. The robot scans the environment for any workers.
	2. It waits until the scanning process is complete.
	3. Calls AA_HOME program to turn back to home position.

# ISRA_MAIN_ZAVIER

1. The robot checks if its in the home position:
	1. If not, it moves to the home position
2. Calls SAFEMOVE_CHECK_HOME program to safely move to the left or right side.
3. The robot checks if it is in the pre-position for the left-hand side (LH) and a part is ready on the left side:
	1. If both conditions are met, it calls ISRA_LH_SCREWING program to start the screwing process on the left side.
4. If the conditions for the left side are not met, it checks if it is in the pre-position for the right-hand side (RH) and a part is ready on the right side:
	1. If both conditions are met, it calls ISRA_RH_SCREWING program to start the screwing process on the right side.
5. If neither side is ready, the robot loops back to the beginning of the main loop.
6. After the screwing process, the robot calls SAFEMOVE_CHECK_LEFT or SAFEMOVE_CHECK_RIGHT program to safely move back to home position if it was working on the left or right side.
7. The robot repeat the process.


