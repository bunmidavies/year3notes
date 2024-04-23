[[COMP35112]]

- commonly used for purposes outside of speculation, polyhedral transformations can be described as transformations on a representation of dependencies within a 2D plane
![](https://i.imgur.com/oU3374u.png)
- arrows are used to represent what iteration depends on what, and this example is a nested loop (hence i and j)
- an exemplar polyhedral transformation could simplify dependencies by skewing the plane
![](https://i.imgur.com/LfOAQUc.png)
- obtaining this space can then be achieved by altering i/j based on additional variables
- another transformation can be performed, by swapping the i/j axes
![](https://i.imgur.com/KsPIVy2.png)

- polyhedral transformations have the following requirements:
	- loop variables to be known at compile time
	- array indices to be a linear function of the loop variables