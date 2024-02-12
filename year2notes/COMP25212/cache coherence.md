[[COMP25212]]
[[COMP35112]]

- cache coherence is necessary in shared memory multiprocessors, for cores to have a consistent view on memory
- ==cache coherence protocols are one of the main limitations as to how many cores a multiprocessor can support== - a number of protocols exist:
	- [[MSI cache states|MSI]]
	- MSI's optimisations: [[MESI protocol]] / [[MOESI]]
	- [[directory based protocols]]

- the memory/cache coherence problem typically affects multicore systems, and is as follows - a core will write to a location in its L1 cache, and other L1 caches may hold shared copies of that same cached location - since the core just updated that location in its cache, the other L1 caches become ==out of date==
- this is essentially the same problem that a singular cache faces with main memory when written to, but extended to multiple cores
- the core has 2 main options:
	1. write through to main memory - this will negate a lot of cache benefits
	2. copy back only when the cache line is rejected
- this follows the same idea as [[cache write policies]], but ==just updating memory isn't sufficient==, since other cores can hold the same location in its L1 cache

![400](https://i.imgur.com/oPedmfX.png)
