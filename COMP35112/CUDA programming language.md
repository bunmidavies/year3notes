[[COMP35112]]

- CUDA = ==Compute Unified Device Architecture== - used for only NVIDIA GPUs, CUDA is a subset of C/C++ involving extra qualifiers

- CUDA is a heterogeneous programming model, involving two main components:
	- host - the CPU - dispatches kernel and data to the device
	- device - the GPU - accelerates the provided kernel using data, and returns resulting data

![200](https://i.imgur.com/iLKHACU.png)

# CUDA example - matrix multiplication

- the host code orchestrates the computation, by copying data to/from the device, and initiating the kernel
- the kernel contains the computation to be performed on the data - in this context, floating point multiplications/additions
- the steps to return $P = M * N$ are briefly as follows:
	1. allocate device memory for $M, N, P$
	2. copy values of $M$ and $N$ to allocated locations
	3. invoke kernel code to perform calculation on device
	4. copy $P$ from device memory to host
	5. free device memory

# function declaration prefixes

- functional declaration prefixes are used to tell `nvcc` - the NVIDIA compiler - how to compile the code
	- `__global__` = executed on device, called from host
	- `__device__` = executed on device, called from device
	- `__host__` = executed on host, called from host
- functions can be both `__host__` and `__device__` and in this case, two different compiled versions are created, resulting in the same code executed on the CPU & GPU