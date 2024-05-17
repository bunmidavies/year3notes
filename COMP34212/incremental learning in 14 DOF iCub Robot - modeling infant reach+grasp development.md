[[COMP34212]]

- realises the development of reaching and grasping skills similar to those displayed by infants, taking into account reflex behaviours initially possessed, neurophysiological and cognitive maturations occurring during relevant development periods
- the following characteristics are exhibited by the resulting model:
	- embodiment - use iCub to match to a good extent human infant characteristics with morphology, kinematic structure and DoFs
	- situatedness - behaviour as a result of the environmental interactions on top of the agents characteristics
	- nervous system and learning process - controller is implemented with a ==neural network==, learning process is through simple trial and error (which is believed to be similar to how infants learn)
	- incrementality - cumulative phases subjected to physiological modifications due to tissue maturation + cognitive modifications

- ==experiment==: iCub robot is trained for the ability to reach and grasp a coloured ball, derived from experiments with children of 4 months of age
- ==neural controller==: uses recurrent neural network, receiving proprioceptive input from the right arm, torso and head, camera input and tactile sensor input on the right hand - all is updated every ==0.1 seconds==
- the angular position of all joints are used as neuron inputs, and neurons binarily encode whether the touch sensors detect the ball or not
- ==DOF==: 14 actuators controlling the head, torso, right arm and right hand, with a motor neuron dedicated to each
- emphasis on ==self-learning== rather than imitation - robot is rewarded for sensorial exploration and multimodal perception (i.e. both seeing and touching) - performance level is evaluated by ==min(pSight,pTouch)==
- parameters are varied randomly, then retained based on whether they lead to the maximisation of the above performance level (evolutionary method, then into ontogenetic learning)
- the three main training phases are:
	- pre-reaching phase: birth - 4 months: simple head orientation + grasping reflex behaviours (achieved through freezing certain DoFs, connection weights, and making camera acuity worse), and introducing [[motor babbling]] (extending arm, producing circular movements around area of object)
	- gross-reaching phase: 4 months - 1 year: improved camera acuity, reduced motor babbling and unfreezing DoFs, mediating reflex behaviours, and improving reaching+grasping ability
	- fine-reaching phase not modelled in experiment (additional neurons?)

# findings
- the phases described above were generally successful, with half of the trials resulting in robots managing to reach through the exhibition of exploratory behaviour in pre-reaching, then improve their reaching ability significantly in gross-reaching, ==but reduce their grasping ability==
- non developmental training with no initial reflexes found that robots were much worse than the robots at the end of the gross-reaching stage

# conclusion
- design of humanoid robot to develop relatively complex action capabilities, by modeling fundamental aspects (embodiment, situatedness, nervous system and learning, incremental development) through a developmental like system
- the papers main further aims would be identifying the scalability of such approaches, and how these early stages of development may be a prerequisite for the development of better capability later on