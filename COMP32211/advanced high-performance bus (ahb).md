[[COMP32211]]

- AHB is a ==pipelined== bus, intended to perform ==one transfer per clock cycle== - contrary to [[advanced peripheral bus (apb)]], which performs one transfer per two clock cycles
![](https://i.imgur.com/5wIRxpC.png)

- the read/write data is typically provided on the next clock cycle, but one command can be provided per clock cycle
- multi-master means that there may be multiple signals controlling the operation of the bus - bus cycles can also be extended or aborted through additional signals (?)
- processor buses on ==medium performance devices== typically use this design