[[COMP37111]]

- Non-Uniform Rational Basis Spline (NURBS) bring more intuition and versatility to the table, employing homogenous coordinates represented by adding a weight to each control point
- in reality, we now have ==knots== and ==weights== rather than control points - the weights define how much control each of the knots have
- the technical implementations of NURBS are beyond the scope of the course, but in short, NURBS curves are generalisations of both bezier curves and b-splines

- NURBS are very popular within computer graphics, for various reasons:
	- geometric flexibility, being able to represent both simple and complex curves and surfaces
	- mathematical precision, allowing for accurate interpolation+approximation of complex shapes
	- intuition for designers through the use of knots and weights (or also called control points and a knot vector)
	- the ability to represent both polynomial curves as well as rational curves
	- NURBS have become an industry standard in various fields