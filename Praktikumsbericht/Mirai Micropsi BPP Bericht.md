I was introduced to a project aimed at revolutionizing the assembly line's operational efficiency and adaptability through the integration of Micropsi Industries' MIRAI robot control technology with a FANUC CRX-10iA/L collaborative robot.

The main objective was to automate complex, dynamic tasks that require a high degree of precision and adaptability, which are often beyond the capabilities of traditional automation systems. By leveraging the advanced machine learning capabilities of MIRAI robot control technology in conjunction with the collaborative features of the FANUC robot, the project aimed to introduce a more adaptable, intuitive, and efficient automation solution, responding to the manufacturing sector's growing demand for flexible and intelligent automation systems.

# Mirai Robot Control Technology Overview

Micropsi Industries' MIRAI technology is a robot control system, utilizing advanced machine learning—a subset of artificial intelligence—to enable real-time execution of complex tasks by robots. This system departs from traditional automation by allowing intuitive, hand-guided training processes instead of relying on scripted programming.

MIRAI's uses imitation learning, a type of supervised learning where the system learns to replicate desired behaviors by analyzing examples. This enables the MIRAI-equipped robot to learn directly from human demonstrations, acquiring behaviors such as precise manipulation of objects based on visual and sensory feedback.

During the training phase, operators guide the robot through the desired actions, with each movement captured by an integrated camera system. These visual inputs are then transformed into data and processed by the MIRAI controller, which sends the information to Micropsi Industries' cloud for analysis. Here, machine learning algorithms develop 'skills' or mathematical models that dictate the robot's actions, allowing it to adapt to variances in real-time tasks without the need for further programming.

These 'skills' function as dynamic guidelines for the robot, enabling it to autonomously perform tasks with a high degree of precision and flexibility, even in the face of environmental changes or task variations. The system's ability to iteratively refine these skills through repeated training sessions ensures robustness and reliability, making MIRAI a powerful solution for automating tasks that demand sophisticated hand-eye coordination and adaptability.

# Scope and Implementation

The scope of the project was precisely defined to focus on tasks that demand advanced hand-eye coordination. A key task was the precise manipulation of truck switches into a bracket during the assembly process. The implementation involved conducting hand-guided training sessions to develop "Mirai-Skills", optimizing these skills for real-time application and integrate these skills together with the FANUC robot program, ensuring the robot could adapt effectively to variations in the task.

# System Setup and Configurations

## Hardware Setup

The integration of MIRAI Robot Control Technology with the FANUC CRX-10iA/L Collaborative Robot relied on various key hardware components, each contributing to the system's overall functionality. Theses components included:

- **Fanuc CRX-10iA/L Collaborative Robot and R-30iB Mini Controller**: The primary robotic unit used in the project, selected for its adaptability and safety features conducive to collaborative work settings.
    
- **Mirai Robot Controller**: The control unit responsible for:

    - Capturing and preserving user-conducted training sessions.
	- Acquiring and storing skills trained via the Micropsi Industries training platform.
	- Generating and directing the robot's actions by applying these trained skills in real-time, guided by visual and other sensory feedback.

- **Ximea xiQ USB3 Camera with Fujinon Lens and Ring Light**: A high-resolution camera setup used to provide visual input to the Mirai system.
    
- **ATI F/T Sensor (Force/Torque Sensor)**: A sensor that provides feedback on the forces and torques applied.
    
- **Gripper**: The end-effector attached to the robot, designed to grasp and manipulate various objects for tasks such as picking and placing components.

The camera, F/T sensor and gripper are securely attach to the robot flange. The F/T sensor is mounted after the camera holder so that the force measurement is not influenced by the camera. The gripper then is attached after the F/T sensor.

The camera is positioned such that changing positions of the target object manifest as noticeable differences in the camera view. The lighting played a significant role. The more consistent the lighting conditions, the easier it is to train a reliable skill. The ring light offers a consistent amount of light because it travels with the camera.

## Network Setup

A crucial step in the integration process involves establishing a robust connection between the MIRAI controller and the FANUC robot's control system. This necessitates a precise arrangement of all hardware components, ensuring they are interconnected correctly. As illustrated in the schematic diagram [refer to Figure], the connections encompass various types, including USB and Ethernet, facilitating communication between the different elements of the system.

