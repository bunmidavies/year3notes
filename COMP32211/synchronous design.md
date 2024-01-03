[[COMP32211]]

- essentially, synchronous design is a good thing - in FPGAs, it's more or less critical - they allow stable, reliable designs to be built for a variety of reasons:
	- RTL design is simplified, since its easier to reason about synchronous designs
	- timing simulation and STA are easier to perform
	- since the design is simplified, reusability is also promoted
	- the majority of external CAD tools and design support are optimised for synchronous designs
	- impacts of FPGA component process changes (i.e. a change in the way things are manufactured) is also minimised

- however, its not always possible to have an entire SoC use the same clock:
	- clock distribution (via a [[clock tree]]) may become increasingly difficult/less feasible
	- certain blocks may work optimally at different clock frequencies (blocks could also be IP from vendors having some specified frequency)
	- some IO may require specific frequencies