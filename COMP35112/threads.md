[[COMP35112]]

- a thread is a sequence of instructions executed on a CPU core - one [[OS processes + process control blocks (PCB)|process]] may consist of one or more threads
- regular, sequential execution of a program would just be a single thread
- since a process has its own address space, all threads belonging to the same process ==share the same address space==, thus threads communicate via shared memory