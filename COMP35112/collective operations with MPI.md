[[COMP35112]]

- a number of collective operations i.e. operations which apply to all processes exist, for instance:
	- `MPI_Barrier`: barrier sync
	- `MPI_Bcast`: broadcast message
	- `MPI_Scatter`: broadcast parts of a single piece of data to different processes
	- `MPI_Gather`: inverse of scatter
	- `MPI_Reduce`: reduction operation, useful for summing etc