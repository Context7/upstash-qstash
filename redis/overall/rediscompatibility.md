Upstash supports Redis client protocol up to version `6.2`. We are also gradually adding changes introduced in versions `7.0` and `7.2`, such as `EXPIRETIME`, `LMPOP`, `ZINTERCARD` and `EVAL_RO`. The following table shows the most recent list of the supported Redis commands: Feature| Supported?| Supported Commands  
---|---|---  
String| ✅| APPEND - DECR - DECRBY - GET - GETDEL - GETEX - GETRANGE - GETSET - INCR - INCRBY - INCRBYFLOAT - MGET - MSET - MSETNX - PSETEX - SET - SETEX - SETNX - SETRANGE - STRLEN  
Bitmap| ✅| BITCOUNT - BITFIELD - BITFIELD_RO - BITOP - BITPOS - GETBIT - SETBIT  
Hash| ✅| HDEL - HEXISTS - HGET - HGETALL - HINCRBY - HINCRBYFLOAT - HKEYS - HLEN - HMGET - HMSET - HSCAN - HSET - HSETNX - HSTRLEN - HRANDFIELD - HVALS  
List| ✅| BLMOVE - BLMPOP - BLPOP - BRPOP - BRPOPLPUSH - LINDEX - LINSERT - LLEN - LMOVE - LMPOP - LPOP - LPOS - LPUSH - LPUSHX - LRANGE - LREM - LSET - LTRIM - RPOP - RPOPLPUSH - RPUSH - RPUSHX  
Set| ✅| SADD - SCARD - SDIFF - SDIFFSTORE - SINTER - SINTERCARD - SINTERSTORE - SISMEMBER - SMEMBERS - SMISMEMBER - SMOVE - SPOP - SRANDMEMBER - SREM - SSCAN - SUNION - SUNIONSTORE  
SortedSet| ✅| BZMPOP - BZPOPMAX - BZPOPMIN - ZADD - ZCARD - ZCOUNT - ZDIFF - ZDIFFSTORE - ZINCRBY - ZINTER - ZINTERCARD - ZINTERSTORE - ZLEXCOUNT - ZMPOP - ZMSCORE - ZPOPMAX - ZPOPMIN - ZRANDMEMBER - ZRANGE - ZRANGESTORE - ZRANGEBYLEX - ZRANGEBYSCORE - ZRANK - ZREM - ZREMRANGEBYLEX - ZREMRANGEBYRANK - ZREMRANGEBYSCORE - ZREVRANGE - ZREVRANGEBYLEX - ZREVRANGEBYSCORE - ZREVRANK - ZSCAN - ZSCORE - ZUNION - ZUNIONSTORE  
Geo| ✅| GEOADD - GEODIST - GEOHASH - GEOPOS - GEORADIUS - GEORADIUS_RO - GEORADIUSBYMEMBER - GEORADIUSBYMEMBER_RO - GEOSEARCH - GEOSEARCHSTORE  
HyperLogLog| ✅| PFADD - PFCOUNT - PFMERGE  
Scripting| ✅| EVAL - EVALSHA - EVAL_RO - EVALSHA_RO - SCRIPT EXISTS - SCRIPT LOAD - SCRIPT FLUSH  
Pub/Sub| ✅| SUBSCRIBE - PSUBSCRIBE - UNSUBSCRIBE - PUNSUBSCRIBE - PUBLISH - PUBSUB  
Transactions| ✅| DISCARD - EXEC - MULTI - UNWATCH - WATCH  
Generic| ✅| COPY - DEL - DUMP - EXISTS - EXPIRE - EXPIREAT - EXPIRETIME - KEYS - PERSIST - PEXPIRE - PEXPIREAT - PEXPIRETIME - PTTL - RANDOMKEY - RENAME - RENAMENX - RESTORE - SCAN - TOUCH - TTL - TYPE - UNLINK  
Connection| ✅| AUTH - HELLO - ECHO - PING - QUIT - RESET - SELECT  
Server| ✅| ACL(*) - DBSIZE - FLUSHALL - FLUSHDB - MONITOR - TIME  
JSON| ✅| JSON.ARRAPPEND - JSON.ARRINSERT - JSON.ARRINDEX - JSON.ARRLEN - JSON.ARRPOP - JSON.ARRTRIM - JSON.CLEAR - JSON.DEL - JSON.FORGET - JSON.GET - JSON.MERGE - JSON.MGET - JSON.MSET - JSON.NUMINCRBY - JSON.NUMMULTBY - JSON.OBJKEYS - JSON.OBJLEN - JSON.RESP - JSON.SET - JSON.STRAPPEND - JSON.STRLEN - JSON.TOGGLE - JSON.TYPE  
Streams| ✅| XACK - XADD - XAUTOCLAIM - XCLAIM - XDEL - XGROUP - XINFO GROUPS - XINFO CONSUMERS - XLEN - XPENDING - XRANGE - XREAD - XREADGROUP - XREVRANGE - XTRIM  
Cluster| ❌|   
We run command integration tests from following Redis clients after each code change and also periodically:
  * **Node-Redis** Command Tests
  * **Jedis** Command Tests
  * **Lettuce** Command Tests
  * **Go-Redis** Command Tests
  * **Redis-py** Command Tests

Most of the unsupported items are in our roadmap. If you need a feature that we do not support, please drop a note to support@upstash.com. So we can inform you when we are planning to support it.
Was this page helpful?
YesNo
Suggest editsRaise issue
Pricing & LimitsChangelog
Assistant
Responses are generated using AI and may contain mistakes.
