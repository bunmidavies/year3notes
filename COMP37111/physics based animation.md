[[COMP37111]]

- physics based animation is essentially the simulation of physical systems, similar in some sense to [[procedural animation]] in which individual frames are not specified, but more concerned with assigning physical properties to objects within a scene, applying forces and solving equations within the system

# particle systems
- commonly used for making smoke, water, fire, sparks etc, particle systems somewhat border procedural and physics-based animation
- particles are typically independent, and do not interact with each other
- particles are typically spawned by emitters - then, external forces such as gravity and wind can be described - finally, the laws of mechanics (ODEs) make the particles move

# mass spring models
- ideal for cloth simulation - somewhat of a parallel to particle systems, mass spring systems contain a collection of particles which are connected with springs 
- a number of forces such as the spring forces themselves, gravity, spatial fields and damping forces are to be considered
- the spring force is a ==structural force== within the system, responsible for maintaining particles joined together at a constant distance from each other while stationary
![](https://i.imgur.com/5aGbThq.png)
- $K$ is the stiffness of the spring
- $P_i$ and $P_j$ experience the same magnitude of force, just in opposite directions