[[COMP35112]]

- adapted from Khronos Group's [[openGL]], OpenCL provides a standard for programming accelerators (e.g. GPUs, CPUs, FPGAs, DSPs)
- similar to [[CUDA programming language|CUDA]], OpenCL provides a restricted version of C + extensions + qualifiers
- the performance considerations are similar, but OpenCL can run in multiple different platforms using different compilers

- device code is similar to CUDA implementations, except when accessing data structures, `get_global_id` is used as opposed to the block dimensions used in CUDA ([[CUDA thread hierarchy]])
- however, host code is more pronounced than CUDA - a lot more boilerplate is included to provide control over the process
- an alternative to this that Khronos Group are also developing is [[SYCL]]