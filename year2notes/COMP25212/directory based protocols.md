[[COMP25212]]
[[COMP35112]]

- directory based protocols overcome the lack of scalability associated with [[snooping protocols|snooping/shared bus protocols]], by using ==distributed hardware== (similar to distributed hardware used in [[out of order execution with tomasulo]])

- an existing approach is to have a centralised directory, which stores cache line information
- each directory entry corresponds to 1 cache line, and has:
	- ==present== bitmap: which core has a copy
	- ==directory dirty bit==: can only be owned by one core, and indicates if the line is out of sync with RAM
- in each core's cache, a line also contains:
	- ==local valid bit==: is the cache line valid?
	- ==local dirty bit==: if core is sole owner, is the data out of sync with memory?
![250](https://i.imgur.com/aZxFtI7.png)

- depending on the scenario, the directory may be read to/written from

# read hit in local cache

- simply read the local value, given the line is valid
![](https://i.imgur.com/OrM5mZA.png)

# read miss in local cache

- firstly, the directory dirty bit is checked
- if the directory dirty bit is set, the unique owner core updates memory, clears its dirty bit and sends the line to the local cache
- if the dirty bit isn't set, then the line data is safe to take from memory or another cache if present
- the valid bit in local cache is set after reading, and *present* is set for the directory line

# write hit in local cache

- if the local dirty bit is set, update local cache
![](https://i.imgur.com/tzR4159.png)

- if the local dirty bit is unset and the directory dirty bit is unset, any present bits in the directory need to be invalidated
- then, the local dirty bit *and* directory dirty bit are set
![](https://i.imgur.com/8drXRkW.png)

- it is not possible for the local dirty bit to be unset, the directory dirty bit to be set, and a write hit to occur - the local dirty bit being unset indicates that the line is shared and there is no unique owner

# write miss in local cache

- if the directory dirt bit is unset, any cache present in the directory is consulted to retrieve the line
- then, invalidate signals are sent to any cores with its present bit set in the directory
- the directory present bit + dirty is set for the local cache and the local cache dirty bit is set

![](https://i.imgur.com/FrR8TqI.png)

- if the directory dirty bit is set, the writing core sends a message to the owner core to update memory, and send the cache line
- the writing core updates the data from the og owner and sets the local dirty bit
- the directory dirty bit is left set, and the og owner is no longer present while the writing core is now present
![](https://i.imgur.com/iMYLv3O.png)

# analysis

- ultimately, the semantics are roughly similar to the [[MSI cache states|MSI protocol]]
- however, the main bottleneck in this case is the central directory
- typical improvements include distributing the directory and caching it itself - this is common in multi-sockets (CPU chips) systems



- now, multiple messages can be transmitted in parallel
![](https://i.imgur.com/1wbH1HZ.png)
- since in this example the directory is centralised, it can still become a bottleneck at some point - by distributing this directory, some scalability issues can be solved
![](https://i.imgur.com/QYz7ZLl.png)

### simple cache line protocols
- cache lines can be in one of 3 states (similar to [[MESI protocol]]):
	1. I = invalid
	2. S = shared - coherent with main memory, other copies may exist
	3. M = modified - value changed, no other copies exist
- the directory itself stores info about cache lines, and these cache lines can be in one of 3 states:
	1. NC = not present in any core's cache
	2. S = cache line is not modified, and in at least one core
	3. M = cache line is modified, and in exactly one core
- the directory uses a ==sharing vector== to know which cores have copies of each cache line

### directory coherence example
![|650](https://i.imgur.com/ncgxFwM.png)

