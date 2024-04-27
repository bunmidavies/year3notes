[[COMP34212]]

- Evolutionary Robotics is a biology inspired method for automatic robotic development - the method also is useful in 
- *Evolutionary Robotics is the ==automatic design== of robots and of their sensorimotor control systems through an ==evolutionary computation== process* (Nolfi & Floreano, 2000)


# adaptation + co-evolution

- *an adaptation in one lineage (e.g. predators) may change the selection pressure on another lineage (e.g. prey), giving rise to a counter-adaptation. If this occurs reciprocally, an unstable runaway escalation of 'arm races' may result* (Dawkins and Krebs, 1979)
- In evolutionary robotics, adaptations can produce a training process where one population progresses due to the gradual complexification of the adaptive task, which is caused by parallel progress in some competing population
- example: [co-evolution of two khepera species](https://www.researchgate.net/profile/Luca_Simione/publication/322998553_Achieving_long-term_progress_in_competitive_co-evolution/links/5b505f140f7e9b240fed31fd/Achieving-long-term-progress-in-competitive-co-evolution.pdf)

- the benefits of co-evolution includes:
	- selecting the most effective solutions based on competing population
	- solutions are selected in order to match counter-strategies
	- complexity of robots increases, without having to increase the supervision
![500](https://i.imgur.com/xibZhA7.png)


# genetic algorithm example

- a computational model of Darwin's Natural Selection
![](https://i.imgur.com/m8b7w7A.png)

- the genotype can be thought of as computer code, which gives way to some phenotype, which is the model that results from that code (e.g. DNN model)

# Example: khepera

# Example: iCub EvoRobot

- the robot uses the FARSA simulator - a collection of open-source C++ libraries for evolutionary experiments with robots