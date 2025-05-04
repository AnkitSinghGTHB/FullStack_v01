# Redis Commands Cheat Sheet

This document outlines basic usage of Redis commands organized by data structure and feature set.

---

## 📦 Redis Strings

Basic key-value operations:

```bash
SET name "Alice"
GET name
DEL name
INCR counter
APPEND name " Smith"
STRLEN name
```
## 📜 Redis Lists
Redis lists are ordered collections of strings:

```bash
LPUSH mylist "a"
RPUSH mylist "b"
LPOP mylist
RPOP mylist
LRANGE mylist 0 -1
```

## 🧩 Redis Sets
Unordered collections of unique strings:

```bash
SADD myset "a" "b"
SMEMBERS myset
SISMEMBER myset "a"
SREM myset "b"
SUNION set1 set2
```

## 🔢 Redis Sorted Sets
Sorted sets with scores for ranking:

```bash
ZADD scores 100 "Alice" 200 "Bob"
ZRANGE scores 0 -1 WITHSCORES
ZREM scores "Alice"
ZREVRANGE scores 0 1
ZSCORE scores "Bob"
```

## 📈 Redis HyperLogLog
Probabilistic data structure for approximating cardinality:

```bash
PFADD hll "a" "b" "c"
PFCOUNT hll
PFMERGE hll_merged hll1 hll2
```

## 🧱 Redis Hashes
Store objects as fields and values:

```bash
HSET user:1000 name "Alice" age "30"
HGET user:1000 name
HGETALL user:1000
HDEL user:1000 age
```

## 🔒 Redis Transactions
Group multiple commands into a transaction:

```bash
MULTI
SET key1 "value1"
SET key2 "value2"
EXEC
```

To cancel a transaction:

```bash
DISCARD
```

## 📢 Redis Pub/Sub
Message broadcasting system:

```bash

Subscriber
SUBSCRIBE news

Publisher
PUBLISH news "Hello World"
```

## 📜 Redis Scripts
Run Lua scripts for atomic operations:

```bash
EVAL "return redis.call('GET', KEYS[1])" 1 mykey
EVAL "redis.call('SET', KEYS[1], ARGV[1])" 1 mykey "value"
```

## 🔐 Redis Connection & Security
Manage access and authentication:

```bash
AUTH yourpassword
CONFIG SET requirepass "yourpassword"
CONFIG GET requirepass
```

Secure connection (if TLS is enabled):

```bash
redis-cli -h <host> -p <port> --tls
```

## 🗺️ Redis Geospatial
Store and query geolocation data:

```bash
GEOADD cities 13.361389 38.115556 "Palermo"
GEODIST cities "Palermo" "Catania"
GEORADIUS cities 15 37 200 km
```

## 🧪 Redis Benchmark
Test Redis performance:

```bash
redis-benchmark -n 10000 -q
redis-benchmark -t set,get -n 100000
```

