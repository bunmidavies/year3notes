[[COMP34212]]

- a robotic manipulator consists of one or more links connected by joints, with an end effector - the end effector is used to affect and move objects within the environment
- each joint has its own joint limit, specifying the extent to which the joint can move
- the ==workspace== of an end effector describes the set of all poses attainable by that end effector mounted on the manipulator

- manipulation problems involve defining endpoints for specific joints, and figuring out paths for a manipulator to take in order to reach some endpoint, with specific joint angles
- [[forward kinematics and inverse kinematics]]

# degrees of freedom

- common degrees of freedom include:
	- shoulder joint (ball) - 3 DOF
	- wrist joint - 2 DOF (?)
	- elbow joint - 1 DOF

# dynamics

- dynamics describe the properties of motion and energy of a moving object, while its moves - depending on the robot and its movement, dynamics can have different effects:
	- slow-moving robots probably wont be strongly impacted by dynamics
	- fast-moving robots likely need to consider dynamics more
- computing direct and indirect dynamics can also be expensive

# compliance

- compliance is the need for a manipulator to yield to environmental forces i.e. certain safety measures need to be made for if a human comes into contact with the manipulator
- certain measures include:
	- springs in joints
	- using soft materials
	- software compliance