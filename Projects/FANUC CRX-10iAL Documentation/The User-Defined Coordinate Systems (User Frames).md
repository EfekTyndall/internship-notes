>[!SUMMARY]+ Table of Contents
>         - [[The User-Defined Coordinate Systems (User Frames)#General Overview|General Overview]]
>         - [[The User-Defined Coordinate Systems (User Frames)#Key Characteristics|Key Characteristics]]
>         - [[The User-Defined Coordinate Systems (User Frames)#Importance in Programming|Importance in Programming]]
>         - [[The User-Defined Coordinate Systems (User Frames)#Capacity and Special Notes|Capacity and Special Notes]]
>         - [[The User-Defined Coordinate Systems (User Frames)#Calibrate a New User Frame|Calibrate a New User Frame]]
>         - [[The User-Defined Coordinate Systems (User Frames)#Activating and Testing the Calibrated USER Frame|Activating and Testing the Calibrated USER Frame]]

#### General Overview

User-defined coordinate systems, known as **"User Frames"** are essential in robotics for customizing how a robot interacts with its environment. They allow programmers to define specific coordinate systems for various tasks and tools.

#### Key Characteristics

- **Cartesian System**: Like the tool coordinate system, user frames are Cartesian, meaning they use a grid system based on right angles for positioning.
- **Relation to 'WORLD' Coordinate System**: By default, the starting position and orientation of a user frame is the same as that of the 'WORLD' coordinate system, which is the robot's overall reference system.
- **Customizable Position and Orientation**:
    - **Defined by Six Coordinates (x, y, z, w, p, r)**:
        - **x, y, z**: Set the origin of the user frame relative to the 'WORLD' frame.
        - **w, p, r**: Define the rotation of the user frame around the x-, y-, and z-axes of the 'WORLD' frame.

#### Importance in Programming

- **Reference for Position Data**: All position data in the robot's program refer to the active user frame when the position was saved.
- **Adaptability**: If there's a change in the positioning of fixtures or tools within the robot's working area, you can recalibrate to match the previously saved positions by adjusting the user frame.

#### Capacity and Special Notes

- **Number of Frames**: By default, up to 9 user-defined coordinate systems can be set, and this number can be adjusted in the system settings.
- **Special User Frame 0**: This frame is unique as it's fixed and always corresponds to the 'WORLD' coordinate system, meaning it cannot be changed.

#### Calibrate a New User Frame

Calibrating a User Frame is essential to align the robot's tasks with its environment. There are different methods to set up a USER frame, with **"Direct Entry"** and the **"Three-Point Method"** being common. Here's how to do it:

1. **Accessing the User Frame Menu:**
	- Navigate to **"MENU (Extend the Menu) > SETUP > Frames"** on the teach pendant.
		![[UF_1.jpg|250]] ![[UF_2.jpg|250]]
	- If the **"User Frame"** aren't displayed, press **[OTHER]** and choose **"User Frame"**.
		![[UF_3.jpg|250]]
2. **Selecting a User Frame:**
	- Select an entry from the list and press **"DETAIL"**. For example, here we choose the entry number 9.
		![[UF_4.jpg|250]]
3. **Choosing the Calibration Method:**
	- Press the **[METHOD]** button to select a method for setting up the User Frame.
	- Ensure that the right Tool Frame is chosen, before continuing with the calibration method. Refer to [[The Tool Coordinate System (Tool Frame)]] for further information.
	- **Direct Entry Method:**
		- **When to Use**: If you know the User Frame's coordinates in relation to the robot's WORLD system in advance.
		- **Steps**:
		    - After clicking **[METHOD]** button, select **"Direct Entry"**.
				![[UF_5.jpg|250]]
		    - In the **"Comment"** field, double-click on the line with asterisks to add a comment for your User Frame.
				![[UF_6.jpg|250]] ![[UF_7.jpg|250]]
		    - Use the arrow keys and numeric keypad to input the coordinates (X, Y, Z) and orientation (yaw, pitch, roll) of the tool.
	- **Three-Point Method:**
		- **When to Use**: Commonly used when the device coordinates are unknown.
		- **Prerequisite**: Ensure the correct Tool Frame is activated for the measuring tip (refer to [[The Tool Coordinate System (Tool Frame)]]).
		- **Steps**:
		    - After clicking **[METHOD]** button, select **"Three Point"**.
				![[UF_8.jpg|250]]
		    - In the **"Comment"** field, double-click on the line with asterisks to add a comment for your User Frame.
				![[UF_9.jpg|250]] ![[UF_7.jpg|250]]
		    - For the first point **"Orient Origin Point"**, move the robot so the measuring tip is at the desired origin and record the position by pressing **"RECORD"** while holding the **"SHIFT"** key on the teach pendant. 
		    - The text will then change from **"UNINIT** to **"RECORDED**.
				![[UF_10.jpg|250]] ![[UF_11.jpg|250]]
		    - For the second point **"X Direction Point"**, move the tip about 200mm in the x-axis direction and record the position.
		    - For the third point **"Y Direction Point"**, move the tip about 200mm in the y-axis direction from the current or base point.
		    - **Pro Tip:** 
			    - Before moving the tip in the y-axis direction, you need to move the tip back to the origin point. This will result a more accurate calibration.
			    - To do that just select **"Orient Origin Point"**, then hold the **"SHIFT"** key and simultaneously holding the **"MOVE_TO"** button. This will move the tip to the origin point.
					![[UF_13.jpg|250]]
4. **Completion and Troubleshooting:**
	- **Finalizing**: After moving to all required points, the new User Frame's coordinates are calculated.
	- **Successful Calibration**: **"USED"** will be displayed after each point, and the calculated coordinates (X, Y, Z, W, P, R) will be shown.
		![[UF_12.jpg|250]]
	- **Error Handling**: If errors occur, like recording identical positions for different points, the coordinate fields will remain empty. In such cases, revisit the steps to correct the errors.

#### Activating and Testing the Calibrated User Frame

Once you've calibrated the User Frame, it's important to activate and test it to confirm it functions correctly. Here's a straightforward guide on how to do this:
1. **Accessing the Jog Menu:**
	- Hold the **"SHIFT"** key and simultaneously press the **"COORD"** button. This will open the jog menu on the robot's interface.
2. **Activating the User Frame:**
	- In the jog menu, go to the **"User"** option.
	- Enter the number of the User Frame you just calibrated.
	![[UF_14.png]]
3. **Testing the User Frame:**
	- With the new User Frame activated, go back to `COORD` and select the **"User"** coordinate system.
	- If necessary, reduce the robot's speed for safety and precision during the test.
	- Now, conduct movement tests:
	    - Move the robot in the directions of the x, y, and z axes.
	    - **Observation**: Carefully watch the robot's movements. They should correspond accurately to the commands based on the User Frame coordinates.
	    - **What to Look For**: Ensure that the movements are smooth and align with the expected directions of the x, y, and z axes.

**Note on Testing:**
- During testing, it's crucial to monitor the robot's response closely. If the movements don't match your expectations or seem erratic, it might indicate an issue with the calibration.
- If any discrepancies are noticed, recheck your calibration steps, or consider recalibrating the User Frame.