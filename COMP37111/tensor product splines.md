[[COMP37111]]

- tensor product splines can be simply thought of as parametric curves, and the two terms may actually be used interchangeably at times
- we can essentially build up a surface from previously discussed splines such as [[bezier curves]],taking the product of polynomials in 2 separate directions, using 2 parameters - a 2D grid of control points can be used so that one is essentially interpolating/approximating a point with 2 dimensions
![](https://i.imgur.com/VhMAsKZ.png)
- the black curves and dotted red curves can be defined using the same control points, while using different parameters to control at what point along the two curves a single point is i.e. $u$ and $v$
- in the example below, we have 16 control points defining 8 curves (if control points weren't shared we'd need 8x4=32 control points) 
![300](https://i.imgur.com/h5aZdgq.png)
- the most common type of tensor product spline covered is the [[bicubic bezier surface]]
- the ==product== in tensor product splines comes from the fact that the two parameters will both have their own bernstein basis functions/polynomials, and the two dimensions are multiplied alongside the corresponding control point

# tradeoffs
there is one main advantage of tensor product spilnes
- if you were to explicitly define surfaces defined by tensor product splines, you'd require a much larger number of vertices - curves in the tensor product spline can share control points, and since everything is interpolated+approximated with parameters, a large amount of storage is saved

this comes at some disadvantages
- tensor product splines are harder to render, since a conversion to mesh form will be required at some point
- ensuring continuity at patch boundaries can also be not so straightforward