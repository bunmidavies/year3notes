[[COMP32211]]
[mantra vlsi](https://mantravlsi.blogspot.com/2014/07/time-borrowing-and-time-stealing.html)

- time stealing and time borrowing are concepts that apply to pipelines with flip-flops and latches, respectively (steal = flip-flop, borrow = latch)
- ==the concept generally applies to pipelines which are not perfectly balanced== - a balanced pipeline would mean the critical path of all pipeline stages are roughly the same, and no stage is being a real bottleneck on time
- the terms are not so much of concern, but more so the principle - time is essentially borrowed or stolen from one pipeline stage which does not require an entire clock period, and given to another stage
- the time for the clock cycle in the next stage of the pipeline is given to the previous stage, which requires more time
- ==these techniques aren't obtained through simple design flow==

- take the time stealing example below
	- the main constraint in the pipeline is the 1000ps stage, thus our clock period is 1000ps i.e. 1GHz clock rate - the next stage only takes 800ps, therefore will have 200ps of free time before its result is actually needed (the next clock cycle)
	- we introduce a 100ps delay to the flip-flop feeding into the 800ps stage (which is the output of the 1000ps stage), it means that if we remained at 1000ps clock period, the 800ps stage would now have only a spare 100ps before its result is needed
	- but now, the 1000ps stage essentially has 1100ps to complete - thus we can reduce the clock period to 900ps i.e. 1.1GHz clock rate, and all constraints are still met
![](https://i.imgur.com/O7RIqCU.png)

- the main difference between time stealing and time borrowing, is that in the case above, you see that time is given from one stage to the previous stage, i.e. 'stolen' - meanwhile, with latches, since they're transparent (i.e. results travel straight away and don't have a delay like a flip flop), any spare time in one stage is automatically exploited by the next stage, thus you're technically already 'borrowing' time to the next stage

- there are various difficulties associated with correctly implementing time borrowing/stealing:
	- standard designs flows won't allow for this
	- there needs to be a well controlled delay in the clock distribution tree (i.e. the 100ps delay which goes to the flip-flop), which can be difficult to make reliable
	- it needs to be guaranteed that the delayed clock edge can capture the data from the pipeline stage which has been given extra time