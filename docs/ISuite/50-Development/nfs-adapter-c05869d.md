<!-- loioc05869d8a02e47d785be0bd6968a8d51 -->

# NFS Adapter

The NFS \(Network File System\) adapter for SAP Integration Suite enables connectivity to NFS server facilitating read and write operations for files. For detailed information regarding adapter configuration, find relevant links at the end of the page.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



## NFS Sender Adapter Features

-   Ability to read files from an NFS folder and its subdirectories.
-   Allows configuration to set the maximum number of files retrieved per poll and the maximum file size that can be read.
-   Support for multiple Post-processing actions such as Move File, Delete File, and Keep File and Process Again.
-   Enables File Archival using Move File under post-processing options.
-   Prevents reprocessing of the same file using Duplicate Checks. The duration can be specified using Duplicate Expiry period field.
-   Supports Regex and Wildcard patterns for file selection.



## NFS Receiver Adapter Features

-   Ability to write to a file on the NFS server. \(allows directory creation while creating a file.\)
-   Add Timestamp or Message ID to the filename.
-   Allows user to specify chunk size for efficient file write operation.
-   Provides multiple Existing File Handling options such as Override, Append, Fail, and Ignore.
-   Provides temporary file checkbox option while writing to a file to ensure data integrity.

**Related Information**  


[Prerequisites and Operational Considerations](prerequisites-and-operational-considerations-9efec9e.md "This topic contains information about adapter architecure, application configuration, and authentication considerations relevant to the NFS Adapter.")

[Configure the NFS Sender Adapter](configure-the-nfs-sender-adapter-c255074.md "NFS Sender Adapter provides the ability to read files from the NFS Server.")

[Configure the NFS Receiver Adapter](configure-the-nfs-receiver-adapter-0ed683b.md "NFS Receiver Adapter provides the ability to write to a file on the NFS server.")

