[[COMP25212]]
[[COMP35112]]

- with the [[MSI cache states|MSI protocol]], there are two cases a core in the $S$ state which gets modified can be in:
	- there are multiple cores in the $S$ state, so the invalidate message must be broadcasted
	- theres only a single core with the shared copy, so theres no need to broadcast an invalidate message
- however, in MSI, both cases are broadcasted, resulting in unnecessary communication which has significant negative impacts in a bus

- the MESI protocol solves this issue by splitting the $S$ state into two states:
	- $E$: exclusive - switch to $E$ after a read causing a fetch from memory. This is the ==only== core with an in-date cached copy
	- $S$: truly shared - there are ==multiple== cores with in-date cached copies
![](https://i.imgur.com/TDsnA49.png)

- by ==avoiding sending unnecessary messages==, systems can benefit from:
	- improved latency
	- lower bandwidth consumption
	- less contention for use of the bus (which is carrying messages)
- furthermore, operations like ==write update== ([[snooping protocols]]) assumes that a new value is 'written through' to memory - however, if ==copy-back== was used ([[cache replacement policies]]), then other caches from other cores may end up fetching the wrong value
- a specific protocol which handles these situations is the ==MESI protocol== (aka illinois protocol)

### outline
- the MESI protocol allows for a copy-back scheme in the cache, by simply extending the usual cache tags which are used, assigning each ==cache line== 1 of four states:
	1. ==modified==: the cache line has been modified and is different from main memory - this is the only cached copy
	2. ==exclusive==: the cache line is ==coherent with main memory== (NOT modified) and is the only cached copy
	3. ==shared==: the cache line is coherent with main memory ==but copies may exist elsewhere== (i.e. in other core caches)
	4. ==invalid==: the line data is not valid
- 4 possible states = ==2 bits to store the state==
- each cache line can only change state when accessed, or receiving a message (due to snooping) where the addresses match up

### local cache transactions
- live lecture goes through the different scenarios better - this is for the cache in the current core we're in (i.e. we're using this cache right now)
![](https://i.imgur.com/Qn3Xshn.png)

### snooping cache transactions
- the snooping cache will only ever be able to modify its state if its received a message via the bus
![](https://i.imgur.com/C5VBg6l.png)
