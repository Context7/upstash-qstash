On this page
### 
​
Symptom
The client can not connect to the database throwing an exception similar to:
Copy
Ask AI
```
[ioredis] Unhandled error event: Error: read ECONNRESET
    at TCP.onStreamRead (node:internal/stream_base_commons:211:20)

```

### 
​
Diagnosis
The server is TLS enabled but your connection (client) is not.
### 
​
Solution
Check your connection parameters and ensure you enable TLS. If you are using a Redis URL then it should start with `rediss://`. You can copy the correct client configuration from Upstash console clicking on **Redis Connect** button.
Was this page helpful?
YesNo
Suggest editsRaise issue
WRONGPASS invalid or missing auth tokenERR max concurrent connections exceeded
Assistant
Responses are generated using AI and may contain mistakes.
