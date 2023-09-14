<!-- loio1577f7742507413081f50c3c80a9bd7a -->

# Partner Directory Cache

To improve performance, Partner Directory is cached.

Entities from the Partner Directory are cached on runtime nodes. From there, they can be accessed with good performance from Script steps in integration flows deployed on the same runtime node.

The following Partner Directory entities are cached:

-   StringParameter

-   BinaryParameter

-   AuthorizedUser


If an object \(for a requested key\) is not found in the cache, it is loaded from the Partner Directory.

Maximum cache size is restricted to 5% of the total heap size. Elements are evicted from the cache according to the Least Recently Used order.

An entry in the cache is invalidated when the entry is updated or deleted. This invalidation can take a few minutes. The invalidation time depends on the number of changes that are done during design time. The more changes are done at the same time, the longer the invalidation takes.

