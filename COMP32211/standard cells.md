[[COMP32211]]
[wiki](https://en.wikipedia.org/wiki/Standard_cell)

- standard cells are essentially just implementations of common components, turning a bunch of logic gates into one big gate that can be used however is required
- the process of converting specified designs into cells which can be laid out on a chip is known as ==technology mapping==, which can be thought of as a type of parallel to program compilation
- CAD tools will typically provide cells within some sort of component cell library in order to ensure reliability - different CADs may hide the underlying logic gate layout and only provide inputs/outputs, while others may display everything

- within typical CAD cell libraries, one might expect all the common gates i.e. AND, NAND, NOR, XOR, XNOR to be available with a range of inputs, and variety of drive strengths
- additionally, flip flop variants and other latches will probably be available, as well as more complex gates like multiplexers
- ==the majority of VLSI (very large scale ICs) are built from standard cells==

![](https://i.imgur.com/v3UWdbi.png)
