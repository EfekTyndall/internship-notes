# Teach Pendant Programs

- **`AA_HOME`:** Move robot tool to Home position using joint motion
- **`AA_PREPOSLH`:** Move robot tool to left hand pre position using joint motion
- **`AA_PREPOSRH`:** Move robot tool to right hand pre position using joint motion
- **`ISRA_CELL_INIT`:** Initialize I/O and parameters
- **`ISRA_LH_SCREWING`:** Left hand screwing process
- **`ISRA_RH_SCREWING`:** Right hand screwing process
- **`ISRA_MAIN_ZAVIER`:** Main program
- **`SAFEMOVE_CHECK_HOME`:**
- **`SAFEMOVE_CHECK_LEFT`:** 
- **`SAFEMOVE_CHECK_RIGHT`:**

### `AA_HOME`

#### Algorithm

1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Home Position Movement:**
    - Execute a joint motion command to move the robot to the home position, defined in the respective position register ``PR[]``.

### `AA_PREPOSLH`

#### Algorithm

1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Left Hand Pre-Position Movement:**
    - Execute a joint motion command to move the robot to left hand pre-position, defined in the respective position register ``PR[8:Home_left_corr]``.

### `AA_PREPOSRH`

#### Algorithm

1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Right Hand Pre-Position Movement:**
    - Execute a joint motion command to move the robot to right hand pre-position, defined in the respective position register ``PR[10:Home_Right]``.

### `ISRA_CELL_INIT`

#### Algorithm

1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Payload Initialization:**
	- Set payload to 1, indicating the screwing spindle.
4. **Digital Output Adjustments:**
	- Deactivate the left-hand process indicator (`DO[]`).
	- Deactivate the right-hand process indicator (`DO[]`).
	- Turn off the left-hand rotation signal (`DO[]`).
	- Turn off the right-hand rotation signal (`DO[]`).
	- Activate the left fixture's open state (`DO[]`).
	- Activate the right fixture's open state (`DO[]`).
5. **Timer Resets:**
	- Clear `TIMER[5]` to its initial state.
	- Clear `TIMER[6]` to its initial state.

1. Initialize the tool frame number to `3` (Camera).
2. Initialize the user frame number to `0` (World/robot base coordinate).
3. Initialize payload number to `1` (Screwing spindle).
4. Set digital output status for left-hand in-process (`DO[]`) to `OFF`.
5. Set digital output status for right-hand in-process (`DO[]`) to `OFF`.
6.  Set digital output status for turn to left-hand (`DO[]`) to `OFF`.
7. Set digital output status for turn to right-hand (`DO[]`) to `OFF`.
8. Set digital output status for left fixture open (`DO[]`) to `ON`.
9. Set digital output status for right fixture open (`DO[]`) to `ON`.
10. Reset `TIMER[5]`.
11. Reset `TIMER[6]`.

### `ISRA_LH_SCREWING`

#### Algorithm

1. **Initialization:**
	- **Set Frame and Tool Configuration:**
		- User Frame is set to 40 (left fixture).
		- Tool configuration is set to 3 (Camera).
	- **Initialize Tact Time Counter:**
		- The tact time counter ``TIMER[1]`` is reset to start timing the operation.
	- **Activate Process Bit:**
		- Digital Output 4 ``DO[4:LH In Process]`` ist toggled ON, indicating the left hand screwing process has started.
	- **Initialize Atlas Copco Modes:**
		- Flush Atlas Copco system settings.
		- Execute `CALL ATLAS` commands for system setup.
	- **Set Start Point:**
		- Set screw number ``R[22:AC_ScrewNumber]`` to 11 for the first screw operation.

2. **Positioning and Movement:**
	- **Assign Robot Position:**
		- Assign robot's new position ``PR[60:newpos]`` to the coordinates in ``PR[R[22]]``, corresponding to the first screw.
	- **Pose Adjustment Based on Screw Number:**
		- Prepare specific poses for each screw number (11-18) using Atlas Copco commands.
	- **Collision Avoidance Strategy:**
		- Apply a 150mm Z-axis offset for screw numbers 13 and 18 to avoid collisions.
		- Use a 50mm Z-axis offset for all other screws.
		- Offset are assigned to ``PR[31:Temp_prepos150mm]``

3. **Measuring Sequence:**
	- **Pre-Measurement Movement:**
		- Move the robot to ``PR[60]``, incorporating the tool offset from ``PR[31]``.
	- **Tool and Measurement Setup:**
		- Execute ``CALL ATLAS`` commands for tool interaction, screw requests, and ISRA system measurements.
	- **Pneumatic Levers Management:**
		- Open pneumatic lever for screw number ``R[22]`` 15 by toggling `DO[101]` to ON.
		- Close pneumatic lever for screw number ``R[22]`` 17 by toggling `DO[101]` to OFF, followed by a safety wait period.
	- **Measurement Positioning:**
		- Move the robot to the measurement position ``PR[60]``.
	- **Measurement and Data Acquisition:**
		- Execute ``CALL ATLAS`` commands to initiate position measurement and update ``PR[60]`` with the results.

