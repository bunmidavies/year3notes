[[COMP37111]]
[wiki](https://en.wikipedia.org/wiki/Rendering_equation)

- the rendering equation describes the total amount of light emitted from point $x$ along a particular viewing direction/vector, consisting of emitted radiance + reflected radiance

$$L_o(x,\omega_o,\lambda,t) = L_e(x,\omega_o,\lambda,t) + \int_\Omega f_r(x,\omega_i,\omega_o,\lambda,t)L_i(x,\omega_i,\lambda,t)(-\omega_i\cdot n)\textrm{d}\omega_i$$
- $L_o$ can be thought of as the light that reaches the viewer, or the spectral radiance reaching the viewpoint from point x along direction $\omega_o$
- $\omega_o$ represents the direction from the point $x$ to the viewpoint
- $L_e$ is the emitted radiance from point $x$ along $w_o$ - a lightbulb for instance will be emitting light
- $w_i$ represents each 'ray' of light coming in from an infinite number of angles within a hemisphere centred at point x 
- $f_r$ is the [[BRDF]]
- $L_i$ is the incident light hitting point $x$ from current direction of concern, $\omega_i$
- $(-\omega_i\cdot n)$, i.e. the dot product of the incident ray direction and surface normal - this will attenuate (reduce) the incoming light based on the angle at which $w_i$ hits the surface

- sometimes the integral on its own can be represented as $L_r$, i.e. the reflected spectral radiance
$$L_r(x,\omega_o,\lambda,t) = \int_\Omega f_r(x,\omega_i,\omega_o,\lambda,t)L_i(x,\omega_i,\lambda,t)(\omega_i\cdot n)\textrm{d}\omega_i$$
![300](https://i.imgur.com/2UgTfvD.png)

- ==the rendering equation is spatially homogenous== - this means it can be applied to all points of a scene regardless of their position or orientation
- however, the rendering equation is a Fredholm equation of the second kind - there is no analytical solution for it as of now, and part of the reason for this is that it is infinitely recursive
- this is modern graphics summed up - we can never analytically solve this thing, so we have to cut corners to make approximations