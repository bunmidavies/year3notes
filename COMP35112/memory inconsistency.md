[[COMP35112]]

tldr;
- memory inconsistency is where illegal/inconsistent states are reached as a result of memory stores occurring out of order
- **OoO execution + write-buffers + multiple caches + OoO stores + need for coherency = erroneous loads** - single-core safety isn't the same as multi-core safety

- memory coherence issues can cause seemingly thread-safe code to exhibit unexpected behaviour

- an exemplar cause is related to how out-of-order execution handles the writing/reading of variables
- store operations typically have their latency hidden by using write buffers - in many cases, this should still be okay, and the stores will still appear to happen in the correct order (which is the main requirement)
- however, issues can occur when storing different variables out of order, and then loading those different variables - which variables are 'new' and which are 'old' need to be consistent, but this may have been violated by shortcuts being taken to issuing one store operation which has nothing to wait for before another store operation
- ultimately, issuing loads + stores out of order can lead to memory being reached out of order, resulting in impossible combinations of variable values

- another example can be when using a memory location as a lock - storing to some variable in a critical section to then immediately releasing the lock results in two store operations, and it is possible that the lock is released before the critical section operation is issued - this is an example of ==memory inconsistency==