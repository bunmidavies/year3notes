[[COMP35112]]

- MOESI builds on further from the [[MESI protocol]], splitting the $M$ state into two separate states:
	- $M$ - modified: not in sync with memory, but the only copy
	- $O$ - owned: not in sync with memory, but other cores have copied this cores value over

![](https://i.imgur.com/KNPqt4p.png)

- without MOESI, any a shared core which modifies its value becomes $M$, and invalidates all other cores in the $S$ state
- but with MOESI, the owner has exclusive rights to make changes to the copy, and can update the shared cores, ==meaning no memory writeback is required== - writeback only becomes necessary when data in $O$ or $M$ is evicted from the cores cache