[[COMP37111]]

the recursive algorithm to generate a BSP tree from a list of polygons is:
1. choose polygon $P$ from list
2. make a node $N$ in BSP tree, and add $P$ to list of polygons in node $N$
3. for each other polygon $Pi$ in the list
	a) if $Pi$ is wholly in front of the plane containing $P$, move $Pi$ to the list of nodes in front of polygon $P$
	b) if $Pi$ is wholly behind the plane containing $P$, move $Pi$ to the list of nodes behind $P$
	c) if $Pi$ intersects the plane containing $P$, split it into two polygons and move them to the respective lists of polygons behind and in front of $P$
	d) if $Pi$ lies in the plane containing $P$, add it to the list of polygons at node $N$
4. apply this algorithm to the list of polygons in front of $P$
5. apply this algorithm to the list of polygons behind $P$

note that the notion of 'front'/'behind' is basically decided by the algorithm and probably only makes more sense when visualising

![](https://i.imgur.com/mvhGqSm.png)
![](https://i.imgur.com/Gl0U40e.png)

- note that since polygons also end up getting split within the binary space partitioning algorithm, you'll probably end up with more nodes/polygons within the tree than there were initial polygons in the scene
- it is desirable for this increase to be minimised, and that the final tree is relatively balanced (in order for traversal to be efficient and exploit the benefits of a balanced tree structure)
- ==for reasons above, the first selected polygon is relatively important== - should be more or less in the middle of the scene?