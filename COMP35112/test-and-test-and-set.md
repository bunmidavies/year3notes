[[COMP35112]]

- tas operations 'lock' the snoopy bus every time it is run, since when the operation begins as an atomic, indivisible operation, it is unknown whether a write is needed or not - this need for atomicity means that everything has to be locked, which can ultimately waste processor time and cause cache coherency traffic (failure to tas - i.e. only READING without writing means that the tas was basically a non-atomic operation, while still invoking the costs of an atomic operation)  
  
- tas costs are reduced with test-and-test-and-set:   
a simple ldr/comparison of the lock address is performed before attempting tas, avoiding the atomicity costs of tas while continuing to busy-wait

- in pseudocode, test-and-test-and-set is implemented as such
```do {
	while(test(S) == 1); //traditional ldr
	while (test-and-set(S)); //tas
}
```

- in assembly, this ends up as
```
loop: ldr %r1, %r2 // address of S in %r2
	cmp %r1, $1
	beq loop
	tas %r2
	bnz loop // branch if %r2 != 0
```

- the main idea is that most of the time we're busy, we wait with a standard `ldr`, and only use the costly `tas` once we've seen that `S` isn't equal to 1 - we're looping with 1 assembly instruction instead of the 3+ used in `tas`