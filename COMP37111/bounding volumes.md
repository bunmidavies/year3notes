[[COMP37111]]

- since collision detection for $n$ dynamic objects scales badly - $O(n^2)$ - it can be more efficient for dynamic objects to be represented using simpler objects, e.g. a cube/sphere
- it will be much faster to check if these simpler objects are colliding with each other
- examples include:
	- ==axis aligned bounding boxes (aabb)== - axis aligned essentially just means the boxes aren't rotated, and are parallel to the x,y,z axes
	- ==oriented bounding boxes== - essentially aabb, except without the axis alignment since the boxes can be oriented as needed
	- ==bounding spheres== - slightly harder to calculate collision, but invariant to rotation of the actual object the sphere is representing
	- ==k-DOP== - DOP = discrete oriented polytype (facet/face), k-sided bounding volume, essentially (the higher k is, the more accurate the volume is, but more computation is required)

- volumes can also be arranged in a hierarchical manner, which is useful for determining whether two objects are in close proximity to each other, which is useful for both rendering and collision