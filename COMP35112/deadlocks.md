[[COMP35112]]

- in this example, a deadlock occurs from two threads calling the same `transfer` function but with opposite sender/recipients - this means neither thread can acquire the locks for both sender and recipient, so both wait infinitely

![](https://i.imgur.com/0h1Io29.png)

- a solution to this is to assign unique ids to each accounts, then sort these and always acquire the locks in a deterministic order