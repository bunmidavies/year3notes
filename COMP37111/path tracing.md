[[COMP37111]]

- the path tracing algorithm takes a similar approach to [[traditional whitted-style raytracing]], but what is done when a ray hits a surface differs:
	1. fire a ray from the eye point through a pixel - if the ray flies through the scene without colliding with anything, there is nothing to be drawn for that pixel
	2. if the ray hits a surface, shadow feelers are sent out as normal - additionally, a new ray is fired out ==stochastically== - it can take into account the light scattering properties of the surface material, but in general can be referred to as having a new ray shot out in a random direction
	3. this repeats until some maximum recursion depth is reached, or the ray flies out the scene, etc. - all previous depths are taken into account and the final colour of the pixel is determined

- a number of samples per pixel can be chosen for a path traced image - this just determines how many rays we're firing out at random per pixel
- ==a low sample count will render very quickly but be very noisy==

- path tracing can simulate both depth of field and motion blur:
	- for depth of field, instead of shooting out rays from one single viewpoint - the viewpoint is slightly altered in position and direction to create a blur effect
	- for motion blur, each ray fired out can be assigned a random time within the interval the shutter is open - then, any moving of deforming objects have to be transformed according to the current time of the ray, in order toSS