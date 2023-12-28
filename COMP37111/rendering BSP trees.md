[[COMP37111]]

- to render BSP trees, the tree must be traversed in linear time, in an ordered determined by the function of the tree
- for instance, with the painters algorithm, to draw polygon $P$, the order to draw the polygons go: behind $P$ $\rightarrow$ $P$ itself $\rightarrow$ in front of $P$
- following the correct order is required to render an entire scene

the following recursive algorithm is used to render a BSP tree from viewpoint $V$

1. if the current node is a leaf node - render all polygons at the current node
2. otherwise, if viewpoint $V$ is in front of the current node:
	a) render the child BSP tree containing polygons behind the current node
	b) render the polygons at the current node
	c) render the child BSP tree containing polygons in front of the current node
3. otherwise, if viewpoint $V$ is behind the current node:
	a) render the child BSP tree containing polygons in front of the current node
	b) render the polygons at the current node
	c) render the child BSP tree containing polygons behind the current node
4. otherwise, viewpoint $V$ must be exactly on the plane associated with current node, therefore:
	a) render the child BSP tree containing polygons in front of the current node
	b) render the child BSP tree containing polygons behind the current node