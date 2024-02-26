[[COMP35112]]

- lock-free data structures can be accessed concurrently without locks through the use of atomic instructions, involving lists, stacks etc.
- these are generally difficult to implement, since updating their state requires more than a single memory store operation done by RMW instructions
- its also difficult to know when a member of the data structure can be freed on languages with no garbage collection
- the main benefit is that they can be faster than lock-based data structures