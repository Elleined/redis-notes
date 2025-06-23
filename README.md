# redis-notes
Notes for redis

- It is an open source key-value store
- It stores the data in-memory meaning data is stored in RAM and will be gone on machine restart.
- It has rich set of data types.
- It can replicate data to any number of replicas.

# Advantages
1. Very fast can perform 110, 000 SETs per seconds, about 81, 000 GETs per second
2. Rich set of data types almost all of known data type is available in redis
3. Can be used in different use cases like: caching, message queues (have support for pub/sub), and any short-lived data in you application, such as session, web page hit counts (rate limiting), and etc.

## Key commands
1. DEL key: delete the specified key
2. EXISTS key: check whether the key exists or not.
3. EXPIRE key seconds: sets the expiry of key
4. KEYS pattern: find all keys matching the pattern
5. PERSIST key: removes the expiry of specified key
6. TTL key: get the remaining time of key
7. RANDOMKEY: returns a random key from re
8. RENAME key newkey: rename the specified key to specified newkey
9. TYPE key: return the data type of specified key
   
## String commands
1. SET key value: set the value of the key
2. GET key: get the value of specified key
3. INCR and INCRBY: increase the integer value of a key
4. DECR and DECRBY: decrease the integer value of a key
5. APPEND key value: appends a value to the key

## Hashes commands
1. HSET key fields values: 
2. HGETALL key: get all the fields and values at the specified key.

#### field commands
1. HDEL key fields: deletes one or more field at the specified key.
2. HEXISTS key field: checks whether the field exists at the specified key.
3. HKEYS key: get all the field at the specified key.

#### value commands
1. HGET key field: get the value of field at the specified key.
2. HVALS key: get all the values at the specified key.

## List commands
1. LLEN key: returns the length of the list
2. LRANGE key start stop: gets a range of elements from the list
3. LSET key index value: sets the value of an element in a list by its index
4. LPUSH key value: prepends one or more value to the list
5. LPOP key: removes and get the first element to the list
6. RPUSH key value: appends one or more value to the list
7. RPOP key: removes and get the last element to the list

## Set commands
1. SADD key members: add member in a set
2. SREM key members: removes member in set
3. SMEMBERS key: get all the members of set
4. SISMEMBER key member: check whether if member exists in set
5. SCARD key: get the number of members in a set

## Transaction commands
1. MULTI: start of transaction block
2. EXEC: execute all commands after the MULTI
3. DISCARD: discards all commands after the MULTI

# Redis as caching layer 
## 4 type of algorithm for caching
1. Fixed window
2. Sliding window
3. Token bucket
4. Leaky bucket

## 2 types of caching
1. CACHE HIT: you are sure that data is available in redis, no database check needed
2. CACHE MISS: you're are not sure that data is available in redis, you will first check in redis before hitting the database.

