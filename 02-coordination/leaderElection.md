### Leader Election

- Electing a process from a group of processes to act as a coordinator is a common task in Distributed Systems
- Usually algorithms define the way to locate the process with the biggest id to act as a coordinator and make sure all other process agree on whom is selected as coordinator.


#### Bully Algorithm

- The process with biggest ID is selected as coordinator
- when a coordinator is out of service, then all process start election by sending election message to all other processes with greater ID
- If any greater process exists then it takes over the election and send OK to lower process
- This continous untill the biggest process receives no response from other processes and then send a COORDINATOR message to all other lower processes and say the, "heyyyyy! I will be the new COORDINATOR"


#### Ring Algorithm

- Each process knows who is its successor
- A process start election with creating a list and adding its own id to it -> send it to the successor who again add its own id to the list
- this goes all around the ring untill reach the original sender
- then the list contains all processes and their IDs
- Now once a again this list circulates around the ring -> now everyone knows who is the coordinator and who are the members of this ring


