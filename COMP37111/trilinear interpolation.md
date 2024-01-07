[[COMP37111]]

- within [[direct volume rendering]], as we pass through voxels when casting rays, we could just use the value of the voxel being passed through - however, this can lead to anti-aliasing effects, so interpolating values from neighbouring pixels in 3D can be useful for getting a more representative sample value
![300](https://i.imgur.com/XbEMLoU.png)
