[[COMP32211]]
[wiki](https://en.wikipedia.org/wiki/Advanced_Microcontroller_Bus_Architecture)

- AMBA is an open-standard on-chip interconnect specification for the connection and management of functional blocks in SoC designs - a number of standards are defined within AMBA, with the most common examples being
	- [[advanced peripheral bus (apb)]]
	- [[advanced high-performance bus (ahb)]]
	- [[advanced eXtensible interface (axi)]]
- each standard specifies the list of signals used in the interconnection and their timing relationship on a cycle-by-cycle basis
- the objectives of AMBA are:
	- to facilitate *right-first-time* development of embedded microcontroller products with one or more CPUs, GPUs or signal processors
	- to be technology independent, allowing for the re-use of IP cores, macrocells, etc
	- to encourage modular system design
	- to minimize silicon infrastructure required to support high performance, low power on-chip communication