[[COMP27112]]
[[COMP37111]]

- backface culling takes a facet and decides whether it is oriented towards the viewer, therefore visible, or oriented away from the viewer therefore invisible
- somewhere in the region of 50% of polygons in a scene could be culled by figuring out which ones won't actually be visible

- there are two main considerations to keep in mind when determining whether a polygon is facing towards or away from the viewer:
	1. this calculation should be relatively cheap
	2. this has to be something that can be done during the rendering pipeline

- calculating whether the polygon faces the viewer can be done by calculating the dot product of the view vector and the polygons surface normal, and checking whether the calculated value is positive or negative
- if negative, the polygon is facing away from the viewer (thus positive = facing towards the viewer)
- a slight downside is the trigonometry required for a dot product, but hardware often has the calculation available as a GPU instruction

- (an alternative method is looking at the winding? of the polygon as it is rendered onto the viewplane, though not entirely sure what this means)