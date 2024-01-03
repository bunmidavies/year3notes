[[COMP37111]]

- bezier curves can be represented as a combination of 3 matrices:
$$GBT(t) = \textrm{Geometry} \times \textrm{Spline Basis} \times \textrm{Power Basis}$$

- geometry = control points
- spline basis aka $B$ = coefficients of bernstein polynomials
- power basis = $1,t,t^2,...,t^n$ where 

- we can easily go to and from $t$ and $B(t)$ using the inverse of the $B$ matrix:
![](https://i.imgur.com/t8PiGia.png)
- $B_i(t)$ simply gives us the final vector we'd need, all we do is just plug in the t values - then by performing matrix multiplication against the geometry matrix, we'll get a resulting vector with dimensions required - in the case below, you'll end up with a 2x1 matrix (i.e. x/y vector)
![](https://i.imgur.com/O4RD1KU.png)
