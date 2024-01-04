[[COMP32211]]
[random paper on wave pipelining](https://ieeexplore.ieee.org/abstract/document/711317)
[other princeton paper](https://www.cs.princeton.edu/courses/archive/fall01/cs597a/wave.pdf)

- a wave pipeline is a pipeline ==without intermediate registers or latches== - inputs change periodically and 'waves' of evaluation chase each other through the logic separated by purely the delays of the logic paths
- in principle, this would be the fastest means of implementing logic, but is regarded as quite near impossible in a lot of cases - as the manufacturing process of ICs varies more and more the possibility of wave pipelining becomes even smaller