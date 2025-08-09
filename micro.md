# System Design Micro Notes

## 💾 Databases
- **SQL**: `JOIN` = expensive at scale
- **NoSQL**: Schema flexibility = app-managed consistency
- **Indexes**: Fast reads, slow writes

## ⚡ Caching
- **Redis**: `SET user:123 "data" EX 3600`
- **Cache Hit**: <1ms, **Miss**: 100x slower
- **Invalidation**: Harder than you think

## 🔌 Protocols
```
HTTP/1.1 vs HTTP/2
┌───────────┬────────────┐
│ 1.1       │ 2          │
├───────────┼────────────┤
│ Text      │ Binary     │
│ No multiplex │ Multiplexing │
└───────────┴────────────┘
```

## 📦 Storage
- **Hot**: SSD ($$$)
- **Cold**: HDD ($)
- **Object**: S3 URL = `https://bucket.s3.region.amazonaws.com/key`

## ⚖️ Scaling
- **Vertical**: Bigger server
- **Horizontal**: More servers
- **Auto-scale**: Cloud magic

## 🔄 Consistency
- **Strong**: All see latest
- **Eventual**: "Will be consistent... eventually"
- **Brewer**: CAP = Choose 2/3

## 📡 CDN
- Edge locations
- TTL matters
- `Cache-Control: public, max-age=86400`

## 🚦 Rate Limits
- **429**: Too Many Requests
- **Token Bucket**: `max_tokens = 100`, `refill_rate = 10/s`

## 📊 Metrics
- **Four Golden Signals**:
  1. Latency
  2. Traffic
  3. Errors
  4. Saturation

## 🕵️ Monitoring
- **RED**: Rate, Errors, Duration
- **USE**: Utilization, Saturation, Errors
