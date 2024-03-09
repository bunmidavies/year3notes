[[COMP35112]]

```
stc %r1, %r2
```
- tries to do `*(%r2)` $\leftarrow$ `%r1` - however, this only succeeds if the ==load linked flag== is set ([[load-linked]])
- afterwards, the value of the load linked flag is returned in `%r1` - representing whether or not the store was successful - and the load linked flag is cleared 