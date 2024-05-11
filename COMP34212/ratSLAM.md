[[COMP34212]]

- ratSLAM aims to emulate the spatial navigation ability of the rat's hippocampal system, who essentially build cognitive maps of environments
- similar to SLAM, the overall goal is building and using maps of large and complex environments simultaneously - its less accurate than SLAM, but theres flexibility to:
	- cope with noisy input
	- deal with changing environments
	- accommodate complexity
- example applications include the iRat: a rat-like robot for spatial navigation experiments, which uses ratSLAM
- OpenRatSLAM is also an open-source version of RatSLAM, with bindings to the Robot Operating System (ROS), meaning any robot could technically take advantage of the navigation cell concepts/visual odometry estimates

# navigation cells in rats

- the place cell, head direction cell and grid cell were discovered in the hippocampus in 1971, 1985 and 2005 respectively
- grid cells and place cells form a path integration mechanism for cognitive maps
	- these give rats the innate sense of the world and their location within it, similar to SLAM mechanisms

### place cells
- place cells fire consistently when the rat is at a specific familiar location within the environment
- the cognitive map in the hippocampus is made up of thousands of place cells, covering the surface of any space

### head direction cells
- head direction cells fire when the rat's head is at specific orientations - all orientations are represented by the head direction cell population
- thus, head direction cells have no correlation with the rat's location

### grid cells
- grid cells fire in a metrically regular way across the whole surface of a given environment - the cells fire when a rat is located at any vertex of a hexagonal pattern across the environment
- the cells are used as a signal for measuring displacement distances and direction

# path integration

- path integration is used to join together individual movements to understand which direction a rat is moving in, at what speed, and for how long
- this ultimately helps to form an inner cognitive map within environments