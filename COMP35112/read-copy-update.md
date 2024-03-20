[[COMP35112]]

- RCU is used for protecting a critical section while allowing concurrent ==lockless== readers
- RCU is suitable for situations where ==its OK for concurrent readers not to see the same state for a given piece of data==, as long as ==all see a consistent state==
- RCU is extensively used in the kernel

# RCU example: linked list update

- given we have a singly linked list, there are two main roles within the list:
	- readers traverse the list to read data from certain nodes
	- writers traverse the list to update data contained in certain nodes, as well as adding/deleting elements
- if we want to update an existing node, the following steps are taken:
	1. allocate a new node
	2. copy the target node's (node to be updated) data
	3. perform whatever update is required
	4. make the copy point to the same next node
	5. ==atomically swap previous node pointer to new node==
	6. observe a ==grace period==: waiting for outstanding readers on the old queue state to no longer be pointing to the target node
	7. once there are no more readers on the target node (i.e. grace period ends), free the old node
- ==note that this is only acceptable where its OK for two readers to see different states of the same node== - the difference in essence is consistent, so ==readers do not need a lock==
- however, ==writers do need a lock==