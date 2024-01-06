[[COMP32211]]

- a data burst essentially allows you to transfer more data than what a bus can typically hold in a single transaction, while still being constrained to a single transaction
- for instance, a data burst could allow you to transfer 128 bits of data in a single transaction, when the bus only holds 32 bits of data, through a burst of 4 beats  
- data bursts are useful because you can reduce transaction overhead for certain amounts of data transfer, increasing throughput - with the example above, you're essentially performing 4 transactions while only paying the overhead of 1 transaction