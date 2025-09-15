curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/schedules \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
[
  {
    "scheduleId": "scd_1234",
    "createdAt": 1623345678001,
    "cron": "0 0 1 * *",
    "destination": "https://example.com",
    "method": "POST",
    "header": {
      "Content-Type": ["application/json"]
    },
    "body": "{\"message\":\"hello\"}",
    "retries": 3
  }
]

```

GET
/
v2
/
schedules
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/schedules \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
[
  {
    "scheduleId": "scd_1234",
    "createdAt": 1623345678001,
    "cron": "0 0 1 * *",
    "destination": "https://example.com",
    "method": "POST",
    "header": {
      "Content-Type": ["application/json"]
    },
    "body": "{\"message\":\"hello\"}",
    "retries": 3
  }
]

```

## 
​
Response
​
array
Object[]
​
createdAt
int
required
The creation time of the object. UnixMilli
​
id
string
required
The id of the schedule.
​
cron
string
required
The cron expression used to schedule the message.
​
destination
string
required
Url or URL Group (topic) name
​
method
string
required
The HTTP method to use for the message.
​
header
Record<string, string[]>
required
The headers of the message.
​
body
string
required
The body of the message.
​
retries
int
The number of retries that should be attempted in case of delivery failure.
​
delay
int
The delay in seconds before the message is delivered.
​
callback
string
The url where we send a callback to after the message is delivered
Was this page helpful?
YesNo
Suggest editsRaise issue
Get ScheduleRemove Schedule
Assistant
Responses are generated using AI and may contain mistakes.
