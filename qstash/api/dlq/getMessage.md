Request
Copy
Ask AI
```
curl -X GET https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "messageId": "<string>",
  "topicName": "<string>",
  "endpointName": "<string>",
  "url": "<string>",
  "method": "<string>",
  "header": {},
  "body": "<string>",
  "bodyBase64": "<string>",
  "maxRetries": 123,
  "notBefore": 123,
  "createdAt": 123,
  "callback": "<string>",
  "failureCallback": "<string>",
  "scheduleId": "<string>",
  "callerIP": "<string>",
  "dlqId": "<string>",
  "queueName": "<string>",
  "responseStatus": 123,
  "responseHeader": [
    {}
  ],
  "responseBody": "<string>",
  "responseBodyBase64": "<string>"
}
```

GET
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
curl -X GET https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "messageId": "<string>",
  "topicName": "<string>",
  "endpointName": "<string>",
  "url": "<string>",
  "method": "<string>",
  "header": {},
  "body": "<string>",
  "bodyBase64": "<string>",
  "maxRetries": 123,
  "notBefore": 123,
  "createdAt": 123,
  "callback": "<string>",
  "failureCallback": "<string>",
  "scheduleId": "<string>",
  "callerIP": "<string>",
  "dlqId": "<string>",
  "queueName": "<string>",
  "responseStatus": 123,
  "responseHeader": [
    {}
  ],
  "responseBody": "<string>",
  "responseBodyBase64": "<string>"
}
```

Get a message from DLQ.
## 
​
Request
​
dlqId
string
The dlq id of the message you want to retrieve. You will see this id when listing all messages in the dlq with the /v2/dlq endpoint, as well as in the content of the failure callback
## 
​
Response
If the message is not found in the DLQ, (either is has been removed by you, or automatically), the endpoint returns a 404 status code.
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
Was this page helpful?
YesNo
Suggest editsRaise issue
List messages in the DLQDelete a message from the DLQ
Assistant
Responses are generated using AI and may contain mistakes.
