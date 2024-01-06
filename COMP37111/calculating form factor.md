[[COMP37111]]

- the form factor $F_{ij}$ between patches $i$ and $j$ takes into account 3 main things:
	1. distance between the two patches + orientation between one another
	2. the shape of the two patches when projected onto one another
	3. the effect of any objects that get in the way of the two patches, causing shadows or affecting transmission of energy

- to get a factor of point 1, we have a simple equation which allows us to do such
$$\frac{1}{\pi r^2} \cos\theta_x \cos\theta_{x'}$$

- ==nusselt analogue== is one of the most intuitive ways for calculating the 'projected shape' of one patch onto the other e.g. $A_i$ and $A_j$ - it involves:
	1. projecting plane $i$ onto the surface of a unit hemisphere
	2. projecting the previous projection onto a 2D unit circle around the point of interest on plane $j$, on the surface
	3. the value is then equal to the differential area of $A_i$ times the proportion of the unit circle covered by the projection
![350](https://i.imgur.com/ehs5s5q.png)


- the occlusion bit (point 3) is more complex and mathematically less elegant - early methods of calculating this involved a hemicube divided into pixel-like squares. This hemicube could sit on a surface, and when trying to project one patch onto another, one could figure out which pixels within the hemicube were being blocked, by sort of treating it like a z-buffer
- another method which is less computationally complex involved binary space partitioning trees
- typically, the complexity for determining form factor scales as $O(nlog(n))$
- the main issue with the hemicube is that its too discrete - assuming that patches will project onto an integer number of pixels