### Fault-Tolerant Distrbitued System Design

- fault-tolerant systems may fail partially but the whole system can still proivde the required services to its users.
- While the system is providing services, the failed components are being repaired.
- Fault-tolerant system is a **dependable** system: A dependable system have requirements for **Availability**, **Reliability**, **Maintainabilit** and **Saftey**.
- A **Available** system is performing without crash at any specific date and time.
- A **highly reliable** system performs for a long time continuously without crash.
- A **Safe** system has no catastrophic results when it failes.
- A **maintainble** system is easy to repaire and no shutdown is needed while repairing.

Faults: might create error, which might create failure -> System crashed

**FAILUER MODELS**

- **Crash Failure**: Server was working correctly before  halting -> No response anymore.
- **Omission Failure**: If it is a Receiver Omission Failure -> Problems in getting the request from client. IF it is a Send-Omission Failure -> Server has done its job but somehow cannot send the response back.
- **Timing Failuer**: Sending response too late -> Performance failuter or too early -> Receipten not ready to get response.
- **Response Failuer**: Server has calculated wrong answers for clients.
- **Arbitrary Failuer**: Server responded with something that should never be returend and the wors case is that the response is never be suspected as a failuer.

**Failure masking with Redundancy**
- Three ways to mask the failure in a distributed systems
- Information Redundancy: Adding more bits to data to recover from arbitrary bit manipulation
- Time Redundancy: An operation/request is redone when no interactions is detected
- Physical Redundancy: More equipment or processes installed to do the job if some of them fail during their execution

