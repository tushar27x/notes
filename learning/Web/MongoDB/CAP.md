- The CAP theorem states that it is not possible to guarantee all three of the desirable properties- consistency, availability and partition tolerance at the same time in a distributed system with replication.
- It states that networked shared-data systems can only strongly support two of the three properties

#### Consistency
- means that the nodes will have the same copies of a replicated data item visible for various transactions.
- Consistency refers to every client having the same view of the data.

#### Availability
- means that each read or write request for a data item will either be processed successfully or will receive a message that the operation cannot be completed.

#### Partition Tolerance
- means that the system can continue operating even if the network connecting the nodes has a fault that results in two or more partitions, where the nodes in each partition can only communicate with each other.
- That means, the system continues to function and upholds its consistency guarantees in spite of network partitions.