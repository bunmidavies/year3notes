[[COMP35112]]

- futex stands for ==Fast User space muTEX== - it is a lock implemented in part ==user space== with atomic operations when there is no contention
- another part of the lock is in ==kernel space==, for when there is contention and specific threads need to be put to sleep (to wait before they can acquire the lock)