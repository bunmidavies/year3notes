[[COMP32211]]

- APB is essentially a straightforward microprocessor bus
- the bus master puts out a command and corresponding address - then, depending on the operation:
	- read - data read from address provided is latched at the end of a cycle
	- write - data to be written is latched by the end of a cycle, but provided at the start of the cycle i.e. at the same time the enable signal is taken high

- the advantages of APB include:
	- simplicity
	- only a single master is required
- APB is slower than AHB, thus is used for low speed, minimal power peripherals

![](https://i.imgur.com/pS6yhoa.png)

![](https://i.imgur.com/OqsTAAJ.png)
