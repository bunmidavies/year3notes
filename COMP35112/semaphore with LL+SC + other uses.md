[[COMP35112]]

```c++
/* address of the lock is in %r2 */

loop: ldl %r1, %r2 // load semaphore from %r2
		comp $0, %r1 // compare sempahore (S) to 0
		beq loop // if S == 0, try check again
		mov $0, %r1 // semaphore appears free
		stc %r1, %r2 // try to take semaphore
		cmp $1, %r1 // check if write succeeded
		bne loop // if not, someone took semaphore first

		/* critical section here */

		st $1, %r1 // release the semaphore with st
```
- note that this essentially ==spinlocks==, since a continuous loop is used - sleeping would be more efficient, but requires OS support

- single atomic RMW instructions such as `tas` atomically combine load and store operations
- ==LL/SC are not atomic in themselves==, but inherently determine whether anything between the two operations have been executed or not with respect to an address, enforcing atomicity