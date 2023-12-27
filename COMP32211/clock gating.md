[[COMP32211]]
[wiki](https://en.wikipedia.org/wiki/Clock_gating)

- clock gating is a popular power management technique, which simply involves removing the clock signal from a circuit when the circuit is not in use
- by stopping the clock, any flip flops in the circuit wont be constantly switching state, which requires power
- clock gating must not introduce glitches when turned on and off, nor impose any clock ==skew==
- unlike techniques like [[dark silicon]], the circuit itself can remain switched on, such that any info held in registers/memory is not lost