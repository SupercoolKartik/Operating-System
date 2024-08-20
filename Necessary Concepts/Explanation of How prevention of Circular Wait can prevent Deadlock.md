Circular wait is one of the necessary conditions for a deadlock to occur in a system. Preventing circular wait can therefore help in avoiding deadlocks. One effective way to prevent circular wait is to **impose a resource ordering** on all the resources in the system and require that processes request resources in a predefined, increasing order.

### Circular Wait Condition

Circular wait occurs when a set of processes are waiting for each other in a circular chain, where each process holds at least one resource and is waiting to acquire a resource held by the next process in the chain. For example:

- Process P1 holds Resource R1 and waits for Resource R2.
- Process P2 holds Resource R2 and waits for Resource R3.
- Process P3 holds Resource R3 and waits for Resource R1.

This creates a circular chain (P1 → P2 → P3 → P1) where none of the processes can proceed, leading to a deadlock.

### Imposing Resource Ordering

To prevent circular wait, the operating system can impose a global order on all the resource types. This means assigning a unique number (or priority) to each resource type. Once this ordering is established, every process must request resources in a strict sequence according to this ordering.

### Example of Resource Ordering

Let’s assume there are three resources: R1, R2, and R3. We impose an ordering such that:

- R1 has the lowest priority (1),
- R2 has a medium priority (2),
- R3 has the highest priority (3).

### Rules for Resource Request

1. **Increasing Order of Request:**
    - A process must request resources in the order of their assigned numbers.
    - If a process needs R1, R2, and R3, it must request R1 first, then R2, and finally R3. It cannot request R2 before R1, or R3 before R2.
2. **No Backtracking:**
    - Once a process has acquired a higher-order resource, it cannot request a lower-order resource. For example, if a process has already acquired R2, it cannot go back and request R1.

### Why Does This Prevent Circular Wait?

By enforcing this order, you eliminate the possibility of circular chains. Here’s why:

- Assume two processes P1 and P2 are requesting resources. If P1 requests R1 and R2, it must do so in that order (R1 first, then R2).
- If P2 also needs R1 and R2, it too must request them in the same order.

Because all processes follow the same order, it’s impossible for one process to be waiting for a resource held by another process that itself is waiting for a resource held by the first process in a reversed order. There’s no way to form a circular chain of dependencies because the resource requests flow in one direction only.

### Practical Example

Consider two processes P1 and P2 in a system with three resources: R1, R2, R3, and they follow this resource ordering:

- **P1** requests R1, and then R2.
- **P2** requests R2, and then R3.

Since P1 must request R1 before R2, and P2 must request R2 before R3, even if P1 and P2 are both holding one resource and waiting for the other, the system will not form a circular wait.

- P1 can never wait for a resource that P2 holds while P2 is waiting for a resource that P1 holds, because of the strict ordering.