[[COMP35112]]

# explicit parallelism

- the programmer explicitly spells out what should be done in parallel/sequence - this means that code modifications are required if the sequential program is already available
- examples include programming w/ threads or using openMP

# implicit parallelism

- no effort is required from the programmer, and the system works out what can be parallelised on its own - for this reason, it means no code in a sequential program must be modified
- some languages with the ability to make strong assumptions about data sharing (e.g. functional languages have 'pure' functions with no side effects) will do this