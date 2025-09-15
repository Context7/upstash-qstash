On this page
### 
​
Symptom
The client gets an exception similar to:
Copy
Ask AI
```
ReplyError: ERR DB capacity quota exceeded

```

### 
​
Diagnosis
Your total database size exceeds the max data size limit of your current plan. When this limit is reached, write requests may be rejected. Read and delete requests will not be affected.
### 
​
Solution-1
You can manually delete some entries to allow further writes. Additionally you can consider setting TTL (expiration time) for your keys or enable eviction for your database.
### 
​
Solution-2
You can upgrade your database to Pro for higher limits.
Was this page helpful?
YesNo
Suggest editsRaise issue
ERR max key size exceededERR max requests limit exceeded
Assistant
Responses are generated using AI and may contain mistakes.
