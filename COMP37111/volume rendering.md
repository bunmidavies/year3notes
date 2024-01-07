[[COMP37111]]

- volume rendering exists in order for the 'inside' of surfaces - for the majority of rendering forms, we're typically not concerned with this, but it can be useful for a number of purposes
- ==volume rendering requires a 3D array/data set of points== - examples of this in medical applicatoins include CT, MRI and MicroCT scans, and in geographical contexts includes sonar/ground penetrating radar scans - these are also known as ==volume sets==, with each particular 3D cell of data being known as a ==voxel==
- the two main methods of volume rendering are:
	- [[direct volume rendering]]
	- [[indirect volume rendering (marching cubes)]]