[[COMP35112]]

- there used to be a big kernel lock serialising all execution of kernel code - this was slowly removed over time, with the final version being in linux v2.6.39 (2011)
- today, the kernel is a highly concurrent, shared memory program

- in order to manage concurrency within the kernel, the following primitives are used:
	- ==mutexes==
	- ==semaphores==
	- ==spinlocks== - busy waiting, usage count 1:
		- run with preemption and interrupts possibly disabled
		- ==usable when kernel execution cannot sleep==