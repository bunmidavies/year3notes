[[COMP37111]]

- deformable object simulation can be thought of as a sort of opposite to rigidbody simulation - objects are (obviously) deformable and elastic
- a common technique for deformable object simulation is the ==Finite Element Method (FEM)==

# Finite Element Method (FEM)
- for FEM, a regular object mesh is converted to the equivalent shape made of tetrahedrals - this is known as ==tetrahedralization== 
- tetrahedrals are the most straightforward object for FEM, but are also appealing for other reasons including:
	- geometric flexibility
	- adaptability to curved boundaries
- FEM then allows us to calculate what forces are required for:
	a) deforming the tetrahedron
	b) returning the tetrahedron to its rest shape