[[_Insert setup scheme here_]]

The MIRAI system comprises two main parts:

- **MIRAI Controller**: This component is the heart of the system, responsible for generating sensor-informed, real-time movements of the robot based on the skills that have been trained and stored. Its ability to translate complex sensor inputs into smooth robotic actions is fundamental to the system's efficiency and effectiveness.
- **MIRAI Training App**: Serving as the primary interface for the MIRAI controller, this application is essential for recording training episodes and managing the skills within the MIRAI ecosystem. Designed for ease of use, the app runs on Android-based tablets, allowing users to interact with the system in a highly intuitive manner.

At the beginning of my involvement of the project all of the necessary hardware components and internal network are already being set up and established.

## Tool Configuration

Before initiating the creation and training of a positioning skill, it is essential to configure the gripper being used through the MIRAI Training App, as this ensures precise control and interaction with objects by allowing the MIRAI System to accurately recognize and integrate the physical characteristics of the gripper. 

The Tool Configuration Menu within the MIRAI Training App offers a platform where users can manage and set up multiple tools. To configure the robot gripper, it is necessary to assign it a name and select the corresponding robot model and sensor. Additionally, critical information such as the tool's Mass and Center of Gravity (CoG) must be provided, with accurate values sourced from the gripper manufacturer's specifications. After entering these details and saving the configuration, thereby finalizing the tool's integration (see tool configuration screenshot).

[Insert tool configuration screenshot]

# MIRAI-Skill Types

MIRAI is designed to navigate complex paths and adapt to visual changes in real-time, with two core competencies:

1. **Positioning Skills**: These enable the robot to align itself with a stationary target quickly and efficiently, using the most direct path. It's essential that the route from the starting point to the target is clear of obstructions for these skills to function.
    
2. **Motion Skills**: These skills allow for more sophisticated movements, suitable for a variety of tasks such as inserting components, tracking contours, handling objects on moving conveyors, or operating in tight spaces where a straight path is not viable.
    
The focus was on employing positioning skills for the precise placement of truck switches into brackets during assembly. The task involves guiding the robot from a reference point to the switches, picking them up, and then moving them into a bracket for insertion. This process requires creating two distinct positioning skills: one for picking up the switches and another for placing them into the brackets.

# Creating and Training a Positioning Skills

## Creating Positioning Skills

The first step in the process is to define a starting point. This involves manually guiding the robot's Tool Center Point (TCP)/ Gripper to a specific location using the teach pendant. 

For the picking task, the chosen starting position is [input joint position of the robot here] (refer to the teach pendant image for details on the joint position). This spot is selected to ensure the camera has a clear view of the entire work area for the picking task. 

For the placing task, the chosen starting position is [input joint position of the robot here] (refer to the teach pendant image for details on the joint position). This position is located above the holder where the bracket is placed, ensuring clear view of the bracket and its holder

