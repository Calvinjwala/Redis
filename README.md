Redis

Redis is what is called a key-value store (key-structure server), often referred to as a NoSQL database. The essence of a key-value store is the ability to store some data, called a value, inside a key.  This data can later be retrieved only if we know the exact key used to store it. We can use the command SET to store the value "fido" at key "server:name”:

SET server:name “fido"

Redis will store our data permanently, so we can later ask "What is the value stored at key server:name?" and Redis will reply with "fido”.

Strings, lists, Sets, hashes, Zsets (sorted sets) are all storable. It can do 300k+ reads/writes per second on 1 core. 

From what I understand, it has atomic operations - so, in a similar way that sockets work, they update in real time and prevent conflict of data. For instance, Redis provides an “incr” option to increase your database by “1” - if user A does this && user B does this, it will show up as 12 (from 10).

You can have a key that expires after a certain amount of time, or one that never expires. You can also push, pop, and “range” information within the db. You can see list length too. It works like JS or Ruby with their commands. Overall, the language and commands are much easier to learn and more intuitive than PSQL. One other one is “superpowers” which can check if a value exists in the array or return 

Redis also provides a sorted set which means that each value has an associated score which can be sorted and returned.

Redis also handles hashes. You can also increment numerical values within hashes.

You can search with exclusion (i.e. search for X, but exclude Y).

Redis is best used for instant analysis --> it cuts the time to process events since it lives in the 
Use Redis for your aggregates since it can all be done on one machine. It allows for a faster database. It gives different access patterns that is typical with a relational database.

It's good for:
-Analytics
- Task Queues         - Small Data
- Distributed Locks   - Bigger Data 
- Caching             - Geo searches
- Data that expires   - Configuration Management
- Cookie storage      - Content distribution
- Search engines
- Ad targeting
- Forums
- Messaging
- High-IO workloads

When Redis does really well...
- When your data model doesn't fit in a relational model very well
- When you have high IO requirements
- When your data fits in memory, or your problem can be sharded
- When you understand Redis' limitations when it comes to data durability


Redis is not a database - it's a database construction kit. You have to build the functionality through Redis. It includes a cache server, messaging server, and aggregate server (incr function allows this)
It is a shared-memory api server.
