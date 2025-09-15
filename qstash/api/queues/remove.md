curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"

```

DELETE
/
v2
/
queues
/
{queueName}
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"

```

Resuming or creating a queue may take up to a minute. Therefore, it is not recommended to pause or delete a queue during critical operations.
## 
​
Request
​
queueName
string
required
The name of the queue to remove.
## 
​
Response
This endpoint returns 200 if the queue is removed successfully, or it doesn’t exist.
Was this page helpful?
YesNo
Suggest editsRaise issue
Upsert a QueueList Queues
Assistant
Responses are generated using AI and may contain mistakes.
