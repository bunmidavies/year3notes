[[COMP35112]]

- ==the ideal level for user code to interface with heterogeneous systems is at the DSL/API level==
- although heterogeneous systems seem to provide numerous benefits, they pose certain issues related to actually being used:
	- capabilities are unknown (before install time)
	- availability of the system's different parts are unknown before runtime
	- the relative benefit of each system is unknown until after runtime

# providing functional portability

- single source approaches i.e. using the same source for all heterogeneous devices - aims to allow a wide range of devices to be able to run the given code
- *low level approach* = [[OpenCL]] allows such programs to be written - programs are distributed with OpenCL source, such that they are device-agnostic, and can run on CPUs, GPUs, FPGAs, Tensor HW etc, making OpenCL a ==layer of compatibility==
- *high level approach* = [[SYCL]] allows valid c++ code with a higher level abstraction to OpenCL to be written, while allowing the code to be automatically compiled into languages for different devices and vendors

# providing performance portability

- the main idea to provide both functional portability as well as performance portability is to use a higher level of abstraction
- domain specific languages (DSLs) and library APIs (e.g. BLAS) for specific problems aim to be responsible for providing performance portability