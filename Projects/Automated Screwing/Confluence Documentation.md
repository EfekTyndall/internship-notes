>[!SUMMARY]- Table of Contents
>- [[Confluence Documentation#Automated Screwing Robot for Truck Door Assembly - Project Documentation|Automated Screwing Robot for Truck Door Assembly - Project Documentation]]
>   - [[Confluence Documentation#1. Introduction and Objectives|1. Introduction and Objectives]]
>   - [[Confluence Documentation#2. Operational Workflow|2. Operational Workflow]]
>   - [[Confluence Documentation#3. System Components|3. System Components]]
>   - [[Confluence Documentation#4. Initial Setup|4. Initial Setup]]
>      - [[Confluence Documentation#4.1. Equipment Preparation|4.1. Equipment Preparation]]
>      - [[Confluence Documentation#4.2. Robot Configuration|4.2. Robot Configuration]]
>         - [[Confluence Documentation#4.2.1. Tool Frame Calibration|4.2.1. Tool Frame Calibration]]
>         - [[Confluence Documentation#4.2.2. User Frame Calibration|4.2.2. User Frame Calibration]]
>   - [[Confluence Documentation#5. Teaching Points|5. Teaching Points]]
>      - [[Confluence Documentation#5.1. Left Door Assembly Points|5.1. Left Door Assembly Points]]
>      - [[Confluence Documentation#5.2. Right Door Assembly Points|5.2. Right Door Assembly Points]]
>      - [[Confluence Documentation#5.3. Additional Points|5.3. Additional Points]]
>   - [[Confluence Documentation#6. ISRA Vision System Setup|6. ISRA Vision System Setup]]
>      - [[Confluence Documentation#6.1. Accessing the ISRA Vision Program|6.1. Accessing the ISRA Vision Program]]
>      - [[Confluence Documentation#6.2. Sensor Calibration|6.2. Sensor Calibration]]
>      - [[Confluence Documentation#6.3. Adding, Training and Modification of New Products for Screw Points|6.3. Adding, Training and Modification of New Products for Screw Points]]
>   - [[Confluence Documentation#7. Teach Pendant Programs|7. Teach Pendant Programs]]
>      - [[Confluence Documentation#`AA_HOME`|`AA_HOME`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`AA_PREPOSLH`|`AA_PREPOSLH`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`AA_PREPOSRH`|`AA_PREPOSRH`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`ISRA_CELL_INIT`|`ISRA_CELL_INIT`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`ISRA_LH_SCREWING`|`ISRA_LH_SCREWING`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`ISRA_RH_SCREWING`|`ISRA_RH_SCREWING`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#`ISRA_MAIN_ZAVIER`|`ISRA_MAIN_ZAVIER`]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#``SAFEMOVE_CHECK_HOME``|``SAFEMOVE_CHECK_HOME``]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#``SAFEMOVE_CHECK_LEFT``|``SAFEMOVE_CHECK_LEFT``]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#``SAFEMOVE_CHECK_RIGHT``|``SAFEMOVE_CHECK_RIGHT``]]
>         - [[Confluence Documentation#Algorithm|Algorithm]]
>      - [[Confluence Documentation#Notes:|Notes:]]
# Automated Screwing Robot for Truck Door Assembly - Project Documentation

## 1. Introduction and Objectives

This document describes the use of an automated screw fastening system to extend the assembly line for truck doors. The initiative aims to use robots to increase productivity and accuracy and ensure optimum assembly precision.

The primary objectives of this project include:
- **Improving operational efficiency:** Automating the screw fastening process to minimize manual labor, thereby shifting human resources to more cognitively demanding tasks such as logistics and quality assurance.
- **Innovating the assembly process:** Using a synthesis of robotic automation, machine vision and automated screw delivery to optimize the assembly process.
- **Safety integration:** Implementing collaborative robotics to promote a cohesive workspace where humans and machines work in tandem to ensure safety without compromising efficiency.
- **Time optimization:** Achieving a target screw fastening time of approximately 60 seconds per door, setting a benchmark for assembly speed.

## 2. Operational Workflow

The system operates on a dual-station model to maximize efficiency:
1. **Initial set-up:** Two assembly stations are positioned one of the each side of the robot unit and prepared for the screw fastening process of the truck door components.
2. **Human interaction:** Operators position and attach a door component to the designated station and initiate the screw fastening process via an activation interface.
3. **Robot execution:** Once activated, the robotic arm begins the screw fastening process, applying precision and consistency.
4. **Parallel processing:** At the same time, the operator can prepare the adjacent door at the other station, ensuring a continuous work cycle.
5. **Completion of the cycle:** After the screw fastening completed, the finished assembly is removed and the process is repeated with a new component.

## 3. System Components

- **Robot unit: FANUC CRX10iA/L collaborative robot:**

	- **Control unit:** Oversees the robot movements and sequences through a sophisticated control algorithm.
	- **Human Machine Interface (HMI):** A teach pendant provides an intuitive interface for programming and operating the system.

- **Screw Fastening and Vision System: Atlas Copco & ISRA Vision:**

	- **User interface:** The assembly control node (ACN) from Atlas Copco facilitates user interaction and system monitoring.
	- **Automation infrastructure:** An automation control box (ACB) from Atlas Copco integrates the system components for seamless communication.
	- **Visual guidance:** Machine vision technology from ISRA Vision enables the robot to analyze images in real time for precise placement of screws.

- **Screw Delivery System:**

	- **Fastening Tool**: A pneumatically driven screw spindle, complemented by an automated feeder, ensures a continuous supply of screws.

- **Safety Mechanism:**
	- **Monitoring System**: Programmable Logic Controllers (PLCs) and a network of safety sensors ensure a secure operational environment, safeguarding human operators.

## 4. Initial Setup

### 4.1. Equipment Preparation

Both the left and right side fixtures are equipped with door components. Essential tools, including the screwing spindle and ISRA Vision camera, are securely mounted onto the robot flange, ensuring they are properly positioned for the tasks at hand. The ACN is also fixed on the robot base fixture for user interaction and system monitoring.

### 4.2. Robot Configuration

Utilizing the robot's teach pendant, the robot is then configured to interact with the mounted tools and fixtures.

#### 4.2.1. Tool Frame Calibration

Initial calibration of the tool frames is essential to set precise operational parameters for the robot's tools.

- **Tool Frame 3:** Configured for the ISRA Vision Camera
	![[AC_TF_3_crop.jpg|500]]
- **Tool Frame 4:** Configured for the Screwing Spindle
	![[AC_TF_4_crop.jpg|500]]

For detailed guidance on this process, including a step-by-step tool frame calibration tutorial, please refer to [[The Tool Coordinate System (Tool Frame)]].

#### 4.2.2. User Frame Calibration

To ensure the robot operates seamlessly within its environment, calibrating user frames is a critical step. This involves defining the spatial relationships between the robot and key components in its workspace.

- **User Frame 40:** Configured for the left fixture, to align operation on the left hand door.
- **User Frame 44:** Configured for the camera calibration plate, which located on the right fixture.
- **User Frame 45:** Configured for the right fixture, to align operation on the right hand door.
	![[AC_UF_40.jpg|250]] ![[AC_UF_44.jpg|250]] ![[AC_UF_45.jpg|250]]

All user frames are calibrated in reference to Tool Frame 4 (the screwing spindle), employing the three-point method. The specific points utilized for this method are clearly marked on both fixtures, with an additional reference point (point 1.1) located on the calibration plate.

For detailed guidance on this process, including a step-by-step user frame calibration tutorial, please refer to [[The User-Defined Coordinate Systems (User Frames)]].

## 5. Teaching Points

After the calibration of tool and user frames, the next phase involves teaching the robot specific points for each screwing holes on both truck doors. Additionally, including offset points for collision avoidance informs the robot of critical areas to navigate carefully, significantly reducing the risk of collisions and ensuring operational safety.

### 5.1. Left Door Assembly Points

For the left hand side door, the points are recorded in relation to Tool Frame 4 (the screwing spindle) and User Frame 40 (left fixture). The designated points are each saved in a position registers (PR) as follows:

- **PR[11] - PR[18]**: Each point, from PR[11] to PR[18], corresponds to specific screw locations on the left-hand door, indicated as Screw_11_LH to Screw_18_LH, respectively.
- **PR[2] = Offset_Z_PR18lh**: This point provides spatial offsets to safely navigate the robot's movements between screws 17 and 18 on left side of the door, thereby avoiding any collision.
	![[AC_PR_11-18.jpg|250]] ![[AC_PR_2.jpg|250]]

### 5.2. Right Door Assembly Points

For the right hand side door, the points are recorded in relation to Tool Frame 4 (the screwing spindle) and User Frame 45 (right fixture). The designated points are each saved in a position registers (PR) as follows:

- **PR[21] - PR[28]**: Each point, from PR[21] to PR[28], corresponds to specific screw locations on the right-hand door, indicated as Screw_11_RH to Screw_18_RH, respectively.
- **PR[1] = Offset_Z_PR18rh**: This point provides spatial offsets to safely navigate the robot's movements between screws 17 and 18 on right side of the door, thereby avoiding any collision.
	![[AC_PR_21-28.jpg|250]] ![[AC_PR_1.jpg|250]]

### 5.3. Additional Points

Besides the screwing points, other additional points are taught for various purposes. These include:

- **PR[5] = calib_plate_1.1:** This point serve as a reference point for the calibration plate's coordinate system, which is located on point 1.1. The point are recorded in relation to Tool Frame 4 (the screwing spindle) and User Frame 0 (world coordinate).
	![[Calib_TCP_1.jpeg|252]] ![[AC_PR_5.jpg|210]]
## 6. ISRA Vision System Setup

The setup of the ISRA Vision System is a critical component in ensuring the precision of the automated screw fastening process. This section outlines the steps to configure the system through the Assembly Control Node (ACN).

### 6.1. Accessing the ISRA Vision Program

1. **Program Launch:**

	- Navigate to the ACN interface and use the search icon located at the bottom left of the screen. Enter "ISRA MONOxD" in the search field and execute the program.
		![[ISRA_1.png|500]]
	- The ISRA Vision program window may not appear immediately upon launching. If this occurs, locate the program log on the taskbar at the bottom of the screen and select it to bring the program window to the forefront.

2. **Administrator Login:**

	- On the landing page of the ISRA Vision program, locate and click the icon at the top right corner (the 4th from the right) to access the login panel. Enter the administrator password, which is "isra" and click "Login". It is essential to perform the subsequent steps with administrator privileges to ensure full access to necessary configurations.
		![[ISRA_2.png|500]]

3. **Activating Setup Mode:**

	- After successfully logging in as an administrator, click the button next to the login icon to access setup mode. A prompt will appear, inquiring whether to activate setup mode. Select "Yes" and confirm by clicking "OK" to proceed with the system setup.
		![[ISRA_3.png|500]]
	- After the setup mode is activated, the previous button will change it's icon.

### 6.2. Sensor Calibration

1. **Accessing Sensor Calibration Menu:**

	- After the previous steps, click the arrow icon on the top left corner of the screen.
		![[ISRA_4.png|500]]
	- Then slide the screen to the left to reveal another sets of menu on the right.
		![[ISRA_5.png|500]]
	- Under the "MONOxD sensor" click the sensor with name "Daimler Trucks".
		![[ISRA_6.png|500]]
	- The calibration menu for this sensor will then appear.

2. **Initiating Calibration:**

	- In the calibration menu select the "Calibrate Sensor" option to begin the calibration process.
		![[ISRA_7.png|500]]
	- Choose "Start Calibration Process," followed by selecting the appropriate calibration target, which in our case is the calibration plate. Confirm your selection and proceed by clicking "Next."
		![[ISRA_8.png|500]]
	- Opt for the calibration plate sized 60x60 with 10 mm marker distance. Confirm your choice by clicking "Next."
		![[ISRA_9.png|500]]

3. **Setting the Zero Point of the Calibration Plate:**

	- Utilize the teach pendant to position the robot at point 1.1 of the calibration plate (**PR[5] = calib_plate_1.1**), which aligns with the world coordinate (User Frame 0) and the screwing spindle (Tool Frame 4). This specific position will be established as the zero point for the calibration plate.
		![[Calib_TCP_1.jpeg|252]] ![[Calib_TP_1.jpg|210]]
	- Enter the x, y, z coordinates of this position into the calibration setup, ensuring they are relative to the world coordinate system (User Frame 0) and the screwing spindle (Tool Frame 4). The orientation (yaw, pitch, roll) should be set to 0 to maintain alignment with the base coordinate system. Proceed by clicking "Next."
		![[ISRA_10.png|500]]

4. **Camera Positioning:**

	- Adjust the sensor using the teach pendant to ensure the calibration pattern fully occupies the image view. Ideally, position the camera at a 30-degree angle from the calibration plate, or move to position **PR[6] = calib_plate_cam** relative to the robot base (User Frame 0) and the robot flange (Tool Frame 1). Continue by clicking "Next."
		![[Calib_TCP_2.jpeg|252]] ![[Calib_TP_2.jpg|210]]
		![[ISRA_11.png|500]]
	- On the teach pendant, switch the tool frame to 1 (robot tool flange) and the user frame to 0 (robot base). Press the POSN button on the teach pendant. Enter the position (x, y, z) and orientation (yaw, pitch, roll) into the calibration setup.  and then click "Next."
		![[Calib_TP_3.jpg|210]] ![[ISRA_12.png|500]]

5. **Finalizing Calibration:**

	- On the next step, click "Calibrate" and ensure each black circle on the calibration plate is enclosed by green boxes, indicating successful calibration. A confirmation message, "Calibration successful!" should appear. If that's not the case, each box can be moved manually to the right position. Proceed by clicking "Next."
		![[ISRA_13.png|500]]

6. **Validation:**

	- Validate the calibration by comparing the simulated image with the real-world scenario. The positions of the sensor and tool flange in the simulation should mirror those in the actual setup. Confirm by clicking "Ok."
		![[ISRA_14.png|500]]

7. **Testing Calibration:**

	- In the calibration menu select the "Test Calibration" to initiate the testing phase.
		![[ISRA_15.png|500]]
	- Click "Test Calibrate." The calibration results will be displayed beneath the image, allowing for a comprehensive assessment of the calibration's accuracy. When finished click "Cancel" to go back to the calibration menu.
		![[ISRA_16.png|500]]

### 6.3. Adding, Training and Modification of New Products for Screw Points

To enable the ISRA Vision System to accurately identify and locate each screwing point on the truck doors, new products corresponding to these points need to be added to the system and then fine-tuned its setting for optimal performance.

1. **Positioning the Robot at a Screwing Point:**

	- Before initiating the robot's movement, ensure the correct tool frame and user frame are selected. For screw points on the left fixture, use User Frame 40; for points on the right fixture, use User Frame 45. The camera (Tool Frame 3) should be the active tool frame to position the camera accurately above the screwing hole.
	- Using the teach pendant, navigate to the pre-saved screw points by accessing **DATA > [TYPE] > Position Registers**. Here, a list of screw points, saved in the position registers, is available.
	- Identify and select one of the screw points from the list. To move the robot to this specific point, double-click **MOVE_TO** on the teach pendant and hold it down until the robot reaches and stops at the designated screwing point.

3. **Adding New Products:**

	- Select "Add new product" within the ISRA Vision System interface.
		![[ISRA_17.png|500]]
	- When prompted to copy settings from an existing product, choose "No."
	- Choose "simple workflow with test" and proceed by clicking "Next."
	- Provide the name and external ID for the new product. Set "Save measurement image" to "Always" for documentation purposes, then click "Next."
		![[ISRA_18.png|500]]
	- Skip loading a CAD model by clicking "Next" and select the sensor named "Daimler Trucks." Proceed by clicking "Next" again.
		![[ISRA_19.png|500]]
	- On the training image page, reduce the contour accuracy to 0.25 using the slider on the right side to enhance system speed, acknowledging that this setting can be adjusted later. Click "Next" to continue.
		![[ISRA_20.png|500]]
	- For the initial setup, skip steps related to robot null tool pose, object contours, contour height, and new zero measurement by selecting "Next" for each.
	- Follow through the remaining steps, including robot pick/place position and test detection, without making changes. After successfully testing the images, click "Ok" to complete the product addition.
		![[ISRA_21.png|500]]

3. **Coordinate System Adjustment:**

	- Identify and select the newly added product from the list by clicking on it.
		![[ISRA_22.png|500]]
	- Click on "Coordinate systems" to open up the coordinate systems configuration menu.
		![[ISRA_23.png|500]]
	- Choose to "Adjust application coordinate system." Confirm changes to the application coordinate system by clicking "Yes" when prompted.
		![[ISRA_24.png|500]]
	- Choose "Use custom base" as the application coordinate system and click "Next."
		![[ISRA_25.png|500]]
	- Input the coordinates of the corresponding user frame (UF 44 or 45), where the screwing point is located, relative to the robot base (UF 0). You can find these values in the teach pendant. Confirm your entries and proceed by clicking "Next" and then "Ok." You will be then brought back to the coordinate systems configuration menu.
		![[ISRA_26.png|500]]
	- Under the coordinate systems configuration menu choose "Adjust Robot-Null-Tool pose". This should be the button on the bottom right corner of the screen.
	- Enter the tool flange (TF 1) pose for this specific position relative to the robot base (UF 0) and confirm by clicking "Ok."
		![[ISRA_27.png|500]]

4. **Detection Settings Adjustment:**

	- On the product menu, select "Detection Settings."
		![[ISRA_28.png|500]]
	- On the right side, enable "Limit search area" and set "Max number of results" to 1. Also, ensure "Rotation" is disabled for stable detection. Then click the arrow on the top left corner of the screen to go back to the product menu
		![[ISRA_29.png|500]]

5. **Contour Model Configuration:**

	- On the product menu, select "Contour model" to go into the contour model configuration menu.
		![[ISRA_30.png|500]]
	- On the right side, type in the contour height in mm. This value can be found using the teach pendant. On the teach pendant inside the position registers list, select the corresponding point and press **POSITION**. Input the Z axis value shown on the teach pendant
		![[ISRA_31.png|500]]
	- Click the "Take new model image" option to capture a fresh image. Confirm by choosing "Yes, take new image."
		![[ISRA_32.png|500]]
	- Then click the "Edit contour feature" option to configure the relevant contours to detect.
		![[ISRA_33.png|500]]
	- Adjust the contour accuracy using the slider on the right side. A good value range between rough and medium.
		![[ISRA_34.png|500]]
	- Click and drag the edges of the green rectangular AOI box on the image to resize it. Ensure the box is large enough to encompass all relevant contours while focusing on the screwing hole for precise detection.
	- 
	- Inside the AOI, green-highlighted contours indicate current selections. To reset this selection, click "Deselect all" located at the bottom right of the screen, removing all previously chosen contours.
	- Identify and click on contours that accurately outline the screwing hole. Adjust the length of these contours by sliding the small green and red circles that appear upon selection, ensuring a snug fit around the screwing hole's perimeter.
	- Locate the green and red directional arrows on the image and drag them to the precise center of the screwing hole. This central positioning is crucial for accurate detection and should be done with care. To finish click "Next."
	- See the image below for reference:
		![[ISRA_35.png|500]]
	- Back in the contour model configuration menu, click on "Take new zero measurement image" and choose "Yes."
		![[ISRA_36.png|500]]
	- Choose "Live image" and click "Next."
		![[ISRA_37.png|500]]
	- Click "Next" and "Ok" to finish.
		![[ISRA_38.png|500]]

6. **Testing the Product:**
	- Go back to the product menu and select "Test."
		![[ISRA_39.png|500]]
	- Click on "Start live detection" to start the test. The live image will appear including the detected contours.
	- On the right side of the image, change the result pose to "Absolute pose" to display the position of the contour, ensuring it aligns with the expected location as per the teach pendant.
	- Click on "Stop live detection" to end the test.
		![[ISRA_40.png|500]]

7. **Activate the Product:**
	- Go back to the product menu. On "General settings" you can see the status of the product. If it's still not activated yet. it shows a red dot with "Inactive" next to it. To activate the product. Click on "General settings."
		![[ISRA_41.png|500]]
	- Click "Activate" and confirm the activation to change the status from red (Inactive) to green (Active).
		![[ISRA_42.png|500]]

## 7. Teach Pendant Programs

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
    - Execute a joint motion command to move the robot to the home position, defined in the respective position register ``PR[7:Home_center]``.

### `AA_PREPOSLH`


1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Left Hand Pre-Position Movement:**
    - Execute a joint motion command to move the robot to left hand pre-position, defined in the respective position register ``PR[8:Home_left_corr]``.

### `AA_PREPOSRH`


1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Right Hand Pre-Position Movement:**
    - Execute a joint motion command to move the robot to right hand pre-position, defined in the respective position register ``PR[10:Home_Right]``.

### `ISRA_CELL_INIT`


1. **Tool Frame Initialization:**
    - Set the tool frame to 3, indicating the camera tool.
2. **User Frame Initialization:**
    - Set the user frame to 0, corresponding to the world or robot base coordinate system.
3. **Payload Initialization:**
	- Set payload to 1, indicating the screwing spindle.
4. **Digital Output Adjustments:**
	- Turn off the left-hand process indicator (`DO[4:LH In Process]`).
	- Turn off the right-hand process indicator (`DO[5:RH In Process]`).
	- Turn off the left-hand turn signal (`DO[7:Turn_2_LH]`).
	- Turn off the right-hand turn signal (`DO[6:Turn_2_RH]`).
	- Activate the left fixture's open state (`DO[101:FixtureOpen]`).
	- Activate the right fixture's open state (`DO[103:FixtureOpen]`).
5. **Timer Resets:**
	- Clear `TIMER[5]` to its initial state.
	- Clear `TIMER[6]` to its initial state.


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

### ``SAFEMOVE_CHECK_HOME``

#### Algorithm

1. **Check Home Position and Part Availability**:
    - If the robot is at the home position and a part is ready on the left (and not on the right), turn towards the left and wait for 0.40 seconds.
    - If the conditions are not met, skip to step 5 for right-hand side processing.
2. **Speed Adjustment for Left-Hand Operation**:
    - If the robot is set to move slowly and no scan is active, set speed to slow and turn off the left-hand turn signal.
    - If the robot is set to move fast and no scan is active, set speed to fast and turn off the left-hand turn signal.
    - If a scan is active, loop back to check speed settings again.
3. **Execute Left-Hand Movement**: Call the program for left-hand position preparation and proceed to the end.
4. **Check Home Position for Right-Hand Operation**:
    - If the robot is at the home position and a part is ready on the right (and not on the left), turn towards the right and wait for 0.40 seconds.
    - If the conditions are not met, check for part availability without turning.
5. **Speed Adjustment for Right-Hand Operation**:
    - Similar to step 2, adjust speed based on robot settings and scan activity, and turn off the right-hand turn signal.
6. **Execute Right-Hand Movement**: Call the program for right-hand position preparation.
7. **End**: Conclude the sequence and prepare for the next cycle.

### ``SAFEMOVE_CHECK_LEFT``

#### Algorithm

2. **Condition Check for Left-Hand (LH) Operation**:
    - If pre-positioned for left-hand operation and LH is not currently in process, turn towards the right-hand (RH) side and wait for 0.40 seconds.
3. **Set Speed Limit**: Default speed is set to slow as a general limit.
4. **Movement Decision Based on Scanning**:
    - If the robot is set for slow movement and no scan is active, turn off the RH turn signal and proceed to final positioning.
    - If the robot is set for fast movement and no scan is active, increase speed to fast, turn off the RH turn signal, and proceed to final positioning.
    - If a scan is in progress, loop back to check movement conditions again.
5. **Final Positioning**: Move the robot to the center position at full speed and stop the timer.

### ``SAFEMOVE_CHECK_RIGHT``

#### Algorithm

1. **Initial Condition Check**: Evaluate conditions for scanning the workspace.
2. **Pre-Condition Evaluation for RH Operation**:
    - If pre-conditions are met (RH is pre-positioned and not in process), initiate a left-hand (LH) turn and pause for 0.40 seconds.
3. **Speed Configuration**: Default to a slow speed setting as a general limit.
4. **Movement Adjustment Based on Scan**:
    - **For Slow Movement**: If set for slow operation and no scan is active, deactivate LH turn and proceed to final positioning.
    - **For Fast Movement**: If set for fast operation and no scan is active, deactivate LH turn, set to fast speed, and move to final positioning.
5. **Scan In Progress**: If a scan is active and fast movement is set, loop back to re-evaluate movement conditions.
6. **Final Positioning**: Move to the central home position at full speed and stop the timer.

### Notes:

- Why toggle DO[6:Turn_2_RH] & DO[7:Turn_2_LH] ON/OFF?
- 

