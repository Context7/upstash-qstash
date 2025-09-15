curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
     "dlqIds": ["11111-0", "22222-0", "33333-0"]
    }'

```

200 OK
Copy
Ask AI
```
{
  "deleted": 3
}

```

DELETE
/
v2
/
dlq
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
     "dlqIds": ["11111-0", "22222-0", "33333-0"]
    }'

```

200 OK
Copy
Ask AI
```
{
  "deleted": 3
}

```

Delete multiple messages from the DLQ.
You can get the `dlqId` from the list DLQs endpoint.
## 
​
Request
​
dlqIds
string[]
required
The list of DLQ message IDs to remove.
## 
​
Response
A deleted object with the number of deleted messages.
Copy
Ask AI
```
{
  "deleted": number
}

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Delete a message from the DLQCreate Chat Completion
Assistant
Responses are generated using AI and may contain mistakes.
