[[COMP34212]]

- path planning can take 2 main approaches:
	- ==qualitative== (topological/route navigation)
		- agent's perspective
		- topological route with distinct landmarks/associations - landmarks can be thought of as waypoints which are easy for the robot to recognise, e.g. natural landmark, sign, visual pattern, or landmark to change behaviour
		- the world can be thought of as a relational graph of nodes and edges - the nodes always represent gateways/landmarks/goals, while the edges represent the paths to get to the path

# topological navigation

- distinctive places (landmark methods):
	- landmarks are treated as waypoints, where each landmark has a perceptually distinct feature, and is easy to recognise
- associative methods:
	- associations are made between perceptual state and movement - for instance, visual homing involves associating visual patterns with locations/routes (example: bees navigation)
- relational graph methods:
	- represent the world as a graph of nodes and edges, where nodes represent gateways, landmarks or goals, and edges represent a navigable path between two nodes
	- a multi-level spatial hierarchy can be introduced, useful for animal navigation