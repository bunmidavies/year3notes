[[COMP35112]]

- by default, a thread locking a lock it already holds results in ==undefined behaviour==

- a ==reentrant lock== is a lock that can be taken by a thread that already holds it - this prevents a thread from [[deadlocks|deadlocking]] itself
- reentrant locks are used with `pthread_mutexattr_t`, and the `pthread_mutexattr_settype` function

```C
pthread_mutexattr_t attr;
pthread_mutexattr_init(&attr);
pthread_mutexattr_settype(&attr, PTHREAD_MUTEX_RECURSIVE);
pthread_mutex_init(&a->lock, &attr);
```