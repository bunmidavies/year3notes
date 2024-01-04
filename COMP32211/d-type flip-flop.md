[[COMP32211]]

- the current device-of-choice for most state holding within synchronous logic circuits (the other major choice being RAM) - the ideal DFF transfers the state of its input data to its output instantaneously at a clock edge, but of course, in reality this is not the case
- there are two main delays which are essentially required by the flip flop:
	- data set up time - a certain amount of time before the clock edge in which the input data does not change
	- data hold time - a certain amount of time after the clock edge in which input data does not change
- the ==propagation delay== of the flip-flop is just the output lag after the clock - if there were no propagation delay then we'd have the ideal, input -> output data transition

- there also exist a number of signals which are seen in variations to the traditional DFF:
	- asynchronous/synchronous clear signal
	- asynchronous/synchronous reset signal
	- clock enable signal