Both position is recorded relative to robot base/ world coordinate in position registers [input position registers number here] (refer to the teach pendant's position register image) within the robot's controller, allowing for easy repetition of this setup in later tasks.

[Insert image of the teach pendant showing joint position] [Insert image of the teach pendant showing position register]

Following the setup, we begin creating new skills via the MIRAI Training App. This involves making several key adjustments in the app to customize the robot's operations for the task at hand. We choose the "Positioning Skill" for this task, which involves picking and placing switches. The skills are named, and the number of cameras used is set, in this case, just one.

[Insert Skill Creation Screenshot 1]

Additional settings include confirming the robot model and the force/torque sensor, which should already be connected and recognized by the MIRAI System. The configuration for a wrist-mounted camera is also specified.

[Insert Skill Creation Screenshot 2]

Setting up the axis configuration is another important step, determining the movements the robot can make. To optimize the task of switch picking, the robot is set to move along the x, y, and z axes and to only rotate around the z-axis, making the movement pattern simpler and more efficient. For the placing task, the robot is set to also rotate around the x and y-axes.

[Insert Skill Creation Screenshot 3]

The tool being used is also specified, which in this scenario is the previously configured robot's gripper.

[Insert Skill Creation Screenshot 4]

Adjusting the camera's gain and exposure is the next step. These settings can be tweaked while viewing the live image on the screen. Here a gain value of [input gain value] and a exposure value of [input exposure value]. The camera should be set up so the target object is clearly visible in the live view.

[Insert Skill Creation Screenshot 5]

The final step involves saving a reference or starting position in the Training App, using the starting point defined earlier as the reference. This concludes the skills creation process.

[Insert Skill Creation Screenshot 6]

## Recording Episodes

Once the skills are created, it appears on the home screen, signaling the start of the training phase. This phase is entered through the training mode, where the user manually navigates the robot between the designated starting point and the target location, then back to the start. These navigational runs are termed episodes and are integral to 'training' the robot.

To begin recording an episode, it's crucial to first position the robot accurately at the starting point. This can be achieved by either directing the robot automatically to the reference position or manually aligning it to a selected starting location. Clearing any obstacles around the robot and calibrating the Force/Torque (F/T) sensor is essential before moving forward.

Prior to initiating the recording, ensuring an unobstructed path from the start to the target location is necessary, along with the removal of any potential interference from the training area. The robot's Tool Center Point (TCP) is then manually guided to the target location, positioned ideally above the intended picking or gripping area.

For the placing task, the switch needs to be gripped by the TCP first. This is done by manually closing the gripper using the teach pendant. After the switch is clamped to the gripper, the TCP is manually guided to the target location, positioned so that the switch is slightly inserted to one of the bracket holes.

Recording begins once the TCP reaches the target location. During this phase, the TCP is manually maneuvered in a spiral pattern away from the target to cover all significant points in the surrounding space that the robot might encounter during the skill's execution. When the skills includes rotational movements, it's vital to navigate through all relevant positions and orientations of the tool within the workspace to ensure the target is captured from multiple angles, especially focusing on areas close to the target location.

Releasing the robot during training triggers an automatic return to the target position and orientation, aiding in keeping the focus on the required area and previewing the eventual movement the skills will perform.

Visibility of the target throughout the recording is crucial. If at any point the target is not visible, the episode should be reconsidered for discard to ensure the quality of the training.

After finishing a recording session, the system provides an option to review the episode. Smoothly conducted sessions are saved, while others may be discarded to maintain training quality. Recalibrating the F/T sensor after each episode is necessary to avoid drift and ensure precise guidance.

Recording a minimum of 5-10 episodes, each with 60-90 minutes duration are recommended to encompass a broad spectrum of variations, making the developed skills robust and versatile for different operational conditions.

## MIRAI Cloud Training

Once the requisite number of episodes are recorded, the skills are primed for cloud-based training within the Micropsi Industries platform. Initiating cloud training prompts a status update, "Cloud training in progress," accompanied by an estimate of the time needed for completion, typically around 90 minutes. Upon conclusion of the cloud training phase, the skills become accessible for testing purposes.

## Testing and Optimizing Skills
  
After the cloud training has been completed, the skills for both picking and placing tasks are prepared for testing, which is conducted from the home screen. The robot is first positioned at a designated starting point by either reverting to a reference position saved earlier or through manual adjustment. Obstacles are cleared and the Force/Torque (F/T) sensor is calibrated prior to beginning the tests.

**For the picking task:**

- The switch is to be placed on the work area, either to mimic real-world scenarios or to replicate the conditions of the initial training setup, before the test is initiated.
- Once the robot has been positioned at the starting point, the visibility of the switch is confirmed by examining the live view.
- Upon skill execution, the gripper is expected to move precisely from the starting point to the switch, skillfully adapting to the switch's position and orientation.
- The robot's adaptability is tested by changing the switch's position and orientation during the test, to see if the robot can adapt and follow the changes.

**For the placing task:**

- The gripper is first manually guided to the switch in the work area using the teach pendant, where the switch should be clamped by the gripper.
- The gripper is then closed manually using the teach pendant
- The gripper is then moved to the reference position, ensuring the bracket and its holder are visible in the live view.
- The skill execution process, similar to the picking task, should be started, with the robot's performance being carefully observed.

Manual intervention with the guidance feature may be necessary during testing if something goes wrong or for safety reasons.

Skills automatically conclude upon reaching a designated end state but can be restarted for further assessment. The end state that halts the skill will be indicated, providing insights into why the skill execution stopped.

Between tests, recalibration of the sensor is required to ensure accuracy. If the skills demonstrate consistent performance under various conditions, they are deemed ready to be integrated with the FANUC Program. Any deficiencies identified can be addressed by focusing on specific areas in need of improvement during subsequent training sessions, thereby enhancing the skill's effectiveness.

# Integrating MIRAI Skills with FANUC Teach Pendant

## Adding MIRAI Skills to String Registers

For a MIRAI skill to be executed within a teach pendant program, the skill name must first be entered  into String Registers in the robot controller using the teach pendant. The picking skill is saved to Register R[5] and the placing skill is saved to register R[4]

1. **Access to the Registers**: The DATA String Registers are accessed by selecting the desired display area, followed by tapping on [DATA] and then [TYPE].
    
2. **Selection of the Register Type**: [3 String Reg] is chosen from the options available to proceed to the string registers section.
    
3. **Skill Name Entry**: In the right field of an empty register, a double tap and then [ENTER] are performed to enter the name of the desired skill to be executed, such as SR[ 3: ] = skill2. Ensuring the skill name precisely matches the one in the MIRAI Training App is crucial. Optionally, a comment or additional relevant information about the skill can be added in the left field of the register. All the skills intended for inclusion in the program are listed in this section.

## Creating a Program to Execute MIRAI Skills

Once the skills have been entered into the data string registers, a program can be developed and designated [insert program name]. This program is designed to orchestrate the entire task of picking up the switch and positioning it into the bracket, necessitating the invocation and execution of each skill for the picking and placing tasks at precisely timed intervals within the program.

### Algorithm Overview

1. **Initialization:**
    
    - Enable collaborative mode for safety.
    - Set motion speed override to 25% for safety and precision.
2. **Main Processing Loop (Repeat 4 Times):**
    
    - Activate the gripper.
    - Open the gripper fully.
    - Move the robot arm to the picking task start position at maximum speed with precise stopping.
    - Execute the picking skill to find the switch.
    - Close the gripper.
    - Move linearly to the "Gripper Offset Position" at a controlled speed with precise stopping.
    - Move to the placing task start position at maximum speed with precise stopping.
    - Disable collaborative mode.
    - Execute the placing skill to slot in the switch to the bracket
    - Enable collaborative mode
    - Open the gripper to release any held object.
    - Return the robot arm to the home position at maximum speed with precise stopping.
3. **Reset:**
    
    - The loop concludes after 4 iterations, ensuring the sequence is repeated the specified number of times.

### Pseudocode

```
// Initialization
Set collaborative_mode = OFF
Set speed_override = 25%

// Main Processing Loop
For counter = 1 To 4
    ActivateGripper(gripper_id=9)
    OpenGripper(gripper_id=9, position=0, speed=255, force=255, option=1)
    MoveToPosition(position_id=8, speed=100%, mode=FINE)
    ExecuteExternalTask(task_id=5)
    CloseGripper(gripper_id=9, position=255, speed=255, force=255, option=1)
    MoveLinearToPosition(position_id=10, speed=250mm/sec, mode=FINE)
    MoveToPosition(position_id=9, speed=100%, mode=FINE)
    Set collaborative_mode = ON
    ExecuteExternalTask(task_id=4)
    Set collaborative_mode = OFF
    OpenGripper(gripper_id=9, position=0, speed=255, force=255, option=1)
    MoveToHomePosition(position_id=5, speed=100%, mode=FINE)
EndFor

// Cleanup and Reset (if any)
// End of Program

```

# Challenges and Constraints

The project faced several challenges, including the significant time required for the training phase and the need for multiple sessions to achieve the desired level of skill robustness. Technological limitations, such as the camera's field of view and the requirement for continuous manual input during training, presented additional hurdles. The integration of specific hardware components, like force sensors, was also crucial for the optimal functionality of the system, highlighting the complexity of integrating various technological elements to achieve the project's goals.



