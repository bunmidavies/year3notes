[[COMP34212]]

- HAMMER = Hierarchical Attentive Multiple Models - used for the control of attention during imitation, one of the core [[social interaction skills]] during development
- the main idea involves a series of parallel models:
	- inverse models: takes the current state + the target goal as inputs, and outputs the motor control commands for the goal
	- forward models: takes the current state + control command as inputs, and outputs the predicted next state of the robot

![](https://i.imgur.com/ivqJlTZ.png)

- HAMMER has been used widely in a number of applications involving imitation:
	- robotic head ESCHeR, that observes + imitates human head movements
	- mobile robot Peoplebot with arm imitating actions as "pick X" or "move hand towards X"
	- imitation for robotic wheelchairs
	- imitation of dancing (Nao robot)