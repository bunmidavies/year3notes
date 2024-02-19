[[COMP35112]]

- barriers allow a group of threads to synchronise at one point, essentially allowing them to 'meet-up'
- barriers are very natural when threads are used to implement data parallelism - for instance performing multithreaded vector addition, we'd want a barrier for all threads adding chunks of the vector together before checking the final result
- barriers are also useful when data dependencies limit loop parallelism - i.e. x number of iterations have a barrier, then the next y iterations

![](https://i.imgur.com/uKqxISK.png)
*data parallelism*

![](https://i.imgur.com/mc8mktV.png)
*loop parallelism*

# barrier example

- in this simple example there are 2 threads - thread 2 is forced to execute for much longer than thread 1 at each iteration, and a barrier sits between each iteration
- examples sit in code folder