[[COMP37111]]
[wiki](https://en.wikipedia.org/wiki/Euler_method)
- named after Leonhard Euler, the euler method can be used to provide a linear, approximate solution to ODEs using an initial value

adapted from wikipedia:
> Consider the problem of calculating the shape of an unknown curve which starts at a given point and satisfies a given differential equation. Here, a differential equation can be thought of as a formula by which the gradient of the tangent line to the curve can be computed at any point on the curve, once the position of that point has been calculated.
> The idea is that while the curve is initially unknown, its starting point ($A_0$) is known. Then, from given differential equation, the gradient of the curve at $A_0$ can be calculated, and this gives the tangent line.
> Take a step of size $h$ along the tangent line up to a point $A_1$. Along a small step, the gradient doesn't change much, so $A_1$ should be close to the curve. Pretending that $A_1$ is still on the curve, the same reasoning as for the point $A_0$ can be used.
> After several steps, a polygonal curve $(A_0,A_1,A_2,...)$ is computed. This curve should not diverge too far from the original unknown curve, and the error between the two curves can be made small if the step size is small enough, and the computation finite

using parametric equation $X$ with parameter $t$, euler method can be described as:
- $t_1 = t_0 + h$
- $X_1 = X_0 + h f(X_0,t_0)$