A cache has to be inherently of low latency, which means all cache data has to reside in main memory (RAM). As is the case with most concurrent systems, writes compete with reads and other writes, which requires some form of locking when write is in progress.

- **[[write-through-cache]]**;
- **[[write-around-cache]]**;
- **[[write-back-cache]]**;


As the cache uses the RAM to save its data, it has a limited space thus it needs to have a way to remove data when its capacity is full, amoung many techniques you can find some [[cache-system-evict-strategies]].
