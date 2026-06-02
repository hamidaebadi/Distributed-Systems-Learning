### Why Replication?

- improve reliability of the system and protect data corruption
- improve system performance by placing data near its users (geographically spreading) or copying a single server
into multiple replicas and devide the workload among them (increase in size)

- However, consistency problems are the price to pay for achieving performance and reliability -> handling those issues
are extremly difficult

### Replication for better performance

- Replication is used as a technique for improving system performance -> Access time decreases when a replica is placed
near its access entity.

- However, the price is to make sure all replicas get updated instantly when a write operation is performed on one of the
replicas. -> more network bandwith -> might cause again performance problem

- It is also important to keeps these replicas consistent -> Implementing this as atomic operations is inherently difficult. 
This comes from the  fact that keeping replicas consistent mean synchronizing them all together so that they agree on the 
content of correct data -> These requires a lot of communication times and network bandwidth.

- This startegy lead to TIGHT CONSISTENCY -> this is extremly expensive to acheive, but if we loose the requirements of
consistency then we can gain performance withoug making it worse. -> e.g what if we give up about atomic update operations??
