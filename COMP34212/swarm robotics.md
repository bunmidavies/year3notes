[[COMP34212]]

- *"Swarm robotics is the study of how independent robots can interact as a **group**, giving rise to **collective behaviour** that a single such robot could not achieve on its own"* - Dorigo et al. 2014; Heinrich et al. 2020
- swarm robotics aims to provide maximal scalability, using a strictly decentralized approach, and limited communication
- due to there also being more than one robot in the system, a sense of fault-tolerance is exhibited by this introduced redundancy

# micro vs macro interactions/structures

- ==self organisation== within robots is the result of macroscale (global, system wide) spatial/temporal structures are formed as the result of microscale (local/peer-to-peer) interactions
- biological examples: Rayleigh-Benard convection, cell differentiation, embryogenesis, reaction-diffusion

# principles of self-organisation

- positive and negative feedback
- fluctuations (i.e. random events)
- multiple microscale interactions

# examples + applications

- ant colony optimisation (ACO)
  real ants are capable of finding the shortest path from a food source to the nest without visual clues - indirect communication occurs through stigmergy. Ants deposit certain amounts of pheromone while walking to form a trail, which each ant prefers to follow
  applicable to traveling salesperson problem, using artificial ants which have some memory, aren't completely blind, and treat time discretely


	

- kilbot - large scale swarm
- disaster relief
- lagoon monitoring
- swarm of quadrotor UAVs for agriculture purposes ("SAGA")