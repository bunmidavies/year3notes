[[COMP35112]]
[random lecture notes](https://harmanani.github.io/classes/csc447/Notes/Lecture15.pdf)

- thread < warp < block < grid

- ==threads==: the fundamental unit of parallel execution, executing the kernel once - implemented in hardware, kernels are relatively lightweight
- ==warp==: group of 32 threads executing in lockstep - all threads execute the same instruction. One warp is assigned to each stream processor of the Stream Multiprocessor (SM)
- when data is unavailable, the SM hides latency by switching to another warp (with zero-cost) - internal communication between these warps is fast
- ==block==: a number of threads grouped together, and each SM handles a single block - the block shares the hardware resources of the SM (i.e. register + shared memory), and runs the warps as a group to completion
- therefore, threads communicate through fast shared memory within the block, and if a block uses more resources than available in the SM, the kernel cannot be launched
- the max number of warps in a block depends on architecture and shared resource usage - blocks can be 1D, 2D or 3D
- ==grid==: all the blocks for a kernel are organised in a cartesian grid, which can also be 1D, 2D or 3D

# grid/block dimension execution

```
MMKernel <<<dim(width/32,width/32), dim3(32,32)>>>(Md, Nd, Pd, width);
```

- `dim(width/32,width/32)` - blocks per grid
- `dim3(32,32)` - threads per block
- therefore the grid has `(width/32,width/32)` dimensions, made up of blocks containing 32x32 threads