4. **Tightening Sequence:**
	- **Measurement and Tool Preparation:**
		- Execute `CALL ATLAS` command to retrieve measurement results.
		- Switch tool configuration to 4 for torque application.
	- **Tightening Position Adjustment:**
		- Update x and y coordinates in ``PR[60]`` for precise alignment based on ISRA data.
	- **Collision Avoidance Precaution:**
		- Move to an intermediate position ``PR[2]`` for clearance, especially critical for screw number 18.
	- **Approach Screw Position:**
		- Move towards the screw position ``PR[60]``, considering the tool offset from ``PR[30]``.
	- **Sensor Management:**
		- Deactivate the feeder Sensor by toggling `DO[70]` to ON.
	- **Final Tightening Positioning:**
		- Move to the exact screw position ``PR[60]`` for tightening process.
	- **Tightening Execution:**
	    - Execute ``CALL ATLAS`` commands to confirm screw readiness, start tightening, monitor the process, and advance the head stroke.
	- **Post-Tightening Procedures:**
	    - Execute ``CALL ATLAS`` commands to verify tightening completion and retract the head stroke.
	    - Move the robot back to ``PR[60]``, incorporating the tool offset from ``PR[31]``.
	- **Sensor Reactivation and Operation Confirmation:**
	    - Reactivate the feeder sensor by toggling `DO[70]` to OFF.
	    - Execute ``CALL ATLAS`` commands to confirm the successful tightening and head stroke retraction.
	- **Screw Number Update:**
	    - Increment the screw number  by 1 ``R[22:AC_ScrewNumber]`` and loop back to step 2 (Positioning and Movement ) for the next screw if within range of screw numbers.
5. **Completion:**
	- **Return to Pre-Position:**
	    - The robot moves to a pre-position ``PR[8]``
	- **Pneumatic Lever Management:**
	    - Open pneumatic lever by toggling `DO[101]` to ON.
	- **Deactivate Process Bit:**
	    - Digital Output 4 ``DO[4:LH In Process]`` ist toggled OFF, indicating the left hand screwing process has stopped.
	- **Stop Tact Timer:**
	    - The tact time counter ``TIMER[1]`` is stopped, marking the end of the operation.

### `ISRA_RH_SCREWING`

#### Algorithm

1. **Initialization:**
	- **Set Frame and Tool Configuration:**
		- User Frame is set to 45 (right fixture).
		- Tool configuration is set to 3 (Camera).
	- **Initialize Tact Time Counter:**
		- The tact time counter ``TIMER[1]`` is reset to start timing the operation.
	- **Activate Process Bit:**
		- Digital Output 4 ``DO[5:RH In Process]`` ist toggled ON, indicating the right hand screwing process has started.
	- **Initialize Atlas Copco Modes:**
		- Flush Atlas Copco system settings.
		- Execute `CALL ATLAS` commands for system setup.
	- **Set Start Point:**
		- Set screw number ``R[22:AC_ScrewNumber]`` to 21 for the first screw operation.

2. **Positioning and Movement:**
	- **Assign Robot Position:**
		- Assign robot's new position ``PR[60:newpos]`` to the coordinates in ``PR[R[22]]``, corresponding to the first screw.
	- **Pose Adjustment Based on Screw Number:**
		- Prepare specific poses for each screw number (21-28) using Atlas Copco commands.
	- **Collision Avoidance Strategy:**
		- Apply a 150mm Z-axis offset for screw numbers 23 and 28 to avoid collisions.
		- Use a 50mm Z-axis offset for all other screws.
		- Offset are assigned to ``PR[31:Temp_prepos150mm]``

3. **Measuring Sequence:**
	- **Pre-Measurement Movement:**
		- Move the robot to ``PR[60]``, incorporating the tool offset from ``PR[31]``.
	- **Tool and Measurement Setup:**
		- Execute ``CALL ATLAS`` commands for tool interaction, screw requests, and ISRA system measurements.
	- **Pneumatic Levers Management:**
		- Open pneumatic lever for screw number ``R[22]`` 25 by toggling `DO[103]` to ON.
		- Close pneumatic lever for screw number ``R[22]`` 27 by toggling `DO[103]` to OFF, followed by a safety wait period.
	- **Measurement Positioning:**
		- Move the robot to the measurement position ``PR[60]``.
	- **Measurement and Data Acquisition:**
		- Execute ``CALL ATLAS`` commands to initiate position measurement and update ``PR[60]`` with the results.

