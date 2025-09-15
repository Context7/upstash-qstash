Request
Copy
Ask AI
```
curl -X DELETE https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"

```

DELETE
/
v2
/
dlq
/
{dlqId}
Try it
Request
Copy
Ask AI
```
curl -X DELETE https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"

```

Delete a message from the DLQ.
## 
​
Request
​
dlqId
string
The dlq id of the message you want to remove. You will see this id when listing all messages in the dlq with the /v2/dlq endpoint.
## 
​
Response
The endpoint doesn’t return anything, a status code of 200 means the message is removed from the DLQ. If the message is not found in the DLQ, (either is has been removed by you, or automatically), the endpoint returns a 404 status code.
Was this page helpful?
YesNo
Suggest editsRaise issue
Get a message from the DLQDelete multiple messages from the DLQ
Assistant
Responses are generated using AI and may contain mistakes.
