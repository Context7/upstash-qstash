Request
Copy
Ask AI
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "flowControlKey": "<string>",
  "waitListSize": 123
}
```

GET
/
v2
/
flowControl
/
{flowControlKey}
Try it
Request
Copy
Ask AI
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "flowControlKey": "<string>",
  "waitListSize": 123
}
```

## 
​
Request
​
flowControlKey
string
The key of the flow control. See the flow control for more details.
## 
​
Response
​
flowControlKey
string
The key of of the flow control.
​
waitListSize
integer
The number of messages in the wait list that waits for `parallelism` set in the flow control.
Was this page helpful?
YesNo
Suggest editsRaise issue
Remove URL GroupList Flow-Control Keys
Assistant
Responses are generated using AI and may contain mistakes.
