[[COMP35112]]

- the `pthread` library has a mutual exclusion lock mechanism - this allows only 1 thread to acquire the lock at any given time 

example:
```C
#include <pthread.h>

pthread_mutex_t mutex;

void thread_function()
{
	pthread_mutex_lock(&mutex);

	// critical section goes here

	pthread_mutex_unlock(&mutex);
}
```

- lock usage example for a circular bounded buffer exists in code folder