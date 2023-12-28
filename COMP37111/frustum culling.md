[[COMP37111]]

- the viewing volume i.e. viewing frustum will have objects that lie on the boundary of the frustum. These objects can be cut into pieces through a process called [[clipping (viewport)]], and then the pieces that lie outside of the frustum can be discarded as there is no place to draw them
- spacial enumeration techniques can be used in order to determine which polygons/objects are candidates for culling