### Data-Centeric Consistency Models

We define shared data resource that maybe physically distributed as **data store**.
Consistency models are just contracts between processes and data stores and says that if a process obey certain
rules then the data store is going to work fine under specific consistency model.

#### Consistent Ordering Operations

**Sequential Consistency**

- In a distributed system that many processes (physically separeted machines) are executing in parallel (concurrently), they do some operatinos on a shared data store.

- The data store is said to be sequentially consistent if all processes agree on any valid order of interleaving operations.

**Causal Consistency**

