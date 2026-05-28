### Coordination in Distributed Systems
---

* In a distributed systems computing nodes should usually make decision or agree on something together
* e.g a process wants to run it's critical section and it should make sure no other process do the same while it is running
* Inorder to avoid conflictions, inconsistencies and detecting failures, we need to coordinate computing nodes' actions

#### General issues related to coordination in Distributed Systems

Now let's talk about common issues in this challenging topic. Coordination is a critical and complex issue -> so much research has been done in this concept.

##### Lack of Global Clock in the system
