[[COMP22111]]
[[COMP32211]]

**timing closure** is where a combinatorial logic design is modified to meet timing requirements

in order to determine these timing requirements, there are two main processes:
- simulation: can indicate well if a system fails at a particular clock speed - however, it would have to be exhaustive, and can require a **long** simulation time
- [[static timing analysis]] (**STA**): static means independent of the input state. STA finds all combinatorial logic between flip flops, and analyses the delay between all possible paths between flip flops. STA reports the critical paths with setup and hold time violations

a number of other tools also exist to aid with timing closure:
- edge speed analysis - edges which are too slow can introduce a number of issues including:
	- induced noise near gate threshold
	- different target gates may observe the input switch at different times
	- increased time in the intermediate state when switching can lead to more power drain
- hold time checking
- clock skew analysis