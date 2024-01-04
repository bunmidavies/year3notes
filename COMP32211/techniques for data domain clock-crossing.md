[[COMP32211]]

- the main concern when transferring substantial amounts of data across clock domains is that synchronisation introduces latency - if each item was synchronised independently, bandwidth is relatively low and latency reflects this as well
![](https://i.imgur.com/000dFqe.png)

- items can be batched up into a buffer, and the entire buffer would be synchronised as one - this can be useful for block transfers. Bandwidth is increased, but so is latency
![](https://i.imgur.com/mgquhHe.png)

- FIFO queues can be implemented in order to 'hide' the latency of all but the first item - latency is thus reduced and bandwidth increased, but at the cost of complexity
- perhaps the most complex technique shown in the notes is the combination of the FIFO with buffered values:
![](https://i.imgur.com/tFMn4lp.png)

- ==double buffering== is also a possible technique, where one buffer is sent off to the other clock domain, and while that is synchronised and being emptied, another buffer is being filled with data - this comes at the cost of more RAM being required, but the obvious advantage of increased bandwidth
- ==decoupling FIFOs== can be used for close to max throughput and minimum latency, but are a slightly harder concept to understand - they involve a counter which increments with each write completed, and decrements with each read completed 