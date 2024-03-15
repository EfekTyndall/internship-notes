- **Important:** 
	- Make sure all of the tool frame [1] values set to zero! 
- **Mirai_DemoV5 Positioning Skill**:
	- The robot can go from the reference position to the target object and orientating based on the location and orientation of the target object (per 22-01-2024).
	- Issue: 
		- At a certain point/ position, the robot can't find the target object. In this example, the robot can only reach until half of the working area (area with the red tape)
		- If the target object positioned on the edge of the working space, robot sometimes won't reach and orientate to the target object
	- Solution: 
		- Record more episode, so that it can reach farther distance from the reference point
		- Try to make the text on side visible near the reference point when recording episodes
		- Use shortest path with no extra movement to the target object
- **Problems:** 
	- We don't have consistent lighting

# Changes on 22-02-2024

- DEMO_2:
	- Adjust override speed before loop
	- Adjust linear motion speed to 250mm/s
	- Adjust all joint motion speed to 100%
	- Turn collaborative mode on before the loop
	- Turn off collaborative mode before MIRAIEXECUTE(4)
	- Turn on collaborative mode after MIRAIEXECUTE(4)
