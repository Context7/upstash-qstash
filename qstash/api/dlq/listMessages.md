Request
with cursor
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{ 
  "messages": [
    {
      "messageId": "msg_123",
      "topicId": "tpc_123",
      "url":"https://example.com",
      "method": "POST",
      "header": {
        "My-Header": ["my-value"]
      },
      "body": "{\"foo\":\"bar\"}",
      "createdAt": 1620000000000,
      "state": "failed"
    }
  ]
}

```

GET
/
v2
/
dlq
Try it
Request
with cursor
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{ 
  "messages": [
    {
      "messageId": "msg_123",
      "topicId": "tpc_123",
      "url":"https://example.com",
      "method": "POST",
      "header": {
        "My-Header": ["my-value"]
      },
      "body": "{\"foo\":\"bar\"}",
      "createdAt": 1620000000000,
      "state": "failed"
    }
  ]
}

```

List all messages currently inside the DLQ
## 
​
Request
​
cursor
string
By providing a cursor you can paginate through all of the messages in the DLQ
​
messageId
string
Filter DLQ messages by message id.
​
url
string
Filter DLQ messages by url.
​
topicName
string
Filter DLQ messages by url group.
​
scheduleId
string
Filter DLQ messages by schedule id.
​
queueName
string
Filter DLQ messages by queue name.
​
api
string
Filter DLQ messages by API name.
​
fromDate
number
Filter DLQ messages by starting date, in milliseconds (Unix timestamp). This is inclusive.
​
toDate
number
Filter DLQ messages by ending date, in milliseconds (Unix timestamp). This is inclusive.
​
responseStatus
number
Filter DLQ messages by HTTP response status code.
​
callerIp
string
Filter DLQ messages by IP address of the publisher.
​
count
number
The number of messages to return. Default and maximum is 100.
​
order
string
The sorting order of DLQ messages by timestamp. Valid values are “earliestFirst” and “latestFirst”. The default is “earliestFirst”.
​
label
string
Filter DLQ messages by the label of the message assigned by the user.
## 
​
Response
​
cursor
string
A cursor which you can use in subsequent requests to paginate through all messages. If no cursor is returned, you have reached the end of the messages.
​
messages
Array
Hide message
​
messageId
string
required
A unique identifier for this message.
​
topicName
string
The URL Group (topic) name if this message was sent to a URL Group.
​
endpointName
string
The endpointName of the message if the endpoint is given a name within the URL Group.
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
​
dlqId
string
required
The unique id within the DLQ. Use this to remove the message from the DLQ DELETE /v2/dlq/{dlqId}
​
queueName
string
The name of the queue if this message is enqueued on a queue
​
responseStatus
int
The http status code of the last failed deliver attempt.
​
responseHeader
Record<string, string[]
The response header of the last failed deliver attempt.
​
responseBody
string
The response body of the last failed deliver attempt if it is composed of utf8 chars only, empty otherwise.
​
responseBodyBase64
string
The base64 encoded response body of the last failed deliver attempt if the response body contains a non-utf8 char only, empty otherwise.
​
label
string
The label of the message assigned by the user.
Was this page helpful?
YesNo
Suggest editsRaise issue
List EventsGet a message from the DLQ
Assistant
Responses are generated using AI and may contain mistakes.
