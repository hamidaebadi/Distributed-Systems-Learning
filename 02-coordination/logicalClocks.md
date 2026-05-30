
   ### Lamport's logical clock
   - Lamport said that: imagine `a -> b`, where **a** is the event of sending a msg to a process running on another machine. **b** is also the event of receiving that msg. Then, **a** happens before **b** and `C(a) < C(b)` where C is the time clock of event on which all processes must agree upon.

   - The Lamport's algorithm for assigning of time to events: 
