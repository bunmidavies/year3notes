[[COMP35112]]

- scheduling in general takes into account a number of factors:
	- communication/interference constraints
	- thread affinity (which threads are preferred for what tasks)
	- thread/task criticality
	- energy and power constraints
- no scheduler that currently exists manages to weigh out all aspects, for instance:
	- linux has separate schedulers which are capacity (workload)/energy aware, but ignores affinity
	- intel only considers affinity
	- task schedulers may consider criticality and affinity
	- research schedulers = better but not ready for real-world

# communication

- there are ==hard== and ==soft== constraints relating to communcation:
	- hard constraints: if threads talk through shared memory, then devices *must* share memory
	- soft constraints: if threads talk often, then devices should be close - if threads compete for the same shared resources, those threads cant be scheduled on the same cluster of resources

# affinity

- in a heterogeneous system, different devices will match better with different workloads - how they actually match up can be difficult to predict, since factors include:
	- the program
	- hardware capabilities
	- device compiler capabilities
- if we're using a purely asymmetric core chip without any external accelerators, determining this can become easier (not that it isn't still difficult) - the only difference now is within the architecture of each core
- the ILP within some program, its memory bounds, latency sensitivity and control flow all affect what is best suited
- these compatibilities are code as well as input dependent, so predicting this in advance is another layer of difficulty

# criticality

- not all tasks/threads are equally important for program progress
- various approaches exist for determining criticality of certain program sections and assigning threads accordingly, but one method is through tracking the cumulative waiting time caused by each thread, and assigning the threads with the highest wait times to fast cores ([jibaja et al.](https://ieeexplore.ieee.org/document/7559529))

# energy/power

- power/energy budgets are always limited, and different requirements of a system may be implied given these budgets:
	- some cores might have to turn off given power budget
	- not all cores can run at top frequency to save power
	- whether to use fewer fast cores or more slow cores in asymmetric systems might be considered
	- more power results in more energy therefore longer runtime = more energy
	- whether to wake up idle cores or run less efficiently on active cores has energy implications