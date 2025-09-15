curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/pause \
  -H "Authorization: Bearer <token>"

```

POST
/
v2
/
queues
/
{queueName}
/
pause
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/pause \
  -H "Authorization: Bearer <token>"

```

Pausing a queue stops the delivery of enqueued messages. The queue will still accept new messages, but they will wait until the queue becomes active for delivery. If the queue is already paused, this action has no effect.
Resuming or creating a queue may take up to a minute. Therefore, it is not recommended to pause or delete a queue during critical operations.
## 
​
Request
​
queueName
string
required
The name of the queue to pause.
## 
​
Response
This endpoint simply returns 200 OK if the queue is paused successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Get a QueueResume Queue
Assistant
Responses are generated using AI and may contain mistakes.