4. **Tightening Sequence:**
	- **Measurement and Tool Preparation:**
		- Execute `CALL ATLAS` command to retrieve measurement results.
		- Switch tool configuration to 4 for torque application.
	- **Tightening Position Adjustment:**
		- Update x and y coordinates in ``PR[60]`` for precise alignment based on ISRA data.
	- **Collision Avoidance Precaution:**
		- Move to an intermediate position ``PR[1]`` for clearance, especially critical for screw number 28.
	- **Approach Screw Position:**
		- Move towards the screw position ``PR[60]``, considering the tool offset from ``PR[30]``.
	- **Sensor Management:**
		- Deactivate the feeder Sensor by toggling `DO[70]` to ON.
	- **Final Tightening Positioning:**
		- Move to the exact screw position ``PR[60]`` for tightening process.
	- **Tightening Execution:**
	    - Execute ``CALL ATLAS`` commands to confirm screw readiness, start tightening, monitor the process, and advance the head stroke.
	- **Post-Tightening Procedures:**
	    - Execute ``CALL ATLAS`` commands to verify tightening completion and retract the head stroke.
	    - Move the robot back to ``PR[60]``, incorporating the tool offset from ``PR[31]``.
	- **Sensor Reactivation and Operation Confirmation:**
	    - Reactivate the feeder sensor by toggling `DO[70]` to OFF.
	    - Execute ``CALL ATLAS`` commands to confirm the successful tightening and head stroke retraction.
	- **Screw Number Update:**
	    - Increment the screw number  by 1 ``R[22:AC_ScrewNumber]`` and loop back to step 2 (Positioning and Movement ) for the next screw if within range of screw numbers.
5. **Completion:**
	- **Return to Pre-Position:**
	    - The robot moves to a pre-position ``PR[10]``
	- **Pneumatic Lever Management:**
	    - Open pneumatic lever by toggling `DO[103]` to ON.
	- **Deactivate Process Bit:**
	    - Digital Output 5 ``DO[5:RH In Process]`` ist toggled OFF, indicating the left hand screwing process has stopped.
	- **Stop Tact Timer:**
	    - The tact time counter ``TIMER[1]`` is stopped, marking the end of the operation.

### `ISRA_MAIN_ZAVIER`

#### Algorithm

1. Initialize counter as `0`.
2. **For** counter from `0` to `2`:
    1. Call program `ISRA_CELL_INIT` to initialize I/O and parameters.
    2. **If** the robot is not at the home position:
        - Call program `AA_HOME` to move the robot to the home position.
    3. Start the `TIMER[5]`.
    4. Call program `SAFEMOVE_CHECK_HOME` to scan the environment for safety and move to pre-position left or pre-position right.
    5. Change to fast override speed.
    6. **If** the robot is at pre-position left and worker confirms the left-hand process:
        - Call program `ISRA_LH_SCREWING` to start the left-hand screwing process.
    **Else If** the robot is at pre-position right and worker confirms the right-hand process:
        - Call program `ISRA_RH_SCREWING` to start the right-hand screwing process.
    **Else**:
        - Jump to label `1`.
    7. **If** the robot is at pre-position left:
        - Call program `SAFEMOVE_CHECK_LEFT` to scan the environment for safety and move to home.
    **Else If** the robot is at pre-position right:
        - Call program `SAFEMOVE_CHECK_RIGHT` to scan the environment for safety and move to home.
    8. Label `1`:
        - Stop `TIMER[5]`.
        - Increment the counter by one.
3. **End for loop**.



2. **Testing the program for the left fixture `ISRA_LH_SCREWING`:**
	- This program is already exist, it just need to be tested if everything work as it intended.
	- An offset point between screw points 17 and 18 also need to be included:
		- **Line 153: `J PR[2:Offset_Z_PR18lh] 100% FINE`**
	- What to be paid attention on:
		- Are the tool and User Frame (in this case User Frame 40) are being set correctly?
		- Is the robot moving to each point in the right sequence (from screw 11 to 18)?
		- Can the camera detect each screwing points correctly?
		- Is the screwing process for each points successful?
		- Are there any collision, when moving from one point to another?
		- Is the screw feeding process to the spindle successful?
		- Are there any error or warning?
	- If any of the points above occurs, then it needs to be fix before advancing to the next step
3. **Creating the program for the right fixture `ISRA_RH_SCREWING`:**
	- Because the same principle apply to the other fixture, `ISRA_LH_SCREWING` can be copied into a new program `ISRA_RH_SCREWING`.
	- A couple of thing in `ISRA_RH_SCREWING` needs to be modified first like:
		- Set the User Frame to 45.
		- Change the used position registers (PR[11] - PR[18]) to their corresponding counterparts (PR[21] - PR[28]).
		- Change the product IDs (11 - 18) to their corresponding counterparts (21- 28).
		- An offset point between screw points 17 and 18 also need to be included:
			- **Line 153: `J PR[1:Offset_Z_PR18rh] 100% FINE
	- If everything done correctly, the program should work as well for the right side.
	- Keep in mind to test the program an look for any issues and fix them before advancing to the next step.
4. **Implementing the programs in the main program `ISRA_MAIN_ZAVIER`:**
	- (Still on progress)


If the values received are a correction of the TCP, the robot should move to the coordinates as an offset from the target position. For each screwing operation, the robot first moves to the image acquisition position and takes an image for approximately one second. The calculated correction values according to the tool coordinate system (x and y values) are added to the target position of the screw connection. The robot then moves to the new position and finally in the positive tool Z direction in order to screw it together.

