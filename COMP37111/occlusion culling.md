[[COMP37111]]

- occlusion culling is essentially involved in the idea that if only the z-buffer technique is used for determining which objects are 'drawn over' by other objects, performance is kind of hindered since ideally we'd want to just exclude any objects from the drawing process if we knew they'd be completely drawn over
- this problem isn't trivial to solve

- one approach which can cull some objects is the 'portal culling approach'

1. from the current viewpoint, identify any 'portals' i.e. any doors/windows through which other enclosed spaces are potentially visible - these portals may be partly or wholly visible from the current view frustum
2. for each portal, cast rays against the perimeter of the portal into the next room you can see through it
3. for each room that a ray enters, identify any other portals that are visible in the view frustum, and repeat the process
4. each room that a ray passes through has contents that are potentially visible from the original viewpoint, create a new viewing 'frustum' from the eyepoint that takes into account the frame of the portal, and repeat the process from step 1 until all visible portals are included

- the visibility of different regions within a scene can be detected more accurately with this approach, allowing the renderer to only focus on portions of the scene that are visible, saving computational resources