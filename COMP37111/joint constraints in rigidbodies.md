[[COMP37111]]

# example
- all rigidbodies have 6 DOF (x,y,z, rotation in x,y,z)
- if we join 2 rigidbodies at one joint, we must subtract degrees of freedom:
![300](https://i.imgur.com/wf97aYh.png)
	- we lose 2 degrees of freedom in losing the ability for either rigidbody to rotate in one axis 
	- we lose 3 degrees of freedom since the 2 rigidbodies cannot move independently in their x,y,z axes - it can only move as one whole piece in the x,y,z
	- thus we are left with 6 + 6 - 2 - 3 = ==7 DOF==