[[COMP34212]]

- localisation asks the following questions?
	- how can you build the map of a new world?
	- how do you recognise where you are?
	- how can you simultaneously map the world and be sure where you are?
	- how do you explore new areas efficiently and consistently?
	- how do you label the map with objects and features or terrain?

- [[SLAM vs vSLAM vs VO|SLAM]]: Simultaneous Localisation and Mapping

### Mobile Robot Localisation (position estimation)

- *"The problem of determining the pose of robot relative to a given map of the environment."* (Thrun et al.)
- Pose **x** of a robot: its position $(x,y)$ and orientation ($\theta$) - $x = (x,y,\theta)^T$
- bayesian algorithms to estimate the probable location of a robot

### Feature-Based Localisation

- to extract features from raw data and match these to the map e.g. corners, walls doors
- common methods include [[marcov localisation]] and [[extended kalman filters]]

