# High Level Design Comprehensive Guide

## Core Concepts

### Scalability
- **Vertical**: Increase server capacity (CPU/RAM) for single machine.  
  *Application*: Monolithic apps needing quick performance boost
- **Horizontal**: Add more servers to distribute load.  
  *Application*: Web applications expecting user growth

### Availability Metrics
- **SLA**: Contractual uptime guarantee (e.g., 99.9%).  
  *Application*: Cloud service provider commitments
- **SLO**: Internal performance targets.  
  *Application*: Team benchmarks for API response times
- **SLI**: Measured metrics like error rates.  
  *Application*: Monitoring dashboards

### CAP Theorem
- Choose 2: Consistency, Availability, Partition Tolerance.  
  *Application*: NoSQL databases prioritize availability over strong consistency

## Databases

### ACID vs BASE
- **ACID**: Guarantees reliable transactions (banks).  
  *Application*: Financial systems requiring precision
- **BASE**: Favors availability over consistency.  
  *Application*: Social media feeds where eventual consistency suffices

### Database Sharding
- **Hash-based**: Even distribution via hash function.  
  *Application*: User data partitioning by userID hash
- **Range-based**: Partition by value ranges (dates).  
  *Application*: Time-series data like sensor readings

## System Architecture

### Microservices
- Independent services with own data stores.  
  *Application*: E-commerce platforms separating payment, inventory, shipping

### Event-Driven Architecture
- Components react to events/messages.  
  *Application*: Real-time notifications in chat applications

## Performance

### Caching Strategies
- **CDN**: Geographic content distribution.  
  *Application*: Static assets for global websites
- **Redis**: In-memory key-value store.  
  *Application*: Session storage for web apps

### Rate Limiting
- **Token Bucket**: Fixed capacity refilled over time.  
  *Application*: API request throttling
- **Leaky Bucket**: Fixed output rate.  
  *Application*: Smoothing traffic bursts

## Distributed Systems

### Consistent Hashing
- Minimizes redistribution when scaling.  
  *Application*: Distributed caching systems like Memcached

### Leader Election
- Chooses coordinator node in cluster.  
  *Application*: Database clusters ensuring write consistency

## Security

### OAuth 2.0
- Delegated authorization framework.  
  *Application*: "Login with Google" functionality

### JWT
- Stateless token-based authentication.  
  *Application*: Single sign-on (SSO) systems

## Deployment

### Blue-Green Deployment
- Two identical environments switch traffic.  
  *Application*: Zero-downtime production updates

### Canary Releases
- Gradual rollout to user subsets.  
  *Application*: Testing new features with 5% of users

## Storage

### Object Storage (S3)
- Unlimited scalable file storage.  
  *Application*: User-generated content like profile pictures

### Time-Series Databases
- Optimized for timestamped data.  
  *Application*: IoT sensor data collection

## Real-World Patterns

### Circuit Breaker
- Fails fast when downstream fails.  
  *Application*: Preventing cascading failures in microservices

### Saga Pattern
- Manages distributed transactions.  
  *Application*: E-commerce checkout across services

## Observability

### Distributed Tracing
- Follows requests across services.  
  *Application*: Debugging latency in microservices

### SLO Monitoring
- Tracks service level objectives.  
  *Application*: Ensuring 95% of requests <200ms

## Messaging

### Pub-Sub Model
- Publishers → Topics → Subscribers.  
  *Application*: Stock market data distribution

### Dead Letter Queues
- Stores failed messages.  
  *Application*: Retry mechanisms for payment processing

## Optimization

### Bloom Filters
- Space-efficient probabilistic lookup.  
  *Application*: Check username availability

### Geohashing
- Encodes geographic coordinates.  
  *Application*: Location-based restaurant searches
