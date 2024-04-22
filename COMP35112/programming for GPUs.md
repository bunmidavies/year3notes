[[COMP35112]]

- for programs beyond a graphic based context, the following characteristics are typically preferable for GPUs:
	- data parallelism
	- simple control flow
	- simple communication
	- significant amounts of work for each piece of data
- currently, there are not a huge amount of programs that fit into these characteristics thus can be executed efficiently using GPUs, but some of the following areas have found benefits:
	- video processing
	- physics
	- DNA sequencing
	- linear algebra
	- deep learning
- previously, to program GPUs for purposes outside of graphics, using OpenGL, DirectX, and similar libraries to express tasks through shaders was a common approach
- as of recent times, general purpose GPU frameworks such as [[CUDA programming language|CUDA]], OpenCL, OpenACC, [[OpenMP]] while not being perfect, have provided improvements to the former