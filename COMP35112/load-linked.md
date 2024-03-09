[[COMP35112]]

- load linked takes 2 registers as parameters, but allows a core to keep some state
```
ldl %r1, %r2
```
- `%r1` $\leftarrow$ `*(%r2)` - a specific 'load linked flag' is set, saving the address from `%r2` in the *locked address register* 

# load-linked flag

- the load linked flag is cleared if another core writes to the locked address (i.e. the address stored in the locked address register)
- for this reason the processor must snoop the address bus to check if such address has been written to
- other events such as context switches and interruptions will also clear the load-linked flag (control flow breaking events)