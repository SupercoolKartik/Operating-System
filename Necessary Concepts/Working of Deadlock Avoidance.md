
Let's understand the working of Deadlock Avoidance with the help of an intuitive example.

|Process|Maximum Required|current Available|Need|
|---|---|---|---|
|P1|9|5|4|
|P2|5|2|3|
|P3|3|1|2|

Let's consider three processes P1, P2, P3. Some more information on which the processes tell the Operating System are :

- P1 process needs a maximum of 9 resources (Resources can be any software or hardware Resources like tape drive or printer etc..) to complete its execution. P1 is currently allocated with 5 Resources and needs 4 more to complete its execution.
- P2 process needs a maximum of 5 resources and is currently allocated with 2 resources. So it needs 3 more resources to complete its execution.
- P3 process needs a maximum of 3 resources and is currently allocated with 1 resource. So it needs 2 more resources to complete its execution.
- The Operating System knows that only 2 resources out of the total available resources are currently free.

**But only 2 resources are free now**. Can P1, P2, and P3 satisfy their requirements? Let's try to find out.

As only 2 resources are free for now, only P3 can satisfy its need for 2 resources. If P3 takes 2 resources and completes its execution, then P3 can release its 3 (1+2) resources. Now the three free resources that P3 released can satisfy the need of P2. Now, P2 after taking the three free resources, can complete its execution and then release 5 (2+3) resources. Now five resources are free. P1 can now take 4 out of the 5 free resources and complete its execution. So, with 2 free resources available initially, all the processes were able to complete their execution leading to a Safe State. The order of execution of the processes was <P3, P2, P1>.

What if initially there was only 1 free resource available? None of the processes would be able to complete its execution. Thus leading to an unsafe state.

We use two words, safe and unsafe states. What are those states? Let's understand these concepts.

### Safe State and Unsafe State

**Safe State** - In the above example, we saw that the Operating System was able to satisfy the needs of all three processes, P1, P2, and P3, with their resource requirements. So all the processes were able to complete their execution in a certain order like P3->P2->P1.

So, **If the Operating System is able to allocate or satisfy the maximum resource requirements of all the processes in any order then the system is said to be in Safe State.**

**So safe state does not lead to Deadlock**.

**Unsafe State** - If the Operating System is not able to prevent Processes from requesting resources which can also lead to a Deadlock, then the System is said to be in an Unsafe State.

**Unsafe State does not necessarily cause deadlock it may or may not cause deadlock**.

![[safe-unsafe-state.jpg]]




>[[Deadlock Avoidance Example]]