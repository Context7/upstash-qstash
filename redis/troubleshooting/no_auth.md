On this page
### 
​
Symptom
The client can not connect to the database throwing an exception similar to:
Copy
Ask AI
```
[ioredis] Unhandled error event:
ReplyError: NOAUTH Authentication required

```

### 
​
Diagnosis
The server does not let you connect because the password is missing in your connection parameters.
### 
​
Solution
Check your connection parameters and ensure they contain the password. If you are using ioredis (Redis client) with a Redis URL, check the URL format. ioredis requires a colon before the password. The format for IORedis - TLS enabled
Copy
Ask AI
```
rediss://:YOUR_PASSWORD@YOUR_ENDPOINT:YOUR_PORT

```

The format for IORedis - TLS disabled
Copy
Ask AI
```
redis://:YOUR_PASSWORD@YOUR_ENDPOINT:YOUR_PORT

```

You can copy the correct client configuration from Upstash console clicking on **Redis Connect** button.
Was this page helpful?
YesNo
Suggest editsRaise issue
Unexpected Increase in Command CountWRONGPASS invalid or missing auth token
Assistant
Responses are generated using AI and may contain mistakes.
