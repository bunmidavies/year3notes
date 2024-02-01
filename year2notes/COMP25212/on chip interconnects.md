[[COMP25212]]
[[COMP35112]]

### definition
- any multicore system must contain a way for all cores to ==communicate effectively== both with:
	- other cores (coherence / sync)
	- main memory
- there are many different ways to enable this, with different tradeoffs (performance, energy, area, fault tolerance etc.)
- a ==Network on Chip== is a network based system which essentially connects different parts of a computer chip together
- the network allows for all different components to communicate efficiently and reliably, ==without bottlenecks==
### evaluating networks
- the three main factors, as with any traditional network are:
	1. ==bandwidth==
	2. ==latency==
	3. ==congestion== - the effect on bandwidth/latency when a network is close to its peak usage
- three other important factors which are more specific to chip networks are:
	1. ==fault tolerance==
	2. ==area in terms of silicon available for use==
	3. ==power dissipation and power available to the network==
### key features of a NoC
- ==topology== - how the cores and other elements are connected together
- ==routing== - how traffic moves through the topology
- ==switching== - how traffic moves from one component to the next

### interconnect options (35112)

| Type | Worst Case | Notes |
| ---- | ---- | ---- |
| Grid | $2(N-1)$ steps for $N\times N$ grid | direct link to neighbours, private on-chip memory for each core, edge cores will have 2 neighbours only - simplest implementation |
| Torus | $N$ steps for $N\times N$ grid | similar to grid (private memory per core too), but more symmetrical paths which wrap around the grid at edges - all cores have 4 neighbours - more wires/complex routing required |
| Torus (higher dimensions) |  | 3D torus = 6 neighbours, 4D torus = 8 neighbours, typically chip multiprocessors typically only have 2D toroids  |
| Bus | Constant latency | Simple to build, but contention problems occur + complexity/routing |

### topologies
- ==bus== - all components are connected to a single wire (==broadcast medium==), and this single wire can only be used by a single componenet at any given time - this can lead to ==scalability issues==
- to improve the bus, transactions can be split - time taken for operations are already divided by the clock
![](https://i.imgur.com/AQN5PPD.png)
- ==crossbar== - N inputs are connected to N outputs, achieving an ==any to any== relationship between components
- crossbar has ==extreme scaling issues==, scaling is quadratic in the number of components
![](https://i.imgur.com/lcA2vnH.png)
- ==tree== - bandwidth and latency vary depending on the depth of the tree
- ==ring== - low bandwidth, variable latency
- ==mesh / grid== - one of the more favourable options today, as any component can reach any other component, and bandwidth is reasonable (while latency may vary)
![](https://i.imgur.com/rqvLQ0h.png)

### routing
- routing is the process of determining the path that data should travel from one component on the chip to another
- multiple strategies for routing exist, and have various tradeoffs:
	- ==minimal routing== - always pick the shortest destination (packets are more likely to be blocked due to this strategy)
	- ==non minimal routing== - packets can be diverted in order to avoid blocking/congested areas (but the risk of ==livelock== now exists)
	- ==oblivious routing== - a simple router, providing deterministic paths which are deadlock free (as it is ==oblivious== to the state of the network), but can then cause blocking/contention problems
	- ==adaptive routing== - packets adapt to avoid contention, thus leading to higher performance, but more complexity (this is barely used in NoCs)
- note that ==blocking = lack of bandwidth==, while ==contention = multiple packets competing==

### switching
- packet switching strategies define how packets move when travelling across a NoC
- info is added to packet headers in order to identify each of them, and perform routing
- there are multiple packet switching strategies, for instance:
	- ==store and forward== - packets essentially move as one. A packet isn't forwarded until all its physical units arrive to each intermediate node (allowing for on the fly failure detection, at the cost of performance)