[[COMP37111]]

- indirect volume rendering essentially involves converting volume data into polygons, which can then be rendered much quickly in comparison to [[direct volume rendering]] methods (since hardware is at a point where direct volume rendering is slow, but the regular polygon stuff is still fast)

## isosurfaces
- isosurfaces are essentially just the 3D equivalent of contour lines (i.e. used for terrain height, barometric pressure in weather forecasts)
- building up isosurfaces can be difficult - the marching cubes algorithm is typically used for this, essentially building up surfaces out of triangles connecting a number of sampled points:
	- start with a cube, with 8 points on its edges - there are a number of different 'configurations' i.e. triangles that can be built based on the configuration of these points
	- based on whether a point passes some threshold you want to set for your isosurface, the point will either have a value of 0 or 1
	- you iterate over all data points in a cube like fashion, building up vertices which connect onto each other in order to build the surface - interpolation can also be added here to make surfaces more accurate

## proxy geometry
- proxy geometry involves stacking up layers of scans such that when you view from a certain angle, multiple layers become visible