[[COMP32211]]

- scan chains are another form of [[post production tests]] - they exist as a means to achieve ==controllability and observability== of 'buried' logic blocks
- flip flops are placed in the normal way, but late in the process are replaced with ==scan flip-flops== - these flip-flops have a second mode of operation (the first mode being the regular flip flop mode), controlled by a global input, which allows their input to be taken from another scan flip-flop
- this essentially turns the chain of scan flip flops into a long shift register
- there is an associated performance cost for substituting flip-flops with scan flip-flops, but the benefits include:
	- improved testability, since it becomes easier to apply test patterns
	- the ability to test logic blocks in parallel - thus reduced test time
	- output of each scan flip flop can be fully passed out to the chip for further analysis, improving observability

![](https://i.imgur.com/FsAJ5pz.png)
