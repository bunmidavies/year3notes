[[COMP34212]]

- SLAM = Simultaneous Localisation and Mapping
- example: Rao-Blackwellized Particle Filter: each particle presents a path and a local map - at each observation, only the sensed area of the maps are updated, and the belief of each particle is computed. A tree is then used to save all the particles that form the history of the current set of particles
- loop closure is useful for checking and adjusting the map for misalignments, and the path will likely propagate backwards, improving the overall map