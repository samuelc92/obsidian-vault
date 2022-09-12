In this cache system the write operation goes direcly to the Database then the cache read the value from the DB in case of a miss.

The downside of this system is that the read latency will be increased because the cache will go more often to the DB.

On the other hand the write latency will be faster comparing to the [[write-through-cache]].