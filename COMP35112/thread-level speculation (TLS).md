[[COMP35112]]

- thread level speculation essentially involves a basic idea involving any program
	1. program is split into equal parts, which each core handles as separate thread
	2. all cores sequentially execute their part of the program, in parallel
	3. if the program was able to be parallelised, these threads can all 'commit' - otherwise, any problems are detected, whichever speculative state was incorrect is rolled back, and execution continues without speculation

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
	- dupilcate shared data 
	- reads and writes need to be tracked
# method-level TLS

- as the name suggests, method-level TLS 