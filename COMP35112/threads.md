[[COMP35112]]

- a thread is a sequence of instructions executed on a CPU core - one [[OS processes + process control blocks (PCB)|process]] may consist of one or more threads
- regular, sequential execution of a program would just be a single thread
- since a process has its own address space, all threads belonging to the same process ==share the same address space==, thus threads communicate via shared memory

- if shared memory is not being used, we must resort to other means i.e. MPI (message passing interface, [[shared memory vs distributed memory]])