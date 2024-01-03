[[COMP32211]]

- the purpose of the ==Video Display Unit (VDU)== controller is to generate:
	- synchronisation and blanking signals
	- framestore addresses, while also reading framestore data to determine pixel values
	- serialise pixel values, and send them to the display at the pixel rate
- it is a fairly simple state machine, often programmable to accommodate various displays (different size, colours, aspect ratios)