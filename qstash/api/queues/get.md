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

200 OK
Copy
Ask AI
```
{
 
  "createdAt": 1623345678001,
  "updatedAt": 1623345678001,
  "name": "my-queue",
  "parallelism" : 5, 
  "lag" : 100
}

```

GET
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

200 OK
Copy
Ask AI
```
{
 
  "createdAt": 1623345678001,
  "updatedAt": 1623345678001,
  "name": "my-queue",
  "parallelism" : 5, 
  "lag" : 100
}

```

## 
​
Request
​
queueName
string
required
The name of the queue to retrieve.
## 
​
Response
​
createdAt
int
required
The creation time of the queue. UnixMilli
​
updatedAt
int
required
The update time of the queue. UnixMilli
​
name
string
required
The name of the queue.
​
parallelism
int
required
The number of parallel consumers consuming from the queue.
​
lag
int
required
The number of unprocessed messages that exist in the queue.
Was this page helpful?
YesNo
Suggest editsRaise issue
List QueuesPause Queue
Assistant
Responses are generated using AI and may contain mistakes.
