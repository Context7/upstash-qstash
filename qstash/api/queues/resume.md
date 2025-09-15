curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/resume \
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
resume
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/resume \
  -H "Authorization: Bearer <token>"

```

Resuming a queue starts the delivery of enqueued messages from the earliest undelivered message. If the queue is already active, this action has no effect.
## 
​
Request
​
queueName
string
required
The name of the queue to resume.
## 
​
Response
This endpoint simply returns 200 OK if the queue is resumed successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Pause QueueCreate Schedule
Assistant
Responses are generated using AI and may contain mistakes.
