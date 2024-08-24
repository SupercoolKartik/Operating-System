
- **Purpose:** The WFG is a simplified version of the RAG, used specifically to model and analyze deadlocks.
- **Components:**
    - **Nodes:** Only processes are represented as nodes.
    - **Edges:** A directed edge from process Pi to process Pj (Pi → Pj) indicates that Pi is waiting for a resource that Pj is currently holding.
- **Usage:** The WFG is directly used for deadlock detection. A cycle in the WFG indicates the presence of a deadlock.