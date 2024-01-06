[[COMP32211]]

- contrary to [[advanced peripheral bus (apb)]] and [[advanced high-performance bus (ahb)]], axi is oriented to ==transactions== rather than bus cycles
- this interface acts more like a network, than a typical bus - semi-independent channels are used to send information, and multiple masters exist for control signals
- each channel is unidirectional (single) and may be pipelined
- the latency of transfers may be many bus cycles, but the throughput of the interface is improved through [[data bursts]]

- transactions may also be completed in a different order to which they were sent in

- ==write transaction== - a write command {address, burst size} is accompanied with a burst of write data, and concludes with a response status (success, error, abort)
- ==read transaction== - similar to write, but data burst and response status are returned together
- since transactions may complete in different orders, transaction **ID**s on each channel allow elements from multiple outstanding transactions to be matched appropriately

![|300](https://i.imgur.com/hPwZXzc.png)

- in short, AXI allows for faster clocking and higher throughput
![](https://i.imgur.com/aPa6A0Y.png)
