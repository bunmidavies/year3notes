[[COMP35112]]

# versioning

- versioning is used in order to
- there are two main types of versioning:
	- eager versioning:
		- transactional data in shared variables
		- original data in undo log
		- fast commit, slow abort
	- lazy versioning:
		- transactional data in private copy
		- original data in shared variables

# validation

- validation involves checking whether a variable has already been modified, with each time that it is accessed
- like versioning, there are two types of validation:
	- eager validation:
		- each read is compared against each previous write location from other threads
		- each write 