[[COMP37111]]

- bicubic bezier surfaces work relatively similar to [[bezier curves]], with two main differences:
	- rather than a single parameter $t$, 2 dimensions of parameters are used i.e. $u,v$ - both of these have their own, separate bernstein basis polynomials
	- instead of a single set of control points, a ==2D grid of control points are used==, hence indexing $i,j$ is required
- the equation for a bicubic bezier surface $S$ can be written as follows
$$S(u,v) = \sum_{i=0}^3\sum_{j=0}^3 P_{i,j} \cdot B_{i,3}(u) \cdot B_{j,3}(v)$$
- the lectures write this in a similar manner, just moving the $u$ component outwards?
![200](https://i.imgur.com/ejcVC5b.png)
- note that the word ==patch== is more or less synonymous with surface
- the matrix representation of the surface uses a point $x$ in 3D space - chatGPT claims this is used as a homogenous coordinate making other transformations easier, but it doesn't seem exactly clear what this does, just that it is required for the control points?
![](https://i.imgur.com/CyhSHR1.png)
- transposes are for dimensions to match up for multiplication