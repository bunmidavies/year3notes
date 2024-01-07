[[COMP37111]]

- direct volume rendering creates images by casting rays into a volume set - much like [[traditional whitted-style raytracing]], these are shot out through some eye point, pixel by pixel
- thus, like ray tracing, it is ==viewpoint dependent==
- unlike ray tracing, instead of bouncing off surfaces/spawning new rays, we intersect the scene 'into' the data, accumulating all effects of colour and transparency along the ray to figure out what colour the origin pixel should have
- note that since these 3d volume sets can have arbitrary values, we're determining the colour based on values but the final colour will sort of be down to us - colour/opacity values for each of the voxels must be defined
- determining 'materials' i.e. separate colours per voxel value can be done through a variety of methods, but one intuitive method is through producing a histogram for voxel values within the data set - by finding isolated peaks within the graphs, we can possibly classify those set of voxel values as materials, and assign a distinct colour for each material
- additionally, opacity values can be assigned per material to decide what materials we want to be visible or invisible - if we're rendering some part of the human body with both bone and tissue, we might want to set the opacity of the tissue material to 0, and keep the bone opacity as 1
![450](https://i.imgur.com/oogwB4E.png)
- to figure out the point for a specific pixel, a simple algorithm is followed:
	- shoot out ray per pixel (or multiple and average out, for now we consider one ray per pixel) into the scene, which has an accumulated colour and opacity of 0 - also define a 'terminal opacity'
	- when this ray intersects a voxel, add the voxels opacity and a certain amount of colour value (based on how much opacity there is 'left' to contribute to the pixel) to the accumulated opacity and colour respectively, then move to the next voxel
	- perform as long as accumulated opacity is less than the terminal opacity, and the ray is still inside the volume
- to calculate the colour to be added while taking into account the opacity remaining, the following equation is used 
```python
accum_colour += (1-accum_opacity) * opacity * colour
```
- the entire pseudocode is as so:
```python
accum_colour= 0; 
accum_opacity= 0; 
/* find first sample point inside the volume */ 
while ((accum_opacity < terminal_opacity) 
	&& (sample_point_inside_volume)) 
	{ 
	/* eval colour and opacity at sample point */ 
	accum_colour+= (1-accum_opacity) * opacity * colour; 
	accum_opacity+= opacity; 
	/* step to next sample point */
}

```

- the results of direct volume rendering somewhat resemble x-ray photography, but there is an absence of local surface shading, thus images look a bit flat
- however, faux surface normals can be created through interpreting changes in voxel values as sort of directions - this can be plugged into a local illumination calculation to give some surface shading, without actual surfaces