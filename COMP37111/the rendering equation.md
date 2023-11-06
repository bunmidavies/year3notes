[[COMP37111]]
[wiki](https://en.wikipedia.org/wiki/Rendering_equation)

- the rendering equation describes the total amount of light emitted from point $x$ along a particular viewing direction/vector, consisting of emitted radiance + reflected radiance

$$L_o(x,\omega_o,\lambda,t) = L_e(x,\omega_o,\lambda,t) + \int_\Omega f_r(x,\omega_i,\omega_o,\lambda,t)L_i(x,\omega_i,\lambda,t)(\omega_i\cdot n)\textrm{d}\omega_i$$
- sometimes the integral on its own can be represented as $L_r$, i.e. the reflected spectral radiance
$$L_r(x,\omega_o,\lambda,t) = \int_\Omega f_r(x,\omega_i,\omega_o,\lambda,t)L_i(x,\omega_i,\lambda,t)(\omega_i\cdot n)\textrm{d}\omega_i$$
