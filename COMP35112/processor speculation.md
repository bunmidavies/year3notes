[[COMP35112]]

- speculation is prevalent in single core processors in a number of manners:
	- branch prediction
	- out-of-order execution
	- value prediction
- all these methods involve making some sort of guess about the upcoming condition of the program, and rolling back the programs state in the case that the speculation was wrong

- speculation essentially introduces parallel execution to serial programs, to avoid the inconvenience of having to turn the serial program itself into a parallel program
- multi-core processors can perform [[thread-level speculation (TLS)]], by treating a program as if its parallel given there are spare cores (without caring whether the code is safe or not) - then, any sequential operations that are not parallelisable can be rolled back and repeated