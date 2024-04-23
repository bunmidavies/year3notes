[[COMP35112]]

- transactional memory provides a number of benefits, but involves a lot of extra work under the hood:
	- maintaining read/write-sets
	- maintaining local write buffers (lazy) or undo-logs (eager)
	- transmitting reads/writes (eager) or writesets (lazy)
	- serialising commits
	- making writes visible
	- deallocating space for sets
	- maintaining a list of active transactions
	- continually listening for validation checks
- a number of software libraries exist to handle this, but whether or not the programmer actually handles it, a lot of extra work is going on in the background
- if the amount of sharing is more than significant performance does not benefit from TM in software

# TM cache

![500 ](https://i.imgur.com/GYVO1YQ.png)

- [[load-linked]] store conditional instructions essentially operate as transactions on a singular memory location: the readset is represented with a locked address register, bus snooping detects R-W conflicts, resetting the load-linked flag causes a restart in the case of a conflict, and if no conflict occurs the value is committed to memory
- the cache-based approach extends upon this, using the cache as a readset, writeset and write buffer
- when performing a transactional write, an invalidate signal must be broadcasted as per usual - receiving this signal means data must be cleared and a restart is necessary

- a number of companies have tried to implement such a system, but many have failed and/or given up - although not perfect, its an elegant solution of high difficulty with implementations needing to solve a number of problems including:
	- limited L1 cache size (upper limit of read/writeset) - essentially, the transaction size must be < size of L1
	- skewed access patterns leading to high pressure in some cache sets
	- only small transactions really become viable given cache size