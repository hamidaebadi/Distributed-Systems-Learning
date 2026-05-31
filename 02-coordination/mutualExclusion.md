### Mutual Exclusion

Concurrent process running could make shared resources inconsistence and corrupt. There should be distributed algorithmes to avoid such conflicts. No two process should access the same shared resource at the same time.

#### Permission-based approach
- Asks permission for using a resource from other processes
- There are centeralized, distributed, ring-based and decentralized algorithms.

  **Centralized Algorithm**

	- a process acts as a coordinator, holding resource data and a queue for holding upcoming resource requests
  - process should first contact coordinator to get access to a resource, coordinator checks if the requested resource is free, and if it is free then the permission is given as a reply to the requerster.
  - if the resource is not free -> either block the caller or send a denying message indicating that resource is already in use -> put the request into the waiting queue
  - easy to implement, used in practical situation, guarantee no starvation and deadlock, fairness
  - single point of failure, can be also the bottelneck of the system


  **Distributed Algorithm**

	-  Requester sends msg containing its id and its timestamp to other N-1 processes
  -  Granting permission should come as a reply from all N-1 process
  -  if two processes access a shared resource at the same time, the one with lower timestamp wins
  -  This algorithm guarantee no starvation and deadlock
  -  However, a lot of messages exchanged, N points of failures, hard to implement for dynamic process groups, requester should have a fresh track of all available processes at the time of sending the request.
 
  **Token-Ring Algorithm**

 - Processes layout in a logical ring structure
 - A token travels through the whole ring
 - each process having the token can decide whether it wants to enter its critical section (only once) or not 
 - Pass the token to neighbor in the ring
 - No starvation or deadlock
 - It should be possible to detect crashed processes that was holding the token recently -> generate new token
