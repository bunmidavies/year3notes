[[COMP34111]]
[wiki](https://en.wikipedia.org/wiki/Monte_Carlo_method)

- Monte Carlo methods encompass a broad class of computational algorithms, typically relying on repeated random sampling, and using such randomness to find answers which may be deterministic in principle

- Monte Carlo methods typically follow a particular pattern:
1. define a domain of possible inputs
2. generate inputs randomly from a probability distribution over the domain
3. perform a deterministic computation on the inputs
4. aggregate the results

- in monte carlo learning specifically, ==you learn while you play, in between moves== - this contrasts to TD-learning, where you learn first, and then you play