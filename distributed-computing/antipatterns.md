Antipatterns in distributes systems that should be avoided in the context of cascading failures. Laura Nolan proposes six of these.

- **Acceptance of an unrestricted number of requests**: The number os requests which a server can receive should be limited. A server should not be allowed to receive more requests than it supports, it is betten fail fast dropping excessive requests than trying to take more time to processed than. The settings should be in a range where the server can reach peak loads, but not so much that it blocks. On proxies or load balancing it is settings implementing the **rate limiting** strategies. Moreover, in the context of queue, if the number of message increase beyond the queue capacity, requests are rejected, if there is a event where the number of requests will increase a large queue should be used. To protect server from excessive load, the concepts of [[load-shedding]] and [[graceful-degradation]].

- **Dangerous (client) retry behavior**: In order to prevent the server to be overloaded by retries requests, client should increase the intervals for retries. I can be uniformly done or generate a random number for each interval. This prevents the system from being hit by accumulating "load waves". The [[circuit-break]] pattern can mitigate this antipattern. Retries should be idemponent and free from side effects.

- **Crashing on bad input**: System should not crash when it receives a bad input from the user, combining this with the retry behavior can be disastrous to the system. Input from outside should be checked in this regard. Using fuzz tests is a good way to detect these type of problems.

- **Proximity-base failover**: When a data center/server failed all requests should not be redirect to the closest data center/server, because it can make other crashes as well. The redirect should be done in a controller manner during failover, which means you have to consider the maximum capacity of each data center.

- **Work prompted by failure**: Failure often cause additional work in the system. In particular, a failure in a system with only a few nodes can lead to a lot of additional work (e.g., replication) for the remaining nodes. This can lead to a harmful feedback loop. A common mitigation strategy would be to delay or limit the amount of replication.

- **Long startup times**: After a failover, when a service starts running again it can receive a lot of requests due to the retries, therefore a long startup time can make the service goes down again. To prevent this you should prefer systems with a fast startup time.

## References

https://blog.mi.hdm-stuttgart.de/index.php/2022/03/03/cascading-failures-in-large-scale-distributed-systems/