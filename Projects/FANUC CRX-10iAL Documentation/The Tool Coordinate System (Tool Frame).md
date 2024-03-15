>[!SUMMARY]+ Table of Contents
>         - [[The Tool Coordinate System (Tool Frame)#Introduction to the Tool Coordinate System|Introduction to the Tool Coordinate System]]
>         - [[The Tool Coordinate System (Tool Frame)#Understanding the Basics|Understanding the Basics]]
>         - [[The Tool Coordinate System (Tool Frame)#Position and Orientation|Position and Orientation]]
>         - [[The Tool Coordinate System (Tool Frame)#Advantages of Defining a Tool Center Point (TCP) on a Robot's Tool|Advantages of Defining a Tool Center Point (TCP) on a Robot's Tool]]
>         - [[The Tool Coordinate System (Tool Frame)#Calibrate a New Tool Frame|Calibrate a New Tool Frame]]
>         - [[The Tool Coordinate System (Tool Frame)#Activating and Testing the Calibrated Tool Frame|Activating and Testing the Calibrated Tool Frame]]

#### Introduction to the Tool Coordinate System

The tool coordinate system, or the **"Tool Frame"**, is crucial in robotics. It helps us control where and how a robot's tool moves and rotates in space. Imagine it as a guide that tells the robot's tool where to go and how to align itself.

#### Understanding the Basics

- **What is it?**: The tool coordinate system is a non-stationary, Cartesian system, which means it uses a grid made of right angles (like the squares on graph paper) for positioning.
- **Tool Center Point (TCP)**: This is the starting point, or 'zero point', of our coordinate system. It's located right at the heart of the tool.
- **Axes Orientation**:
    - **Z-Axis**: Generally points along the tool's direction. Think of it as pointing outwards from the tip of the tool.
    - **Default Position**: If not set up, it's at the front center of the tool flange (the part where the tool attaches to the robot), called the Tool Attachment Point (TAP). The Z-axis aligns with the robot's 6th axis.
    - **Standard Orientation**: The Z-axis typically points in a positive direction (away from the robot).

#### Position and Orientation

- **Coordinates**: We use six coordinates to describe the tool's position and orientation: x, y, z, w, p, r.
    - **x, y, z**: These describe the tool center point's position.
    - **w, p, r** (yaw, pitch, roll): These describe the tool's orientation by its rotations around the x, y, and z axes.
- **Flexibility**: You can adjust the position and orientation to fit different tools.
- **Multiple Systems**: Up to 10 different tool coordinate systems can be set (and this number can be changed in the robot's settings).

![[TF_1.png | center]]

#### Advantages of Defining a Tool Center Point (TCP) on a Robot's Tool

 1. **Easy Orientation and Precision:** 
	 - With a TCP, the robot knows exactly where the pivot point of the tool is. 
	 - Makes manual operations simpler and more precise, as the robot can orient its tool accurately.
 2. **Consistent Speed in Movements:** 
	 - The speed at which the robot moves its tool is based on the TCP. This is important for tasks that require consistent speed. 
	 - It ensures that movements are smooth and consistent, directly benefiting the quality of tasks like gluing or welding.
 3. **Flexibility in Tool Switching:** 
	 - You can switch between different tools on the same robot by selecting the corresponding TCP for each tool. 
	 - This allows the robot to approach the same point using different tools, enhancing programming efficiency and versatility.
4. **Customizable Impact Direction:**
	- The direction in which the tool impacts or interacts with objects can be freely set.
	- Offers more control during manual operations, allowing for a wide range of tasks to be performed more effectively.

![[TF_2.png | center]]

#### Calibrate a New Tool Frame

1. **Accessing the Tool Frames Menu:**
    - Navigate to **"MENU (Extend the Menu) > SETUP > Frames"** on the teach pendant.
		![[TF_3.jpg|250]] ![[TF_4.jpg|250]]
    - If the screen doesn't display **"Tool Frame"**, press the **[OTHER]** button and select **"Tool Frame"**.
	    ![[TF_5.jpg|250]]
2. **Selecting a Tool Frame:**
    - In the **"Tool Frame"** section, pick a free entry from the list and press the **"DETAIL"** button. This allows you to enter the specifics of the new tool frame. For example, here we choose the entry number 9.
	    ![[TF_6.jpg|250]]
3. **Choosing the Calibration Method:**
	- Press the **[METHOD]** button to select a method for setting up the tool coordinate system.
	- **Direct Entry Method:**
	    - This method lets you manually enter the coordinates of the tool center point. It's useful if you already know these details from data sheets or CAD system measurements.
	    - After clicking **[METHOD]** button, select **"Direct Entry"**.
		    ![[TF_6_1.jpg|250]]
4. **Entering Coordinates and Orientation:**
	- In the **"Comment"** field, double-click on the line with asterisks to add a comment for your reference.
		![[TF_7.jpg|250]] ![[TF_8.jpg|250]]
	-  Use the arrow keys and numeric keypad to input the coordinates (X, Y, Z) and orientation (yaw, pitch, roll) of the tool.
		![[TF_9.jpg|250]]
	- **Note**: Measure the distance from the tool flange (Default Position) in X, Y, Z coordinate and the orientation. Distance is measured in millimeters and orientation in degrees.

#### Activating and Testing the Calibrated Tool Frame

Once you've successfully calibrated the tool coordinate system, it's important to activate and test it to confirm everything is set up correctly. Here’s how you can do it:
1. **Accessing the Jog Menu:**
	- Hold the **"SHIFT"** key and press the **"COORD"** key simultaneously. This action will open the jog menu on your robot's interface.
2. **Activating the Tool Coordinate System:**
	- In the jog menu, navigate to the **"Tool"** option.
	- Enter the number of the tool coordinate system that you've just calibrated.
	- Confirm your selection by pressing **"ENTER"**.
	- The new tool coordinate system is now active.
	![[TF_10.png]]
3. **Testing the Tool Coordinate System:**
	- Select the **"TOOL"** coordinate system through the **"COORD"** option.
	- Rotate the tool around the x-, y-, or z-axis. As you do this, observe the movement and position of the tool center point closely.
	    - **What to Look For**: Ensure that the tool moves as expected and that the tool center point aligns correctly with your inputs.
	- Additional Testing (if applicable):
	    - If you used the **Direct Entry** or the **Six Point Method** for calibration, also verify that the axis directions are correct as per your specifications.

**Note on Observation**
- Pay attention to how the tool behaves as you rotate it. The movements should correspond accurately to the axis you are manipulating.
- If you notice any discrepancies or unexpected movements, you may need to recalibrate or adjust the settings.