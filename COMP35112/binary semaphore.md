[[COMP35112]]

- a single shared 'boolean' variable $S$ which value is used to protect a shared resource
	- `S == 0` means the resource is free
	- `S == 1` means the resource is in use

- in order to operate `wait(S)` i.e. the acquisition of the lock/semaphore, atomicity is needed
- the lock itself is a shared data structure, so the issues that revolve around not using synchronised data structures also technically exist around using synchronised data structures
- to ensure that `wait()` is "indivisible" i.e. atomic, special instructions must be required in hardware - these are special CPU instructions that realise a few operations atomically
- these few operations typically include a memory load, comparison and possibly a memory write