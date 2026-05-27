Let's answer to a few important questions.
What is a distributed systems? what are its building blocks and characteristics?
why do even we need a distributed system? 

---


What is a distributed system?
- DS is highly related to computer networks
- a collection of autonomous computing elements -> nodes
- users see a single system, but at the back there is a collection of independently running nodes
- Nodes work for a common objectives --> they need to communicate with eachother via message passing.'
- Networked computers that provide services that have been spread accross many nodes but give illusion of having only one single node for the services.


Challenges & issues in DS
- computing nodes run independently but they have to coordinate their actions with eachother --> No global clock in the whole system --> Coordination and Synchronization are BIG CHALLENGES.

- DS is expected to behave in a way that hides failures of some independent nodes while providing the services to the user without interruptions --> Fault Tolerance.

- DS perfome well in large-scale because of replications of resources to many places, but consistency is a challenge while trying to make systems better using replicas.--> copies of replicas need to be consistent all the time --> Consistency and Replication

- Secure and authorized access is challenge within DS.


Why do we even need to build DS?
- Technological advancements require systems to be able to handler huge amount computations that are requested by users
- to utilize new technologies
