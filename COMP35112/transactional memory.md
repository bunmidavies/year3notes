[[COMP35112]]

- transactional memory follows the idea of transactions for databases, except the transactions are used for parallel threads instead
- transactions are ==indivisible==, meaning for external observers, they either happen or not:
	- while executing, changes inside the transaction are not visible outside


- within hardware, TM can be implemented with the use of caches

| TM             | Caches              |
| -------------- | ------------------- |
| Read/write-set | Read/write tag bits |
| Transmitting   |                     |