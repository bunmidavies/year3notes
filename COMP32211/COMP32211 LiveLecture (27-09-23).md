11 lectures + exam
11 lab sessions + own time
guest lecture somewhere after reading week

lectures move towards asic process, and labs use fpga

modern chips may have 10^11 or more transistors
though many of these may be ram

asics may approx, have 10 billion transistors, while fpgas have 100s of millions

practicals:
- verilog implementation
- simulation
- debugging
- simulation continued
- timing
- simulation continued
- testing
- simulation continued
- synthesis

- the 'team' objective - produce a GPU capable of drawing/plotting a range of functions on a display - where the functions are built as programmable hardware
- implemented on fpga

the objective is:
- produce one functional block
- test/verify interfaces
- verify its function
- integrate into an SoC
- demonstrate

### VDU controller
- the VDU controller generates synchronisation/blanking signals, as well as framestore addresses

- framestore: a 2d array of memory with numeric representation of a pixels colour

- double buffering: having more framestore memory than the minimum, its possible to make smoother (tear free) animation