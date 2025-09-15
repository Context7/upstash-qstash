curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
[
  {
    "createdAt": 1623345678001,
    "updatedAt": 1623345678001,
    "name": "my-queue",
    "parallelism" : 5, 
    "lag" : 100
  },
  // ...
]

```

GET
/
v2
/
queues
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
[
  {
    "createdAt": 1623345678001,
    "updatedAt": 1623345678001,
    "name": "my-queue",
    "parallelism" : 5, 
    "lag" : 100
  },
  // ...
]

```

## 
​
Request
No parameters
## 
​
Response
Array
required
Hide child attributes
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
Remove a QueueGet a Queue
Assistant
Responses are generated using AI and may contain mistakes.
