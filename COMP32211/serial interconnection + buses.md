[[COMP32211]]

- for wider system interconnection, its common to use serial interconnection
- serial communication simply means that a transmitter would send $C$ bits of a command (e.g. read/write), $A$ bits of an address and $D$ bits of data
- serial interconnection is inherently cheaper, slower and far fewer chip-pins are required - it is suitable for wireless applications, and examples include:
	- ethernet
	- USB
	- I$^2$C
- though the pin restrictions aren't really a concern for intra-chip connections, the reduction in wiring is attractive for some SoC applications
![](https://i.imgur.com/6oj9CYI.png)
