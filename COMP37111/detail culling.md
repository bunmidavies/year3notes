[[COMP37111]]

- the basic idea behind detail culling is to just not bother drawing things that are too small (to the viewer) to have a perceivable effect on the final scene
- this can be a tiny object not that far away, or a huge object way too far away
- all that needs to be determined is the size of the object when projected onto the viewplane, using trigonomtery based on the bounding cubes of the object
- detail culling is particularly effective for moving scenes, since the tiny bits of lost detail are much less likely to be noticed