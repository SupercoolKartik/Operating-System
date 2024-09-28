The **dirty page** refers to a page in memory that has been modified since it was loaded from disk but hasn't yet been written back to the disk.

- **When a page is loaded into memory** from the disk (let’s say it's part of a file or program), the data in that page is the same in both memory and disk.
    
- **Modifying the page**: As a program runs, it might modify the data in that page (for example, writing to a variable stored in memory). At this point, the version of the page in memory is different from the version on disk. This is when the [[Dirty Bit]] gets set to indicate that the page has been **"modified"** or **"dirty"**.