Leader-based / master-slave replication:

- One of the replicas is designated the leader. When clients want to write to the database, they must send their requests to the leader, which first writes the new data to its local storage.
- The other replicas are known as followers. Whenever the leader writes new data to its local storages, it also sends the data change to all of its followers, as part of replication log or change stream.
- When a client wants to read from the database, it can query either the leader or any of the followers. However, writes are only accepted on the leader.