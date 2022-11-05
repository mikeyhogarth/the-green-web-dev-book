# Use the right kind of database

Choose the correct type of database for the job you are doing. By defaulting to popular or familiar database types, you may be missing the opportunity to optimise metrics such as data size and CPU usage, subsequently increasing your energy footprint.

For many years, relational databases such as Postgres, SQL Server and MySQL have dominated the online database landscape. As the web has matured, certain patterns and use cases have emerged for which relational databases are not an ideal fit. Eventually these patterns became common enough to spawn database architectures specifically built around those use cases.

Examples of modern database paradigms include;

| Database Type  | Examples                    | Use for                                                            |
| -------------- | --------------------------- | ------------------------------------------------------------------ |
| Relational     | Postgres, MySQL, SQL Server | Traditional information systems with unpredictable access patterns |
| Key-Value      | Redis, memcached            | Caching, Queues, Leaderboards                                      |
| Document Store | MongoDB, Elasticsearch      | Semi-structured document-oriented data                             |
| Graph Database | Neo4J                       | Fraud Detection, Recommendation Engines, highly relational data    |

The decision around which database to use is highly case-specific, but the core principle is **not to simply default to the popular or familiar choice**. Look at your requirements and choose a database based on those - this might involve doing some research to see how other people solve your particular problem. Think about whether things like **high-availability** or **burst-traffic scalability** are important to you (in which case, SQL might not be the best choice due to its inability to scale easily) or whether or not you can identify all of your access patterns up front (and if not, SQL probably _is_ a good choice due to its flexibility).

Even within each database paradigm there are decisions to be made around **which product to use**, prompting more research. In the case of Key-Value databases for example, there are important differences between [Redis](https://en.wikipedia.org/wiki/Redis) and [memcached](https://en.wikipedia.org/wiki/Memcached) that might make you choose one over the other;

- Redis allows you to persist your data to disk (memcached cannot do this without plugins).
- Memcached is multithreaded, allowing you to handle more operations at once on multi core computers.
- Redis is very feature rich, whereas memcached just does one thing well.
- Memcached benchmarks faster on writes, although has parity with redis on reads.
- Whilst both databases are supported in multiple languages, wider support exists for Redis.

It's also about making your own life easier. Opting for a graph database, for example, brings with it all the graph _algorithms_ you might need such as measures of [centrality](https://en.wikipedia.org/wiki/Centrality) and [distance](<https://en.wikipedia.org/wiki/Distance_(graph_theory)>), or the ability to find clusters. Whilst you _could_ model your graph data within a relational database, this would then require you to write all these algorithms yourself should you want to use them. Not only would this take up a lot of time and effort, your own implementations are unlikely to be as efficient as those provided by a database specifically architected for that kind of task.

Using certain database paradigms also opens up the opportunity to adopt a serverless architecture - [AWS DynamoDB](https://aws.amazon.com/dynamodb/) and [Azure CosmosDB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) are both highly scalable NOSQL databases that offer serverless, consumption-based plans - this means you only pay for what you use, but also that you don't have a database server running 24/7 burning electricity when you're not even using it.

## Relevant Links

- [Databases on Azure](https://azure.microsoft.com/en-gb/product-categories/databases/)
- [Databases on AWS](https://aws.amazon.com/products/databases/)
- [Databases on Google Cloud](https://cloud.google.com/products/databases)
