[[COMP24011]]
[[COMP34212]]

- translational dof = translation in x, y, z
- rotational dof = rotation in x, y, z - roll, pitch, yaw

- bodies will have theoretical total DoF, alongside their controllable DoF (what they can actually influence) - uncontrollable DoF create problems for the controller in that they make movement more complicated

- Total/Controllable ratio
	- holonomic: controllable = total (e.g. helicopter)
	- non-holonomic: controllable < total (e.g. car)
	- redundant: controllable > total (e.g. arm)