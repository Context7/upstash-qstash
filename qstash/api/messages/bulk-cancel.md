curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/messages/ \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <token>" \
  -d '{"messageIds": ["msg_id_1", "msg_id_2", "msg_id_3"]}'

```

202 Accepted
Copy
Ask AI
```
{
  "cancelled": 10
}

```

DELETE
/
v2
/
messages
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/messages/ \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <token>" \
  -d '{"messageIds": ["msg_id_1", "msg_id_2", "msg_id_3"]}'

```

202 Accepted
Copy
Ask AI
```
{
  "cancelled": 10
}

```

Bulk cancel allows you to cancel multiple messages at once.
Cancelling a message will remove it from QStash and stop it from being delivered in the future. If a message is in flight to your API, it might be too late to cancel.
If you provide a set of message IDs in the body of the request, only those messages will be cancelled.If you include filter parameters in the request body, only the messages that match the filters will be canceled.If the `messageIds` array is empty, QStash will cancel all of your messages.If no body is sent, QStash will also cancel all of your messages.
This operation scans all your messages and attempts to cancel them. If an individual message cannot be cancelled, it will not continue and will return an error message. Therefore, some messages may not be cancelled at the end. In such cases, you can run the bulk cancel operation multiple times.
You can filter the messages to cancel by including filter parameters in the request body.
## 
​
Request
​
messageIds
Array
The list of message IDs to cancel.
​
queueName
string
Filter messages to cancel by queue name.
​
url
string
Filter messages to cancel by destination URL.
​
topicName
string
Filter messages to cancel by URL Group (topic) name.
​
fromDate
number
Filter messages to cancel by starting date, in milliseconds (Unix timestamp). This is inclusive.
​
toDate
number
Filter messages to cancel by ending date, specified in milliseconds (Unix timestamp). This is inclusive.
​
scheduleId
string
Filter messages to cancel by schedule ID.
​
callerIP
string
Filter messages to cancel by IP address of publisher.
## 
​
Response
A cancelled object with the number of cancelled messages.
Copy
Ask AI
```
{
  "cancelled": number
}

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Cancel MessageUpsert URL Group and Endpoint
Assistant
Responses are generated using AI and may contain mistakes.
