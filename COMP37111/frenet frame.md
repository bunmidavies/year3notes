[[COMP37111]]
[statisticshowto]https://www.statisticshowto.com/frenet-frame/)

- a frenet frame is a moving right-handed coordinate system determined by the tangent line of a curve and its curvature - the frame locally describes a point on a curve and changes orientation along the curve
- the frenet frame is made up of 3 vectors:
	- $T$ - unit tangent vector (unit = magnitude of 1), goes in the direction of whatevers being modelled
	- $N$ - unit normal, first derivative of the tangent vector, divided by its length (to become unit vector), indicating the direction in which the curve is turning
	- $B$ - binormal, i.e. $T \times N$, cross product of tangent and normal