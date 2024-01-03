[[COMP37111]]

- the most convenient way to convert between b-spline and bezier is through using the matrix form of representing parametric curves, i.e. $P(t) = GBT(t)$
- if we define our bezier basis coefficients as $B_1$, and our b-spline basis coefficients as $B_2$, and our bezier control points and b-spline control points as $G_1$ and $G_2$ respectively, we can convert $G_1$ to $G_2$ using $B_1$ and $B_2$
- the transformation above essentially allows us to define the same curve in both bezier and b-spline form

![300](https://i.imgur.com/jwx6NQo.png)
