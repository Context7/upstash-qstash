curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "messageId": "msg_123",
  "topicName": "myTopic",
  "url":"https://example.com",
  "method": "POST",
  "header": {
    "My-Header": ["my-value"]
  },
  "body": "{\"foo\":\"bar\"}",
  "createdAt": 1620000000000
}

```

GET
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
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "messageId": "msg_123",
  "topicName": "myTopic",
  "url":"https://example.com",
  "method": "POST",
  "header": {
    "My-Header": ["my-value"]
  },
  "body": "{\"foo\":\"bar\"}",
  "createdAt": 1620000000000
}

```

## 
​
Request
​
messageId
string
required
The id of the message to retrieve.
Messages are removed from the database shortly after they’re delivered, so you will not be able to retrieve a message after. This endpoint is intended to be used for accessing messages that are in the process of being delivered/retried.
## 
​
Response
​
messageId
string
required
A unique identifier for this message.
​
topicName
string
The URL group (topic) name if this message was sent to a URL Group.
​
endpointName
string
The endpoint name of the message if the endpoint is given a name within the URL group.
​
url
string
required
The URL to which the message should be delivered.
​
method
string
The HTTP method to use for the message.
​
header
Record<string, string[]>
The HTTP headers sent to your API.
​
body
string
The body of the message if it is composed of utf8 chars only, empty otherwise.
​
bodyBase64
string
The base64 encoded body if the body contains a non-utf8 char only, empty otherwise.
​
maxRetries
int
The number of retries that should be attempted in case of delivery failure.
​
notBefore
int
The unix timestamp in milliseconds before which the message should not be delivered.
​
createdAt
int
required
The unix timestamp in milliseconds when the message was created.
​
callback
string
The url where we send a callback each time the message is attempted to be delivered.
​
failureCallback
string
The url where we send a callback to after the message is failed
​
scheduleId
string
The scheduleId of the message if the message is triggered by a schedule
​
callerIP
string
required
IP address of the publisher of this message.
Was this page helpful?
YesNo
Suggest editsRaise issue
Batch MessagesCancel Message
Assistant
Responses are generated using AI and may contain mistakes.
