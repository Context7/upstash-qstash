curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"

```

202 Accepted
Copy
Ask AI
```
OK

```

DELETE
/
v2
/
messages
/
{messageId}
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"

```

202 Accepted
Copy
Ask AI
```
OK

```

Cancelling a message will remove it from QStash and stop it from being delivered in the future. If a message is in flight to your API, it might be too late to cancel.
## 
​
Request
​
messageId
string
required
The id of the message to cancel.
## 
​
Response
This endpoint only returns `202 OK`
Was this page helpful?
YesNo
Suggest editsRaise issue
Get MessageBulk Cancel Messages
Assistant
Responses are generated using AI and may contain mistakes.
