[[COMP35112]]

- a test-and-set instruction, `tas` checks a memory location addressed by a register, then checks if it contains 0 and performs the following:
	- if value is 0, switch its content to 1 and set CPU zero flag
	- otherwise, clear zero flag and don't set anything
- this instruction-level behaviour is ==atomic== - it cannot be interrupted, and no other cores

# implementing `wait()`/`signal()` with `tas`

- for our binary semaphore using wait:
	- lock is free when `S == 0`
	- lock is taken when `S == 1`
- in order to implement `wait()`, we try to take the lock with `tas`:
```
loop: tas %r2
	bnz loop
```

- in order to implement `signal()` (releasing the lock), we simply use a store operation - singular assembly instructions are atomic
```
str $0, %r2
```

# tas and the cache
- the processor must 'lock' the snoopy bus for every multiprocessor `tas` operation, since multiple processors may have a copy of the binary semaphore in their cache