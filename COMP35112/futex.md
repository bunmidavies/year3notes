[[COMP35112]]

- futex stands for ==Fast User space muTEX== - it is a lock implemented in part ==user space== with atomic operations when there is no contention
- another part of the lock is in ==kernel space==, for when there is contention and specific threads need to be put to sleep (to wait before they can acquire the lock)

# operation

a futex firstly uses a 32 bit variable living in user space, accessed concurrently by threads - when the variable is 0, the lock is free  
  
threads wishing to take the lock perform CAS on the variable - if the CAS succeeds, the thread managed to get the lock without kernel intervention, thus the thread proceeds with its critical section  
  
if another thread now tries to perform CAS on the variable, and fails, this thread must be put to sleep - this means the kernel is required, and the `futex` system call is made in this case  
  
the futex system call makes one last CAS operation to make sure the lock still isnt free, and if its still not free, the thread is put to sleep in a wait queue  
  
any other threads which try to access the user space lock will also follow this same path  
  
when the lock-owning thread wants to release the lock, the thread uses a CAS operation to set the user space variable back to 0, then makes the `futex` syscall to wake up one of the threads in the wait queue (a non optimised implementation will always make this call, since the user space cannot know whether there are still threads in the kernel's wait queue)  
  
the woken up thread makes the CAS call to the user space lock and succeeds