[[COMP37111]]
[iris dynamics](https://irisdynamics.com/articles/forward-and-inverse-kinematics)

- ==forward kinematics== - the calculation of the position/orientation of an effector i.e. the the body part at the end of some bone (?), using only the angles of said effectors
- this allows animators to simply provide angles of bones, and allow a computer to determine the actual position

- ==inverse kinematics== - the reverse of forward kinematics (i.e. backwards kinematics) - given the effector end position, the joint angles are calculated
- therefore, animators in this scenario provide positions of effectors and a computer calculates the angles at which effectors join at

- forward/inverse kinematics are also important in robotics - it can be used to tell you how to move a robotic arm to reach some point in space, and vice versa