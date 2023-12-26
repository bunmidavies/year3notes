[[COMP32211]]

- 'flat' netlists can be fine for small devices - i.e. you place and route all logic gates in one go
- meanwhile, for SoCs it may be preferable to have a hierarchical layout - for instance this can mean for multicore processors, you layout one core then duplicate the layout for the others
- ==macrocells are essentially, typically large functional blocks== which serve some specific purpose, and can be slotted into a layout - turning some part of a design into layout is known as 'hardening', so macrocells and 'hardened' layout may be used interchangeably
- the most common macrocells are things such as:
	- memory
	- adder components
	- multiplier building blocks
	- complete microprocessors
	- specialist systems
- the process of placing these macrocells is typically called ==floorplanning==
- macrocells can prove useful since despite perhaps slightly suboptimal in some cases, its much faster to perform the floorplanning and its much easier to verify timing since you only have one version to test

- a lot of FPGA designers may use macrocells, and thus cannot modify those hardened designs but will still find them useful
![](https://i.imgur.com/QAFdd4p.png)
