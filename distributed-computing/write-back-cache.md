In this cache system the write operation is done in the cache then asynchronously it is done in the DB.

This improve both write and read latency. However, as the operation happens on the DB asynchronously data can be lost, one way to improve is with replication os the cache.