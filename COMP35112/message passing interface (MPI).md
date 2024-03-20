[[COMP35112]]

- message passing interface (MPI) is a ==standard== for creating portable parallel applications - it's used to program a wide range of parallel architectures, including supercomputers and clusters
- MPI is the ==most widely used API for parallel programming==, and ==message passing== is the main form of communication - it allows parallelism to be exploited beyond the boundaries of a single physical machine
- ==MPI in principle has no concept of shared memory== ([[shared memory vs distributed memory|shared memory]]), which means it is not limited by machine boundaries, which is the reason its hugely popular with supercomputers/clusters
- ==main cost==: programs cannot be easily transferred to a version utilising MPI - one must redesign an application with MPI in order for it to be ported

- in MPI, each process is identified with a ==rank== - messages are sent with a sender/recipient rank in mind, as well as a tag indicating the type of message being sent
- processes can be grouped, and ==communicators== allow communications to be restricted between said groups

- mpi itself is a separate library, and on ubuntu/debian requires `mpicc` as a gcc wrapper as well as `mpirun` in order to run a program with either:
	- a single process
	- a specified number of processes (`-n <number>`)
- ==the same compiled program runs on all processes== - `int main` can be thought of as a sort of main [[shaders|shader]] function 