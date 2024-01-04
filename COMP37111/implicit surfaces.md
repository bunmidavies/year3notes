[[COMP37111]]

- implicit surfaces simply define a surface using a singular formula - three cases then apply to determine how a point ($x,y,z$) relates to the surface:
	- $f(x,y,z) = 0$ - point is on a curve of the surface
	- $f(x,y,z) < 0$ - point is inside surface
	- $f(x,y,z) > 0$ - point is outside surface

# tradeoffs
advantages
- implicit surfaces require no 'metadata' alongside them, in comparison to a tensor product spline or mesh which will require control points or vertices respectively
- checking a points relation to the surface is super efficient, since it just needs to be plugged into the formula and one of the 3 cases stated above will apply
- weird surfaces/topologies are suitable for an implicit representation
disadvantages
- generating points of the surface is not straightforward, so actually rendering the surface can prove difficult? given the fact you just have a formula to determine whether a point is in, on or outside the surface, how exactly do you then draw this surface out? (monte carlo method perhaps?)
- since one formula is used for the whole surface, modifying the geometry isn't as straightforward as other methods - with a mesh you could just add the new vertices you'd like to be part of the surface