curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/events \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "cursor": "1686652644442-12",
  "events":[
    {
      "time": "1686652644442",
      "messageId": "msg_123",
      "state": "delivered",
      "url": "https://example.com",
      "header": { "Content-Type": [ "application/x-www-form-urlencoded" ] },
      "body": "bWVyaGFiYSBiZW5pbSBhZGltIHNhbmNhcg=="
    }
  ] 
}

```

GET
/
v2
/
events
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/events \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "cursor": "1686652644442-12",
  "events":[
    {
      "time": "1686652644442",
      "messageId": "msg_123",
      "state": "delivered",
      "url": "https://example.com",
      "header": { "Content-Type": [ "application/x-www-form-urlencoded" ] },
      "body": "bWVyaGFiYSBiZW5pbSBhZGltIHNhbmNhcg=="
    }
  ] 
}

```

QStash events are being renamed to Logs to better reflect their purpose and to not get confused with Workflow Events.
## 
​
Request
​
cursor
string
By providing a cursor you can paginate through all of the events.
​
messageId
string
Filter events by message id.
​
state
string
Filter events by stateValue| Description  
---|---  
`CREATED`| The message has been accepted and stored in QStash  
`ACTIVE`| The task is currently being processed by a worker.  
`RETRY`| The task has been scheduled to retry.  
`ERROR`| The execution threw an error and the task is waiting to be retried or failed.  
`IN_PROGRESS`| The task is in one of `ACTIVE`, `RETRY` or `ERROR` state.  
`DELIVERED`| The message was successfully delivered.  
`FAILED`| The task has errored too many times or encountered an error that it cannot recover from.  
`CANCEL_REQUESTED`| The cancel request from the user is recorded.  
`CANCELLED`| The cancel request from the user is honored.  
​
url
string
Filter events by url.
​
topicName
string
Filter events by URL Group (topic) name.
​
scheduleId
string
Filter events by schedule id.
​
queueName
string
Filter events by queue name.
​
fromDate
number
Filter events by starting date, in milliseconds (Unix timestamp). This is inclusive.
​
toDate
number
Filter events by ending date, in milliseconds (Unix timestamp). This is inclusive.
​
count
number
The number of events to return. Default and max is 1000.
​
order
string
The sorting order of events by timestamp. Valid values are “earliestFirst” and “latestFirst”. The default is “latestFirst”.
## 
​
Response
​
cursor
string
A cursor which you can use in subsequent requests to paginate through all events. If no cursor is returned, you have reached the end of the events.
​
events
Array
Hide child attributes
​
time
int
required
Timestamp of this log entry, in milliseconds
​
messageId
string
required
The associated message id
​
header
Record<string, string[]>
required
The headers of the message.
​
body
string
required
Base64 encoded body of the message.
​
state
string
required
The current state of the message at this point in time.Value| Description  
---|---  
`CREATED`| The message has been accepted and stored in QStash  
`ACTIVE`| The task is currently being processed by a worker.  
`RETRY`| The task has been scheduled to retry.  
`ERROR`| The execution threw an error and the task is waiting to be retried or failed.  
`DELIVERED`| The message was successfully delivered.  
`FAILED`| The task has errored too many times or encountered an error that it cannot recover from.  
`CANCEL_REQUESTED`| The cancel request from the user is recorded.  
`CANCELLED`| The cancel request from the user is honored.  
​
error
string
An explanation what went wrong
​
nextDeliveryTime
int
The next scheduled time of the message. (Unix timestamp in milliseconds)
​
url
string
The destination url
​
topicName
string
The name of the URL Group (topic) if this message was sent through a topic
​
endpointName
int
The name of the endpoint if this message was sent through a URL Group
​
scheduleId
string
The scheduleId of the message if the message is triggered by a schedule
​
queueName
string
The name of the queue if this message is enqueued on a queue
​
header
string
The headers that are forwarded to the users endpoint
​
body
string
Base64 encoded body of the message
​
responseStatus
int
The status code of the response. Only set if the state is `ERROR`
​
responseBody
string
The base64 encoded body of the response. Only set if the state is `ERROR`
​
responseHeaders
Record<string, string[]>
The headers of the response. Only set if the state is `ERROR`
​
timeout
int
The timeout(in milliseconds) of the outgoing http requests, after which Qstash cancels the request
​
method
string
Method is the HTTP method of the message for outgoing request
​
callback
string
Callback is the URL address where QStash sends the response of a publish
​
callbackHeaders
Record<string, string[]>
The headers that are passed to the callback url
​
failureCallback
string
Failure Callback is the URL address where QStash sends the response of a publish
​
failureCallbackHeaders
Record<string, string[]>
The headers that are passed to the failure callback url
​
maxRetries
int
The number of retries that should be attempted in case of delivery failure
​
retryDelayExpression
string
The mathematical expression used to calculate delay between retry attempts. If not set, the default backoff is used.
Was this page helpful?
YesNo
Suggest editsRaise issue
List LogsList messages in the DLQ
Assistant
Responses are generated using AI and may contain mistakes.
