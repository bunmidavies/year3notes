[[COMP35112]]

there are three main types of heterogeneity, increasing in generality:
- domain specific accelerators
- general purpose accelerators
- asymmetric multi/many-cores

# domain specific accelerators

- designed finely towards some application/domain, in order to provide better performance and energy efficiency, with the use of less transistors
- vector machines and floating point units, as well as SIMD units and tensor units are essentially applying this idea, but the new part of domain specific accelerators is that these are large scale processing units on the chip, but outside any specific core
- the main motivation to create domain specific accelerators has been fuelled by ==big data==, and the need to carry out heavy workloads under specific energy/time constraints
- the financial incentive for designing and integrating these accelerators has led to a Cambrian explosion of hardware designs
- common applications might include cryptography & compression, sequence alignment, parsing & pattern matching

- *example*: Snapdragon 8 Gen 2 SoC:
	- contains image signal processor, digital signal processor, AI accelerator, network processor and security chip

# general purpose accelerators

- unlike domain specific accelerators, general purpose accelerators typically aim to just deal with massively data-parallel workloads, and will typically be controlled by the CPU - thus making them not completely independent
- examples include on-chip general purpose GPUs, integrated graphics - these are tightly coupled with the CPU
- although FPGAs may be seen as domain specific, they typically offer general purpose designs which can be useful for workloads which are too complex/low latency for GPUs, and too parallel for CPUs

- *example*: project catapult by Microsoft involved offloading part of bing search onto intel FPGAs - the work which was offloaded to FPGAs saw a 40x speed increase, resulting in 2x the throughput for bing's search with reduced energy

# asymmetric multicores

- asymmetric multicores are CPUs which exhibit heterogeneity themselves
- cores with different capabilities are tightly coupled, while all being fully programmable, and running the OS
- a single ISA will still be used across all cores
- ==static asymmetry== (ARM big.LITTLE / Intel P vs E cores) involves predefining which cores have what characteristics
- ==dynamic asymmetry== (e.g. turbo boost processors) essentially involves homogeneous cores, which have the ability to be tuned as required - more runtime resources (power/thermal budget) can be allocated to whichever cores need them