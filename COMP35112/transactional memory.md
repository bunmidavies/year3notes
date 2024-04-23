[[COMP35112]]

- transactional memory is often applied on mostly parallel code, to allow it to run fully in parallel 
- the fundamental idea behind transactional memory is transactions, similar to those used in files and databases

- transactions will handle the resource sharing mechanisms required in order to prevent illegal operations - instead of using locks, the operations can be monitored to see if they interfere with each other
- transactional memory is as easy to program as coarse-grain locks, while being as efficient - if not more efficient - than fine-grain locks

# transaction properties

transactions typically follow ACID properties
- atomicity: transactions either happen, or they do not happen
- consistency: one valid state leads to another valid state
- isolation: transactions do not leak any information
- durability: once committed, the outcome of the transaction endures

==for TM, only atomicity and isolation are significant==:
- transactions are ==indivisible==, meaning for external observers, they either happen or not - all data races are eliminated by this property:
	- while executing, changes inside the transaction are not visible outside
	- once executed, all changes become visible outside and at the same time
	- if the transaction fails, then no sign of this is visible

# TM mechanisms

- to provide atomicity and isolation, TM enforces versioning and conflict detection - these mechanisms can be enforced in a ==eager== or ==lazy== manner

### versioning
- multiple versions are maintained due to speculative writes being possible

- ==eager versioning== is also known as direct update/undo-log based - variables are directly updated, but old values are kept in a log. When committing, the log is deleted, but if a commit is aborted, the original value is restored with use of the log
- this means that writes essentially become visible, and isolation is only exhibited through validation

- ==lazy versioning== is also known as deferred update/write-buffer based - variables are not directly updated, but instead a private version is kept and updated
- when committing, the private version is copied to the original shared variable - abortion simply involves deleting the private version

- in short:
	- eager versioning = very fast commit, very slow abort (efficient when aborts are rare)
	- lazy versioning = slow commit, fast abort (efficient when aborts are not rare (but not common?))

### conflict detection
- conflicts are detected to maintain atomicity and/or isolation
- two sets are used to keep track of variables
	- read-set: keeps track of shared variables that have been read
	- write-set: keeps track of shared variables that have been written to

- ==eager validation== is a form of pessimistic detection, where every read/write operation checks the sets to see if other transactions have involved the shared variable
- when a conflict occurs, the thread performing the earlier operation aborts & restarts
- an issue is that it is possible for threads to livelock with each other - if thread 1 reads+writes variable X, then thread 2 later on reads+writes variable X, thread 1 restarts only to then cause thread 2 to restart, and this repeats indefinitely

- ==lazy validation== is a form of optimistic detection - transactions are only validated when the threads end, so execution always progresses until its time to commit

![](https://i.imgur.com/rp3Tid1.png)

- it is also possible to mix and match approaches depending on use case e.g. eager for writes, lazy for reads - all four combinations are possible for validation/versioning, though its not always practical