[[COMP34212]]

# iconic localisation

- iconic localisation involves raw sensor readings to match actual observations to expected observations - the computation involved with this method is high since many sensor readings need to be taken
- iconic localisation is a grid-based method, since the world is partitioned into a tesselation of convex polygons, and the likelihood of possible poses within each polygon is calculated

# monte carlo localisation

- particles/sample poses are scattered throughout some space
- the belief that the robot is within one of these poses is calculated, and over time more 'particles' i.e. poses are added while others are removed if they have a low belief associated with them