A **dirty bit** is a flag(initially set to 0) used in memory management to indicate whether a page in memory has been modified since it was loaded from disk. It helps optimize memory operations by keeping track of whether a page needs to be written back to disk when it's replaced or swapped out.

When the system needs to replace a page in memory (during **page replacement**), it checks the dirty bit of that page:

- **Dirty bit = 0 (clean page)**: The page has not been modified, so there's no need to write it back to disk. It can simply be removed from memory.

- **Dirty bit = 1 (dirty page)**: The page has been modified, so it must be written back to disk before being replaced. This ensures that no changes are lost.
