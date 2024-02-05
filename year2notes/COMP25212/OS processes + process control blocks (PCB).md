[[COMP25212]]

- a program executing on the CPU runs as a ==process==
- using the notion of [[virtual memory + page tables|virtual memory]], the process has the illusion that it has access to 100% of the memory (address space)
- 2 programs will run in 2 different processes, i.e. 2 different address spaces

![500](https://i.imgur.com/e5vsYaS.png)

# process control block (PCB)

- processes within an OS can have a number of different states, and typically will jump between these states
- a process control block / PCB stores info related to the state of an 'alive' process being handled by the operating system ([[software multithreading]])

a range of information is stored within these blocks:
- process ID
- process state
- PC
- stack pointer
- general registers
- memory management info
- open file list with positions
- network connections
- CPU time used
- parent process ID