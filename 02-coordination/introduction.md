### Coordination in Distributed Systems
---

* In a distributed systems computing nodes should usually make decision or agree on something together
* e.g a process wants to run it's critical section and it should make sure no other process do the same while it is running
* Inorder to avoid conflictions, inconsistencies and detecting failures, we need to coordinate computing nodes' actions

#### General issues related to coordination in Distributed Systems

Now let's talk about common issues in this challenging topic. Coordination is a critical and complex issue -> so much research has been done in this concept.

##### Lack of Global Clock in the system 
 - Each computing node has its own local clock -> their clocks are not usually synchronized
 - If two processes do not interact with each other, there is no need to agree on a time.
 - Most process don't care about exact absolute time, but the relative ordering of events among processes is much more attractive to them -> LOGICAL CLOCK.
