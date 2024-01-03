[[COMP32211]]
[synchronisation in digital logic circuits (stanford)](https://web.stanford.edu/class/ee183/handouts/synchronization_pres.pdf)

- when a signal comes in from a different synchronous system (i.e. a different clock domain), this signal is essentially ==asynchronous== to your system
- even in the case that the external system has the same clock frequency as the internal system, the signal will still have some skew

- a synchroniser exists to essentially convert an external, asynchronous signal from a metastable state into a digital, well defined state i.e. 1 or 0
- typical synchronisers have two flip-flops, like so:
![400](https://i.imgur.com/GSRZWB3.png)
- it essentially involves a flip-flop going metastable for some period of time, but relying on the fact that the probability of a flip-flop remaining metastable decreases exponentially with time
- it is required that synchronisers are:
	- reliable
	- low latency (or as low as possible while maintaining reliability)
	- low power/area impact