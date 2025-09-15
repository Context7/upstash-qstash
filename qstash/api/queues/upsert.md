curl
Node
Python
Go
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue" , 
    "parallelism" : 5,
  }'

```

POST
/
v2
/
queues
/
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue" , 
    "parallelism" : 5,
  }'

```

## 
​
Request
​
queueName
string
required
The name of the queue.
​
parallelism
int
required
The number of parallel consumers consuming from the queue.
For the parallelism limit, we introduced an easier and less limited API with publish. Please check the Flow Control page for the detailed information.Setting parallelism with queues will be deprecated at some point.
## 
​
Response
This endpoint returns
  * 200 if the queue is added successfully.
  * 412 if it fails because of the the allowed number of queues limit


Was this page helpful?
YesNo
Suggest editsRaise issue
List Flow-Control KeysRemove a Queue
Assistant
Responses are generated using AI and may contain mistakes.
