
### Lamport's logical clock
- Lamport said that: imagine `a -> b`, where **a** is the event of sending a msg to a process running on another machine. **b** is also the event of receiving that msg. Then, **a** happens before **b** and `C(a) < C(b)` where C is the time of the event on which all processes must agree upon.

- The Lamport's algorithm for assigning times to events:
  - Each process P<sub>i</sub> holdes a counter C<sub>i</sub> = local time of the process before happening of an event
  - Increment C<sub>i</sub> += 1
  - set the time stamp of P<sub>i</sub> to C<sub>i</sub> i.e ts(P<sub>i</sub>) = C<sub>i</sub>
  - Send the message m to process P<sub>j</sub>
  
     **On receiving side:**
   - Upon receiving of m from Netwrok layer, P<sub>j</sub> sets its counter = max(C<sub>j</sub>, ts(m))
   - increment its counter clock and delivers the message to the application level
---

### Vector Clocks

Lamport's logical clock helps us to synchronize events by assigning logical times to events and compare their timestamps to find out if some event happen before another event. However, that might not always be the case . For example, process P1 might send a message m1 to P2 --> by lamport's logical clock the receiving time of m1 in P2 is greater than the sending time m1 from P1. Now suppose that process P3 sends a message m2 to P2 --> if sending time of m2 < receiving time of m1, then can we conclude that m2 was triggered by m1??!? --> Definitly not, because m2 was sent independently of m1 from P3 to P2.

So, Lamport's logical clock cannot detect causalities. 
Inorder to detect causalities we need vector clocks

How does it work?

Vector clock works by maintinig a vector for each process in the following way: 
- Each process mainatains a vector containing n entries for n processes
- A process Pi contains the number of events happened locally in the ith position of the vector.
- Any jth-position in the Pi process's vector keeps track of events that happened till that time in the process pj.
- When a message m is about to sent from process Pi to Pj -> an event (call it a) is created locally.
- Process Pi vector's ith position is incremented
- Process Pi sends message m with current updated vector to process Pj.
- Upon receiving, Pj merges its own vector with the received vector data
- increments its jth-position in the vector and pass it to the application layer
- compare vectors and detect causalities if necessary
