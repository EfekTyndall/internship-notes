# SAFEMOVE_CHECK_HOME

1. Check to turn **left** or check to turn **right**.
	- Turn **left** condition:
		- At home position
		- werker quittieren links ON
		- werker quittieren rechts OFF
		- IF TRUE:
			- Turn to LH ON = Safety Scan LH Active
				- IF detect something inside the detection range, turn OFF disabling signal for CSC (CSC Enabled)
				- ELSE CSC disabling signal should be turned ON all of the time
			- TIMER[6] START
			- WAIT .40(sec)
			- CALL AA_PREPOSLH
			- Turn to LH OFF = Safety Scan LH Deactivate
		- ELSE:
	- Turn **right** condition:
		- At home position
		- werker quittieren links OFF
		- werker quittieren rechts ON
		- IF TRUE:
			- Turn to RH ON = Safety Scan RH Active
				- IF detect something inside the detection range, turn OFF disabling signal for CSC (CSC Enabled)
				- ELSE CSC disabling signal should be turned ON all of the time
			- TIMER START
			- WAIT .40(sec)
			- CALL AA_PREPOSRH
			- Turn to RH ON = Safety Scan RH Deactivate
		- ELSE:
	- Other conditions:
		- At home position
		- werker quittieren links OFF
		- werker quittieren rechts OFF
		- IF TRUE:
			- Wait .50(sec)
			- Back to Nr. 1 (check to turn **left** or check to turn **right**)
		- ELSE:
	- Other conditions:
		- At home position
		- werker quittieren links ON
		- werker quittieren rechts OFF
		- IF TRUE:
			- Wait .50(sec)
			- Start to turn **left** (turn left conditions) and after that process is finished, turn to **right** (turn right conditions)
- END

# SAFEMOVE_CHECK_LEFT

1. Check if it safe to turn **right**
	- Turn **right** conditions:
		- At Pre-position LH
		- LH In Process OFF
		- IF TRUE:
			- Turn to RH ON = Safety Scan RH Active
			- IF detect something inside the detection range, turn OFF disabling signal for CSC (CSC Enabled)
			- ELSE CSC disabling signal should be turned ON all of the time
			- WAIT .40(sec)
			- CALL AA_HOME
			- Turn to RH OFF = Safety Scan RH Deactivate
			- TIMER[6] STOP
2. END

# SAFEMOVE_CHECK_RIGHT

1. Check if it safe to turn **left**
	- Turn **left** conditions:
		- At Pre-position RH
		- RH In Process OFF
		- IF TRUE:
			- Turn to LH ON = Safety Scan RH Active
			- IF detect something inside the detection range, turn OFF disabling signal for CSC (CSC Enabled)
			- ELSE CSC disabling signal should be turned ON all of the time
			- WAIT .40(sec)
			- CALL AA_HOME
			- Turn to LH OFF = Safety Scan RH Deactivate
			- TIMER[6] STOP
2. END

# Notes

- Scan is active only while DO[1] is on. Need to be change, so scanning is always active during turning.
- 