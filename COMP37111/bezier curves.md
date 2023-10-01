[[COMP37111]]
[wiki](https://en.wikipedia.org/wiki/B%C3%A9zier_curve)
[primer to bezier curves](https://pomax.github.io/bezierinfo/#introduction)

- a bezier curve is defined by a number of control points, and the curve itself is influenced by these points
- bezier curves themselves are a type of ==parametric function== - typically, a parameter $t$ is used in both the calculation of the $x$ and $y$ coordinates of some curve
- this means that the $y$ of the curve doesn't rely on $x$, and vice versa
- bezier curves are polynomials of $t$, and that polynomial is known as the basis function