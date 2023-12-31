[[COMP24011]]

search algorithms require a data structure to keep track of the search tree that is being constructed, and are used to solve [[inference tasks]]

for each node in the tree, a structure should contain the following:
- ==state== - the state of the node
- ==parent== - the node which generated this current node
- ==action== - the action that was applied to the parent to generate this node
- ==path-cost== - the cost, traditionally noted $g(n)$

these nodes can then be stored within a ==queue== - there are 3 main types of queue:
- ==LIFO== - also known as a stack
- ==FIFO== - the traditional queue
- ==priority queue== - some arbitrary ordering function sorts the queue

==explored sets== for search algorithms can be implemented with ==hash tables== ([[COMP26120]]), and insert/lookup operations for these are typically ==constant==

basic search strategies are also known as ==uninformed== or ==blind== search algorithms - these algorithms have ==no additional info== about states beyond what is provided in the problem definition

search strategies that are ==informed== use problem specific knowledge, making them more efficient in finding solutions - these typically involve ==heuristic functions== or ==evaluation functions== to determine what is "best" in a search tree

examples of informed searches include: [[A* search]]

### Breadth-first search / BFS
in BFS, the root node is expanded first, then all successors are expanded, etc.

the ==FIFO queue== is used to represent the frontier in a BFS search

in the worst case with a search tree having $b$ successor nodes for each node, and a depth $d$ - $b^d$ nodes have to be generated by this search, thus determining the ==time== and ==space complexity==

the main drawback of BFS is the ==memory requirements== - when all step costs within a search tree are ==equal==, BFS is ==optimal==

### Depth-first search / DFS
in DFS, the ==deepest== node is always expanded first

the ==LIFO queue== is used to represent the frontier in a DFS search

DFS looks for the ==first== solution in a planning problem, and will return it once found, thus it is not ==optimal==

DFS beats BFS in terms of ==space complexity== - it only ever needs to store one path at any given time, which is a max of `depth` nodes - for this reason, DFS is found useful in [[constraint satisfaction]]

depth-first search can be stopped from failing in infinite state spaces by introducing a predetermined depth limit - this is the ==depth-limited search== (note that for the reason that there is a max depth, this search cannot guarantee ==completeness==)