[[COMP35112]]

- locks are synchronisation primitives enforcing 2 main constraints on the execution of a critical section
	- ==serialisation==: (typically) 1 thread can concurrently execute the critical section
	- ==atomicity==: when a thread $T$ starts to run critical section $S$, $T$ must finish $S$ before another thread can enter $S$
- to protect the critical section, only one thread can hold the given lock at a time (serialisation) - then, this thread holding the lock only gives it up once its executed the whole critical section (atomicity)
- any other thread that wants to enter the critical section tries to acquire the lock, and if unsuccessful will wait

![](https://i.imgur.com/IAE0b3R.png)


# examples

- locks protect shared data from concurrent access
- this may be required for various reasons, but a simple example includes a cash machine
- if 2 transactions are happening at nearly the same time, it must be ensured that the cash machine doesn't accept 2 withdrawals which sum to more money than it has, due to it having enough money to serve either individual transaction


- another simple example includes incrementing a value across multiple threads
![](https://i.imgur.com/vXPAk2j.png)
