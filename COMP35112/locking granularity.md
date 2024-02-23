[[COMP35112]]

- locking granularity describes how big a chunk of code you should treat as critical sections within your code
- for instance, ==coarse-grained== locking may involve you creating a critical section involving operations operating on both shared and unshared data
- meanwhile, ==fine-grained== locking would strictly only use locks when accessing shared data

- fine-grained locking increases parallelism in comparison to coarse-grained locking, but may require more overhead due to the increased number of lock operations (and perhaps more complexity is introduced)