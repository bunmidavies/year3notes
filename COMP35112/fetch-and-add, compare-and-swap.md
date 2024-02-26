[[COMP35112]]

- fetch-and-add: returns the value of a memory location and increments it
- compare-and-swap (CAS): compares the value of a memory location with a value in a register, and swaps with another value in a register if they're equal

```C
compare_and_swap(addr, comp, new_val)
{
	if (*addr != comp)
		return false;

	*addr = new_val;
	return true;
}
```

- all of these instructions are read-modify-write with the need to lock the snoopy bus during their execution
- with RISC pipelines, these are quite difficult to implement, whereas with CISC architectures RMW operations are more suitable