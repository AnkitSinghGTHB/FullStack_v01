# Redis Commands Cheat Sheet

This document outlines basic usage of Redis commands organized by data structure and feature set.

---

## General/Utility Commands
- `keys *` – List all keys in the database
- `flushall` – Remove all keys from all databases
- `ping` – Check server connection
- `echo <message>` – Print a message from the server

---

## String
- `set <key> <value>` – Set a string value
- `get <key>` – Get the value of a key
- `getrange <key> <start> <end>` – Get a substring of the value
- `mset <key1> <value1> <key2> <value2> ...` – Set multiple key-value pairs
- `mget <key1> <key2> ...` – Get multiple values
- `strlen <key>` – Get the length of the value
- `incr <key>` – Increment integer value by 1
- `incrby <key> <increment>` – Increment integer value by a specified amount
- `decr <key>` – Decrement integer value by 1
- `decrby <key> <decrement>` – Decrement integer value by a specified amount
- `incrbyfloat <key> <increment>` – Increment float value by a specified amount
- `expire <key> <seconds>` – Set a timeout on a key
- `ttl <key>` – Get the time-to-live of a key
- `setex <key> <seconds> <value>` – Set value and expiration in one command

---

## List
- `lpush <key> <value1> [value2 ...]` – Push values to the left (head)
- `rpush <key> <value1> [value2 ...]` – Push values to the right (tail)
- `lrange <key> <start> <end>` – Get a range of elements
- `llen <key>` – Get the length of the list
- `lpop <key>` – Remove and get the first element
- `rpop <key>` – Remove and get the last element
- `lset <key> <index> <value>` – Set the value at an index
- `linsert <key> BEFORE|AFTER <pivot> <value>` – Insert before or after a pivot
- `lindex <key> <index>` – Get element at index
- `lpushx <key> <value>` – Push to list only if it exists (left)
- `rpushx <key> <value>` – Push to list only if it exists (right)
- `sort <key> [options]` – Sort the list
- `blpop <key> <timeout>` – Blocking pop from the left
- `brpop <key> <timeout>` – Blocking pop from the right

---

## Set
- `sadd <key> <member1> [member2 ...]` – Add members to a set
- `smembers <key>` – Get all members
- `scard <key>` – Get the number of members
- `sismember <key> <member>` – Check if member exists
- `sdiff <key1> <key2> ...` – Difference between sets
- `sdiffstore <destination> <key1> <key2> ...` – Store difference in a new set
- `sinter <key1> <key2> ...` – Intersection of sets
- `sinterstore <destination> <key1> <key2> ...` – Store intersection
- `sunion <key1> <key2> ...` – Union of sets
- `sunionstore <destination> <key1> <key2> ...` – Store union

---

## Sorted Set (ZSet)
- `zadd <key> <score1> <member1> [score2 member2 ...]` – Add member(s) with score(s)
- `zrange <key> <start> <stop> [WITHSCORES]` – Get members by rank
- `zrevrange <key> <start> <stop> [WITHSCORES]` – Get members by reverse rank
- `zcard <key>` – Get number of members
- `zcount <key> <min> <max>` – Count members by score range
- `zrem <key> <member1> [member2 ...]` – Remove member(s)
- `zscore <key> <member>` – Get score of a member
- `zrevrangebyscore <key> <max> <min> [WITHSCORES]` – Get members by score in reverse order
- `zincrby <key> <increment> <member>` – Increment score of a member
- `zremrangebyscore <key> <min> <max>` – Remove members by score range
- `zremrangebyrank <key> <start> <stop>` – Remove members by rank range

---

## Hash
- `hset <key> <field> <value>` – Set field in hash
- `hget <key> <field>` – Get value of field
- `hkeys <key>` – Get all field names
- `hvals <key>` – Get all values
- `hgetall <key>` – Get all fields and values
- `hexists <key> <field>` – Check if field exists
- `hlen <key>` – Get number of fields
- `hmset <key> <field1> <value1> [field2 value2 ...]` – Set multiple fields
- `hmget <key> <field1> [field2 ...]` – Get multiple fields
- `hincrby <key> <field> <increment>` – Increment integer field
- `hincrbyfloat <key> <field> <increment>` – Increment float field
- `hdel <key> <field1> [field2 ...]` – Delete field(s)
- `hstrlen <key> <field>` – Get length of field value
- `hsetnx <key> <field> <value>` – Set field only if it does not exist

---

## HyperLogLog
- `pfadd <key> <element1> [element2 ...]` – Add elements to HyperLogLog
- `pfcount <key> [key2 ...]` – Count unique elements
- `pfmerge <destkey> <sourcekey1> <sourcekey2> ...` – Merge HyperLogLogs

---

## Transactions
- `multi` – Start a transaction
- `exec` – Execute all commands in the transaction
- `discard` – Discard all commands in the transaction
- `watch <key> [key2 ...]` – Watch keys for conditional execution

---

## Pub/Sub (Publish/Subscribe)
- `subscribe <channel>` – Subscribe to a channel
- `publish <channel> <message>` – Publish a message to a channel
- `psubscribe <pattern>` – Subscribe to channels by pattern
- `pubsub channels` – List active channels
- `pubsub numsub <channel>` – Number of subscribers for channels
- `pubsub numpat` – Number of pattern subscriptions

---

## Scripting
- `eval <script> <numkeys> <key1> ... <arg1> ...` – Execute Lua script
- `script load <script>` – Load a script and get its SHA1
- `evalsha <sha1> <numkeys> <key1> ... <arg1> ...` – Run script by SHA1
- `script exists <sha1>` – Check if script exists
- `script flush` – Remove all scripts

---

## Connection/Database Management
- `select <db>` – Select the database (not directly shown but referenced)
- `auth <password>` – Authenticate (not directly shown but referenced)

---

## Summary Table

| Data Type / Feature     | Commands Used                                                                                           |
|------------------------|---------------------------------------------------------------------------------------------------------|
| String                 | set, get, getrange, mset, mget, strlen, incr, incrby, decr, decrby, incrbyfloat, expire, ttl, setex     |
| List                   | lpush, rpush, lrange, llen, lpop, rpop, lset, linsert, lindex, lpushx, rpushx, sort, blpop, brpop       |
| Set                    | sadd, smembers, scard, sismember, sdiff, sdiffstore, sinter, sinterstore, sunion, sunionstore           |
| Sorted Set (ZSet)      | zadd, zrange, zrevrange, zcard, zcount, zrem, zscore, zrevrangebyscore, zincrby, zremrangebyscore, zremrangebyrank |
| Hash                   | hset, hget, hkeys, hvals, hgetall, hexists, hlen, hmset, hmget, hincrby, hincrbyfloat, hdel, hstrlen, hsetnx |
| HyperLogLog            | pfadd, pfcount, pfmerge                                                                                |
| Transactions           | multi, exec, discard, watch                                                                            |
| Pub/Sub                | subscribe, publish, psubscribe, pubsub channels, pubsub numsub, pubsub numpat                          |
| Scripting              | eval, script load, evalsha, script exists, script flush                                                 |
| General/Utility        | keys, flushall, ping, echo                                                                             |

---
