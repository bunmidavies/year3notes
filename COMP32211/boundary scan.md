[[COMP32211]]

- boundary scan chains are similar to regular [[scan chains]], except the scan chain runs around the boundary of the device - as opposed to through all the flip-flops in between each block
- boundary scan chains are frequently used for not just device testing, but also:
	- device programming - i.e. downloading configurations without connecting via I/O pins, as well as uploading internal states
	- software debugging, for instance ARM processors allow access via JTAG, allowing one to:
		- stop the processor
		- scan an STM instruction onto the instruction input
		- clock an arbitrary number of times
		- stop/start the clock
	- access to memory contents is also possible
- JTAG is the typical boundary scan protocol, named after its developers the Joint Test Action Group - the protocol involves a bypass path, and identity register as well as the boundary scan register, allowing access to more than one scan chain, and multiple devices
- JTAG has a five pin interface to control the boundary scan registers and other elements mentioned above
- DR = Data Registers, which can either be the boundary scan registers, the bypass register, or the IDCODES (?)
![](https://i.imgur.com/pXH48uM.png)

![](https://i.imgur.com/8UYlHmR.jpg)
