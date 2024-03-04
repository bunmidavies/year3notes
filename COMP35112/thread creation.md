[[COMP35112]]

- typically processes and threads are created with `clone()` - the majority of parameters involved with this aren't important ==when creating a process==, but are required
- the behaviour is similar to the `fork` command in UNIX - the parents resources (including address space) are duplicated for the child

```
long clone(unsigned long flags, void *stack, int *parent_tid, int *child_tid, unsigned long tls);
```

- `flags` specifies creation options
- `stack` and `tls` point to the child's stack and thread local storage
- `parent_tid` and `child_tid` specify where to store the id of the created thread


# `pthread_create` implementation

- `pthread_create` calls `__clone`, a wrapper for `clone` implemented in x86-64 assembly