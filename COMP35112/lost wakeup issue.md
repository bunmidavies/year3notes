[[COMP35112]]

- the lost wakeup issue can occur when using [[condition variables]], where a signal is not sent to all threads waiting on a condition variable
- a fix in such a situation is to use `pthread_cond_broadcast()` - which wakes up all threads - rather than `pthread_cond_signal()`