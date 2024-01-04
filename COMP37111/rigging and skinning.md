[[COMP37111]]

# rigging
- ==rigging== = building 3D models by using hierarchical bone structures, where different bones/joints move in part with each other 
# skinning
- ==skinning== = associating a characters geometry/mesh with bones and deforming the geometry accordingly, based on how the bones move - one of the most common techniques is ==skeleton subspace deformation (SSD)==
- by using skinning, an animator does not have to focus on moving every single vertex within a polygonal mesh, but instead can just move bones how they want
- typically, parts of the body closer to joints aren't moving purely based off one bone - it is more common to use some weighted combination of bones involved in order to manipulate surrounding skin, or in this case the surrounding mesh
- in the photo below, the black triangles on the right indicate facets that are dependent on more than one bone in order to deform
![300](https://i.imgur.com/AceuWI7.png)
- formally, a vertex $v_i$ will have a set of bones $b_j$ and according weights for each bone $w_{ij}$ - we say that if $w_{ij}$ is 1, then vertex $v_i$ is ==rigidly attached== to bone $b_j$
- these weights must be non-negative, and the sum of all weights for one vertex should be 1

- the matrix transformation for deforming some vertex based off a bone movement is as follows:
$$p'_{ij} = T_jB^{-1}_j p_i$$
- $p_i$ is the position of the vertex in world space
- $B^{-1}_j$ is the bone transformation (?)
- $T_j$ is the transformation required to go from local bone space to world space (?)