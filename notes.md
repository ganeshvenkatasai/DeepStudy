
# System Design Fundamentals

## 1. Key Concepts

### Scalability
- **Vertical Scaling**: Increase resources of a single node (CPU, RAM)
- **Horizontal Scaling**: Add more nodes to the system

### Availability
- Measured as percentage of uptime (e.g., 99.9% = "three nines")
- Strategies:
  - Redundancy
  - Failover mechanisms
  - Load balancing

## 2. Database Patterns

```sql
-- Example SQL for read replicas
CREATE DATABASE replica_db AS REPLICA OF main_db;
```

### Replication Types
| Type          | Pros                  | Cons                  |
|---------------|-----------------------|-----------------------|
| Master-Slave  | Simple to implement   | Single point of failure |
| Multi-Master  | High availability     | Conflict resolution needed |

## 3. Caching Strategies

```python
# Python example using Redis
import redis

cache = redis.Redis(host='localhost', port=6379)
cache.set('user:123', '{"name": "John", "age": 30}')
```

### Cache Invalidation
1. **TTL** (Time To Live)
2. **Write-through**
3. **Write-behind**

## 4. Load Balancing Algorithms

> "The key to scaling is distributing load evenly across resources." - System Design Principle

- **Round Robin**
- **Least Connections**
- **IP Hash**

## 5. CAP Theorem

*Consistency*  
*Availability*  
*Partition Tolerance*

Pick **two** out of three in distributed systems.

## 6. Example API Design

`GET /api/users/<id>`  
```json
{
  "id": "123",
  "name": "Alice",
  "email": "alice@example.com"
}
```

## 7. Checklist for Design Interviews

- [ ] Clarify requirements
- [ ] Define API contracts
- [ ] Estimate scale
- [ ] Choose database
- [ ] Plan caching
- [ ] Consider security
