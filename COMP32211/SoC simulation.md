[[COMP32211]]

- simulation is performed in order to verify: 
	- the functionality of an RTL description
	- the correctness of a completed chip
	- the timing and electrical properties of the proposed product
- simulation may not only stop at the chip level - complete systems can also be simulated in order to verify something will work every time
- simulated models allow what would otherwise be hidden nodes to be examined and manipulated in a much easier manner - if it weren't for this, then at the SoC level, figuring out what is causing some minor fault would be more or less impossible

- a number of levels of simulation exist:
	- functional - these may not necessarily fit timing requirements, hence why a separate set of simulation is required for such. It also doesn't guarantee that a design will be physically feasible i.e. constructable
	- timing - timing verification exists to isolate a critical path, both pre-layout (after synthesis) and post-layout (netlist has been laid out) - delays and electrical buffers may be inserted as necessary after post-layout simulation
	- electrical
	- physical?