On this page
### 
​
Symptom
The client gets an exception similar to:
Copy
Ask AI
```
ReplyError: ERR max request size exceeded

```

### 
​
Diagnosis
Your command exceeds the max request size which is `1Mb` for “Free” and “Pay as you go” databases.
### 
​
Solution-1
You can split your data into smaller chunks and send them in separate commands.
### 
​
Solution-2
You can upgrade your database to Pro as it has higher limits. Also you can submit quota increase request in the console or you can contact support@upstash.com about the options with higher max request size limit.
max-request-size-limit is about the size of a single request. Your data structure (like list, set) can exceed the max request size limit without any problem. If you try to load all elements in the list with a single request then it can throw the max-request-size-limit exception.
Was this page helpful?
YesNo
Suggest editsRaise issue
ERR max concurrent connections exceededERR max single record size exceeded
Assistant
Responses are generated using AI and may contain mistakes.
