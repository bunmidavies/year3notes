[[COMP37111]]

- while [[traditional whitted-style raytracing]] treats light transport as though it consists of 'infinitely thin rays', radiosity goes to the other abstract extreme, treating the scene as a general exchange of energy between all objects inside it
- for this reason radiosity also has more or less opposite visual effects to ray tracing:
	- radiosity assumes all surfaces are perfect diffusers
- radiosity methods were first developed within the field of heat transfer, based on the idea of the conservation of energy, and were later refined for rendering graphics - the method name originates from ==thermodynamic radiosity== - the flux leaving a surface at point x

radiosity involves the following
- the surface is divided up into 1+ smaller surfaces called patches
- a 'form factor' is computed for each pair of patches, measuring how visible each pair of patches are to each other, in terms of angle, distance, and patches in the way
	1. identify patches associated with light sources
	2. shoot light energy into the scene from identified sources, and consider the diffuse-diffuse effect on any patches that are visible to the light source - these are target patches which accumulate light energy, which can be shot again
	3. repeat the process, starting with patches that have the most unshot energy
	4. stop when a high percentage of the initial energy is used up

- the energy values + form factors essentially give a linear system of equations, in which solving gives the radiosity i.e. brightness of each patch, taking into account diffuse interreflection and soft shadows
- ==classic radiosity== solves all these equations simultaneously, thus can be quite computationally heavy, but once we have the final solution we have a complete diffusely rendered scene
- ==progressive radiosity== can apply the 'bouncing' of energy iteratively, such that we can get a preview of the rendering after 1 or 2 bounces - we can thus stop rendering prematurely if we think the scene looks good enough rather than wait for convergence
- ==shooting radiosity== will shoot light from the patch with the most energy at each step - with each step, only patches in the direct line of sight of the patch shooting energy will be illuminated, and this repeats until a steady state is reached

- radiosity $B$ of a smaller area of a patch $\delta A_i$ at point $x$ can be described as such:
	$$B(x)\delta A = E(x)\delta A + \rho (x) \delta A \int_S B(x')\cdot F(x,x')\delta A'$$
- $E$ = emitted energy of point on patch
- $\rho (x)$ = reflectivity of point
- $S$ = all surfaces in the scene, where $x'$ represents the point on the other surface
- $B(x')$ = radiosity of the other point
- $F(x,x')$ is the form factor of $x$ to $x'$ (1 if completely visible, 0 if completely invisible to each other)
- thus you have the energy emitted from the point + reflected energy from the point (by taking into account all incoming energy from other points)
![499](https://i.imgur.com/jjzKmUo.png)
- like the rendering equation, this infinite recursion means analytically solving such an equation will not be possible
- to fix this, we have the discrete radiosity equation, which solves a radiosity value ==per patch==
$$B_i = E_i + \rho_i\sum_{j=1}^n B_j F_{ij}$$
- where we have $i$ patches

# tradeoffs
- one of the main issues with radiosity, mostly to do with patches, is that we have no initial idea of how patches should be generated - we don't know how the scene should be split up in a discrete sense. If we create too many patches we're going to waste our time, but if we don't create enough or don't focus on the right points we'll miss subtle lighting effects
- one workaround to above is to use some cheap ray tracing beforehand just to figure out where the 'action' in the scene is happening, and what interesting effects are where - then, we can place patches accordingly, with more patches in more 'interesting' areas
- tiny flaws in original polygonal meshes can give holes in the environment, causing energy to leak out, giving darker results than expected
- radiosity is excellent for scenes with primarily diffuse surfaces, and can typically generate more realistic looking shadows than those within [[traditional whitted-style raytracing]]
- radiosity is also view independent, which can allow you to bake the result into a texture which can just be mapped to some model, allowing considerable speedups in realtime rendering, and any interactive applications e.g. games