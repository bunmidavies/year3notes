[[COMP35112]]

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