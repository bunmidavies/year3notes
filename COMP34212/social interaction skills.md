[[COMP34212]]

- within a child's development, there are 4 main skills which develop incrementally:
	1. joint attention: gaze and pointing gestures
	2. imitation: body movement, action/goals
	3. cooperation: spontaneous altruistic behaviour
	4. theory of mind: ability to attribute beliefs, goals and percepts to other people

# joint attention / gaze

- there are 4 main developmental stages:
	1. sensitivity stage - child only understands that it can look to the left/right side of the caregiver's gaze direction
	2. ecological stage - child begins to scan along the line of gaze for the object they're looking for
	3. geometrical stage - the child recognises the angle they must orientate to be able to see the object of interest
	4. representational stage - the child has the abilities of all previous stages, and can also find objects outside its current field of view

# example model: nagai et all

![500](https://i.imgur.com/eQP1Qmv.png)

- the underlying architecture has 5 underlying components:
	- salient feature detectors: colour, edge, motion and face
	- visual feedback controller: moves the head towards the salient object in the robot's view
	- self-evaluator learning module: neural network to learn the mapping between face image and head position, and the desired motor signal
	- internal evaluator: check if there is an object in the centre of the vision/image
	- gate module: selects between outputs from visual feedback controller and the learning module to return the corresponding motor command

![500](https://i.imgur.com/EeZi1PG.png)

# joint attention and pointing

- imperative pointing: requesting an object when another agent isn't initially looking at it
- declarative pointing: creating shared attention on an object, thus making it the focus of the interaction
