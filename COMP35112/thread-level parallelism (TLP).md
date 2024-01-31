[[COMP35112]]

- with thread-level parallelism, the programmer divides the program into sequences of instructions that can run in parallel (contrary to [[instruction-level parallelism (ILP)]], where singular instructions are running in parallel)
- this is a more 'general purpose' approach allowing for larger amounts of parallelism to be extracted (at the cost of the programmers effort)
- again, since there is no guarantee of which order the threads run in due to scheduling, ==data sharing becomes the main issue== - synchronisation techniques are required
![400](https://i.imgur.com/OOLO7od.png)

- in a program which runs all threads purely sequentially on a single core, the total execution time is the sum of each threads execution time
- the ideal execution time with thread-level parallelism is:
  `sequential execution time / number of parallel threads`
- if thread A = 2s, thread B = 2s, sequential time = 4s, ideal exec time with 2 parallel threads = 4 / 2 = 2s 