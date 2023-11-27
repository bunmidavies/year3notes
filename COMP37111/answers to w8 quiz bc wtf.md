[[COMP37111]]

## Question 1
- Raytracing inherently produces the following effects:
	- Specular highlights
	- Reflection
	- Refraction
	- Hard Shadows
	- Participating Media (i.e. fog, smoke)
	- Depth of Field
## Question 2
- Radiosity naturally produces:
	- diffuse reflection
	- soft shadows
	- colour bleed
## Question 3
- Path tracing can handle all effects mentioned
## Question 4
- The rendering equation with only a BRDF can handle the following effects:
	- specular highlights
	- reflection
	- colour blend
	- penumbral shadows
	- umbral shadows
	- diffuse interreflection
## Question 5
- texture baking can approximate the following effects, given the viewpoint is moving:
	- colour bleed
	- soft shadows
	- hard shadows
	- diffuse interreflection
## Question 6
- insufficient samples per pixel within path tracing can result in images which are both noisy and innaccurate
## Question 7
- path tracing becomes more computationally complex based on the size of the viewplane
## Question 8
- Radiosity is viewpoint independent
- Texture baking is viewpoint independent, since you essentially perform the rendering properly once and forever use that same result