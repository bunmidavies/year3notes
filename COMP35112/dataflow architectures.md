[[COMP35112]]

- [[functional programming for parallel programming|functional languages]] essentially return a graph of evaluations, representing how data flows as well as each operation's prerequisites / dependents
- these graphs can be represented with ==dataflow graphs==, where instructions are nodes, and data flow is represented with edges
- dataflow machines exist to execute these dataflow graphs, with specific principles in mind:
	- data values flow to instructions, as opposed to instructions flowing into a processor and modifying its state
	- when all operands are ready, the instruction consumes them and generates a new value

# graph example: $b^2 - 4ac$

![350](https://i.imgur.com/hK8HzcV.png)

- loops can also be represented, by using $F$ to represent the flow of the program as some operand into another edge to represent the instruction should be run again

# programming dataflow machines

- typical machine code is tedious for representing graphs, so instead, higher level functional programming languages, or single assignment languages can be used
- single assignment language = language where a variable can only be assigned to once (e.g. LLVM IR)

# manchester dataflow machine

components:
- token queue - buffering + inserting new data
- matching store - used to match tokens with the according instructions
- instruction store - stores a representation of the dataflow graph
- processor bank - executes actual instructions with operands

the machine used SISAL (stream and iteration in a single assignment language), invented by Lawrence Livermore in the 80s - the language was imperative-friendly, but could be easily compiled into a dataflow graph or for use in any highly parallel machines

moving tokens around a large network, as well as using a huge amount of chips meant the computer became too expensive for what it was worth. However, the concept of limited dataflow is a precursor to things like OoO execution, signal processing, tasked-based computing, etc.

