[[COMP35112]]
[oracle multithreaded programming guide](https://docs.oracle.com/cd/E19683-01/806-6867/sync-91921/index.html)

- without condition variables, there are two main ways we could wait to acquire a lock for a critical section a separate thread is currently in
	- ==sleeping== - we sleep for some arbitrary amount of time before trying to acquire the lock (or let another task run), in the hope that we will be able to after sleeping. This can work, but can result in time wasted where we could acquire the lock but are still asleep
	- ==busy-wait== - we continually try to acquire the lock straight away, which means the thread is continually preoccupied, allowing nothing else to run

- condition variables are used to atomically block threads until a particular condition is true - condition variables are always used with a mutex lock
- when a thread changes a given 'condition', it can signal the associated condition variable to cause 1+ waiting threads to wake up, acquire the mutex again, and evaluate the condition

- this allows the thread to wake up exactly when is needed, without monopolising the CPU by continually trying to acquire a lock
- essentially - ==a mutex only allows you to wait until the lock is available; a condition variable allows you to wait until some application-defined condition has changed==

![](https://i.imgur.com/qnJN1lG.png)
