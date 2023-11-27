[[COMP34111]]

- whether to use a constant $\alpha$ (learning rate) or a decreasing learning rate depends on the environment:
	- ==constant learning rate== - use in a changing environment - by decreasing the learning rate, the agent loses its ability to respond to changes in the environment
	- ==decreasing learning rate== - use in an unchanging environment - more precise estimations of average rewards will be produced
- in a lot of cases though, whether the environment is changing or not is unknown