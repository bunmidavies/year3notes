[[COMP35112]]
[stack overflow q](https://cs.stackexchange.com/questions/20044/memory-consistency-vs-cache-coherence)

### Coherence
- concerned with a ==single memory location==, and ensuring that all cores see the newest version of some memory location
- not interested in the relative order of different updates
- coherence is also typically handled automatically by hardware

### Consistency
- concerned with the ==overall system state== i.e. multiple memory accesses to all memory locations, and their ordering
- different levels of consistency are intended by the program
- keeping data coherent is not the main concern
- consistency models essentially form a contract between the programmer, compiler, and hardware

- ==every system that is sequentially consistent is also coherent at every memory location, but every system that is sequentially consistent is not necessarily sequentially consistent==