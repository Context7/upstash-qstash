On this page
### 
​
Symptom
New clients can not connect to the database throwing an exception similar to:
Copy
Ask AI
```
"message" : "[ioredis] Unhandled error event:
ReplyError: ERR max concurrent connections exceeded\r
at Object.onceWrapper (events.js:286:20)\r
at Socket.emit (events.js:203:15)\r    at Socket.EventEmitter.emit (domain.js:448:20)\r
at TCPConnectWrap.afterConnect [as oncomplete] (net.js:1093:10)\n"

```

### 
​
Diagnosis
You have reached the concurrent connection limit.
### 
​
Solution-1
You need to manage connections more efficiently. If you are using serverless functions, you can create the Redis client inside the function and close the connection when you are done with the database as below.
This solution may have a latency overhead (about 4 ms). See the blog post for more.
Copy
Ask AI
```
exports.handler = async (event) => {
  const client = new Redis(process.env.REDIS_URL);
  /*
    do stuff with redis
     */
  await client.quit();
  /*
  do other stuff
   */
  return {
    response: "response",
  };
};

```

### 
​
Solution-2
You can use @upstash/redis client which is REST based so it does not have any connection related problems.
### 
​
Solution-3
You can upgrade your database to Pro for higher limits.
See the blog post about the database connections in serverless functions.
Was this page helpful?
YesNo
Suggest editsRaise issue
Error read ECONNRESETERR max request size exceeded
Assistant
Responses are generated using AI and may contain mistakes.
