[[COMP35112]]

# shared memory

- ==shared memory== - accessible from every part of the computation
- in this case, memory is connected to all cores - for this reason, all memory is accessible from all threads, for both reads/writes
- chip multiprocessors almost always end up with shared memory

# distributed memory

- ==distributed memory== - accessible from only one part of the computation
- in this case, memory is connected to only one core - for this reason, in software, memory is only accessible through the thread that owns it, giving way for ==message passing==
- supercomputers typically use distributed memory implementations more

# hardware vs software

- from a hardware perspective, distributed memory is preferable due to:
	- easier to implement
	- higher bandwidth is possible
	- scales better (super computers)
- from a software sharing perspective, shared memory is preferable due to:
	- easier programming
	- works with irregular communication

- one of the main issues with complex hardware is whether to expose software to it, or to use more hardware to hide such complexities:
- if we are to hide existing hardware complexities with more hardware, we have higher hardware costs, more complicated design and wasted energy/cycles
- if we just let software be exposed to this, we'll end up with more complicated code (causing higher costs) and again, wasted energy+cycles