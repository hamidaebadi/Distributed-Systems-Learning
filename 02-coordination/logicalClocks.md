
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
