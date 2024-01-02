[[COMP22111]]

there are various properties to note about clock distribution:
- clocks have ==high fan-out==, since they may be used for thousands of flip flops ([[network fan-out]])
- clock edges should be fast, since a slower edge increases uncertainty in when exactly a transition happens
- clock signals are repetitive - the latency at which a clock signal reaches a flip flop does not matter so much, as long as they always arrive at regular intervals

- clock signals may need to be electrically buffered, which is okay ==provided clock skew remains small==
- since the clock signal is distributed over an area of a chip with buffers, this can be referred to as a [[clock tree]]


the main goals of clock distribution are as follows:
- the clock should be phase-aligned with an external input clock
- skew should be 0 (or at least well characterized)
- jitter should be 0
- the set up time + data hold time should be 50/50 (or at least well characterized)

other goals of clock distribution include:
- the clock network should use a low amount of power
- the distribution should be simple to design and verify
- clock generation should support testing and debugging