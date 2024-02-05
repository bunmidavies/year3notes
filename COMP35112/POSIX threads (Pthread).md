[[COMP35112]]

- Pthread stands for the ==POSIX thread library== - it exposes a C/C++ API to create and manage multiple threads within a process (a single program)
- threads exist as `pthread_t` data structures

### `pthread_create()`
- creates and launches a thread with the following parameters:
	- which function the thread should run
	- optionally, what should be passed as parameters to this function
- use `pthread_exit()` to have the new thread you have spawned exit

### `pthread_join()`
- waits for another thread to finish, taking a `pthread_t` as an argument

![300](https://i.imgur.com/bsTjxbJ.png)
