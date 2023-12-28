[[COMP32211]]

more or less just taken from the slide:
- future SoCs are likely to contain ==many processors== - some of which will be explicit multiprocessor chips
- processors are too useful to not be duplicated for both testing and redundancy purposes

- future SoCs will also likely have multiple regions with different clocks, power supplies, etc. - regions could also be asynchronous, and communicate with each other in a similar manner to computer networks
- regions can also be powered off when not in use ([[dark silicon]])

- hardware will become more reconfigurable (see 'hard' processors within big FPGAs e.g. xilinx 'zynq') - by introducing dynamically reconfigurable accelerators, parts of arbitrary software algorithms can be somewhat 'compiled' to be executed in hardware (thus requiring less power and being much faster)
- ==the distinction of software and hardware is expected to blur eventually==