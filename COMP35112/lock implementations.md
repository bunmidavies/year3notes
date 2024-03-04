[[COMP35112]]

- under the hood, `pthread_mutex_lock` and other sleep-based lock access primitives rely on the kernel - this is because the kernel is essentially the entity that puts threads to sleep and wakes them up (how could a thread put itself to sleep/wake itself up?)
