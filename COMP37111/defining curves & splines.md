[[COMP37111]]

- there are two main ways a curve can be defined:
	1. a continuous 1D set of points in 2D or 3D - this definition allows you to easily generate points along a curve and define a basic shape
	2. a mapping from an interval $S$ onto a plane - this definition allows us to describe trajectories and manipulate the speed at which we traverse the curve

- a set of points is easy to imagine

- an example mapping function could look like:
$$P : \mathbb{R} \in S \rightarrow \mathbb{R}^2, P(t) = \begin{pmatrix} x(t) \\ y(t)\end{pmatrix}$$

- a spline in graphics can be thought of as a function representing a smooth curve that is defined by a number of control points
- multiple types of splines exist, varying in the mathematical functions used and their properties 