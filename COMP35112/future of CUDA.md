[[COMP35112]]

- currently, CUDA's conventions and boilerplate code required makes implementing high performance algorithms awkward at times - within the future, improvements to CUDA include:
	- unified host & device code
	- execution space inference
	- unified memory space (therefore data doesn't need to be copied to/from device)
	- almost full C++17 support