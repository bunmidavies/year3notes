[[COMP35112]]
[oracle multithreaded programming guide](https://docs.oracle.com/cd/E26502_01/html/E35303/ggecq.html#:~:text=Spin%20locks%20are%20a%20low,the%20lock%20has%20become%20available.)

- threads attempting to hold an unavailable spinlock will busy-wait, as opposed to going to sleep for regular mutex [[locks]]
- essentially, when the calling thread requests a spin lock that is held by another thread, the second thread 'spins' in a loop to test if the lock has become available
- although this monopolises CPU resources, this results in lower wakeup latency