[[COMP35112]]

- memory consistency models aim to provide:
	- a clear definition of how stores become visible
	- a clear definition of how stores can be ordered, and what is/isnt allowed
	- a clear context for hardware and software optimisations

# sequential consistency (SC)

- created by Leslie Lamport in 1979 - the most straightforward consistency model, involving no out-of-order memory operations

*"The result of any execution is the same as if the operations of all the processors were executed in some sequential order, and the operations of each individual processor appear in this sequence in the order specified by its program*

- this can effectively be thought of as representing the programmers view of the memory
- however, the model is typically too restrictive given that:
	- all operations must have a specific order
	- no memory operations can be reordered
	- no software/hardware optimisations are possible
- optimisation potential is traded for constraints and better chances of correctness

# release consistency

- within release consistency, writes to shared variables can be considered 'invisible' within locked regions, since reordering them doesn't affect the programs result
- a contract is made between the programmer and the system, entailing:
	- shared access is protected by synchronisation
	- critical sections are assumed to be atomic
	- operation orders don't have any external effects
- in this scenario, reordering of operations is completely valid provided the above conditions are met, there are no internal effects, and writes are completed before release
- ==fence/barrier instructions== are used to indicate the beginning/end of critical sections - past a specific fence, a guarantee that all memory operations past this fence are completed can be made
- within ARM architecture, the `dmb` (data memory barrier) instruction is used to enforce release consistency - on top of this, two other instructions are used:
	- STLR/Store-Release: atomic modification of variables after all previous store instructions are complete
	- LDAR/Load-Acquire: atomic reading of variables while forbidding subsequent writes to be executed beforehand