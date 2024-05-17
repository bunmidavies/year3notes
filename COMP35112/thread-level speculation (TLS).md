[[COMP35112]]

- thread level speculation essentially involves a basic idea involving any program
	1. program is split into equal parts, which each core handles as separate thread
	2. all cores sequentially execute their part of the program, in parallel
	3. if the program was able to be parallelised, these threads can all 'commit' - otherwise, any problems are detected, whichever speculative state was incorrect is rolled back, and execution continues without speculation
- three main types of TLS are covered
	- [[thread-level speculation (TLS)#loop-based TLS|loop-based TLS]] (below) - can range from slowdown $\rightarrow$ decent speedup
	- [[method-level TLS]] - speedup occasionally occurs
	- [[arbitrary point TLS]] 

# overheads of TLS

- shared data is often duplicated
- reads and writes often need to be tracked in order to avoid dependency violations and illegal actions - on top of this, checking the status of the location of lower threads when reading + checking the status of the location of higher threads when writing is also required
- as mentioned, TLS is also not beneficial if the computation time is less than the time required for threads to commit their final state
- if speculation is unsuccessful, the non-speculative thread has run much slower for no reason, and the speculative threads have effectively contributed nothing - with respect to energy/power constraints, energy wasted is another downside TLS may involve

- attempts to reducing rollbacks and mentioned overhead include:
	- value forwarding (stalling reads from higher threads)
	- value prediction for the return value of methods
	- partial commits
	- using caches as speculative data buffers

# loop-based TLS

- based on M. Cintra and DR Llanos paper, 2005
- given there's a loop with $x$ iterations and $n$ threads, each thread is given $\frac{x}{n}$ iterations to handle - the first thread can be considered non speculative, while the other $n-1$ threads are speculative
- the main requirement for threads executing in parallel is that the ==relative order of reads & writes remain the same== - this means that there are only two illegal actions which cause issues:
	- Writes followed by reads from earlier threads - this is a ==Write After Read (WAR)== dependence violation
	- Reads followed by writes from earlier threads - this is a ==Read After Write (RAW)== dependence violation
- another issue is that these accesses are only identified after they occur

### solving dependence violations
- one method of solving the write after read dependence violation is by giving each thread a copy of the data
- solving read after write violations is more tricky - data within a thread is kept in one of 4 states:
	- S = speculatively loaded
	- M = modified
	- SM = speculatively loaded & modified
	- N = not accessed
- threads which write to data in the S state causes a violation, since they should have modified the data before it was loaded - the thread which speculatively loaded the data can then rollback by deleting its whole speculative state

### resulting parallelism
- once all threads have finished computing, the results are committed in order of the program, from iteration $0$ to $x$
- for loop based TLS to show improvements to performance, the time for computation must be much longer than the time required to commit
$$\textrm{work per thread >> commit effort}$$
- simultaneously, with very large computation per thread, there is a high probability of conflicts, likely resulting in high costs related to conflict
- in short:
	- keep track of reads/writes
	- lower threads notify higher threads of writes they do
	- if the higher threads are in the S/SM state - rollback
	- threads then all commit in program order

- overheads of TLS include:
	- duplicate shared data 
	- reads and writes need to be tracked