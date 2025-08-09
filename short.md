# System Design Short Notes

## Core Principles
- **KISS**: Keep It Simple, Stupid
- **YAGNI**: You Aren't Gonna Need It
- **Horizontal > Vertical Scaling**

## Databases
- **SQL**: ACID transactions, rigid schema  
  `SELECT * FROM users WHERE id = 123;`
- **NoSQL**: Flexible schema, scales horizontally  
  `db.users.find({_id: 123})`

## Caching
- **Redis**: Key-value store, sub-millisecond latency
- **Memcached**: Simpler than Redis, no persistence
- **CDN**: Cache static assets globally

## Load Balancing
- Round Robin
- Least Connections
- IP Hashing

## CAP Theorem
```
   C
  / \
 A---P
```
Choose 2:
- **CA**: Traditional DBs (PostgreSQL)
- **CP**: MongoDB, Redis
- **AP**: Cassandra, DynamoDB

## API Design
- REST: Resource-based (`/users/{id}`)
- GraphQL: Query language
- gRPC: Protocol buffers, binary format

## Microservices
- Pros: Independent scaling, tech diversity
- Cons: Network latency, distributed tracing

## Message Queues
- Kafka: High throughput, ordered logs
- RabbitMQ: Flexible routing, AMQP protocol

## Rate Limiting
- Token bucket
- Leaky bucket
- Fixed window counter

## Storage
- **Hot**: SSD (frequent access)
- **Cold**: HDD/Glacier (archive)
- **Object**: S3, Blob Storage

## Monitoring
- **METRICS**: Prometheus
- **LOGS**: ELK Stack
- **TRACING**: Jaeger/Zipkin
