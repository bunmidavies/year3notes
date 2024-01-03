[[COMP32211]]

- transparent latches is a term commonly used synonymously with just 'latches' - it is a simple ==asynchronous== storage element, differing to a typical D-type flip-flop (DFF)
- latches have 3 signals:
	- $D$ - Data in 
	- $Q$ - Data out
	- $En$ - Combinatorial enable signal
- the latch is asynchronous, so whenever En is high, D matches Q (thus the latch is 'transparent')
- if En is low, then D will remain as whatever value it was, unaffected by Q
![300](https://i.imgur.com/D9aHbfv.png)

- ==advantages==:
	- silicon area of a latch is about half of a DFF, potentially making it cheaper
	- no clock cycle latency since asynchronous - can sometimes be useful for data transfer between modules
- ==disadvantages==:
	- controlling enable from combinatorial logic must be glitch free, which can be difficult to ensure
	- CAD tools no longer optimised for asynchronous modules (STA relies on analysing paths between synchronous DFFs)
	- FPGAs built with numerous DFFs, thus synthesizing latch can end up being more expensive