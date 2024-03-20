[[COMP35112]]

- with C++'s parallel abstractions from the standard library, 4 main execution policies are provided
	- `sequenced_policy` = no parallelism
	- `unsequenced_policy` = SIMD execution
	- `parallel_policy` = parallel execution
	- `parallel_unsequenced_policy` = parallel SIMD execution
- there are roughly 80 stl algorithms that the parallel execution policies are suited to, including:
	- `all/any_of`
	- `copy/fill`
	- `find/search`
	- `for/each`
	- `generate`
	- `min/max/minimax`
	- `sort`
	- `reduce`
	- `remove`
	- `transform`
- it's easy to also compose algorithms