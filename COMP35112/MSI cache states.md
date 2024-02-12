[[COMP35112]]

- cache can have 2 control bits for each line it contains, indicating the state of that cache line, relative to main memory:
	- ==modified== - the cache line is valid and has been written to but the latest values have not been updated in memory yet. **A line can be in the modified state in at most 1 core**
	- ==invalid== - there may be an address match on this line but the data is invalid - the line must be fetched from memory or another cache, before this cache serves any read/writes
	- ==shared== - not invalid and not modified - a valid cache entry exists and has the same. value as main memory. **Several caches can have the same line in the shared state**

- the state of a cache line may be changed when a core tries to read/write data in that line
- ==state transitions== have 3 aspects:
	- the **messages** sent between caches:
		- *read* message = core 1 cache requests a cache line from another core
		- *invalidate* messages = core 1 cache asks other caches to invalidate one of its cache lines
	- has any access been made to main memory
	- any state changes

# dual core example - modified invalid

![](https://i.imgur.com/nbIkIbh.png)
- read on core 1: cache hit, served from core 1
- write on core 2: cache hit, served from core 1
- read on core 2:
	- core 2 sends out read request on snooping bus + other cores
	- core 1 shares cache line with core 2, and writes cache line back to RAM
	- both core 1 and core 2 become shared i.e. S


![](https://i.imgur.com/aGlez9L.png)
- write on core 2:
	- core 2 must read correct value first, placing a read request on snooping bus + other cores
	- core 1 sends line to core 2 and to RAM, so both become S state
	- now core 2 modifies line, becoming M, and sends out invalidate request, making core 1 invalid (i.e. I)