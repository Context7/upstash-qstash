Request
Copy
Ask AI
```
curl -X GET https://qstash.upstash.io/v2/flowControl/  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "flowControls": [
    {
      "flowControlKey": "<string>",
      "waitListSize": 123
    }
  ]
}
```

GET
/
v2
/
flowControl
/
Try it
Request
Copy
Ask AI
```
curl -X GET https://qstash.upstash.io/v2/flowControl/  -H "Authorization: Bearer <token>"

```

200
Copy
Ask AI
```
{
  "flowControls": [
    {
      "flowControlKey": "<string>",
      "waitListSize": 123
    }
  ]
}
```

## 
​
Response
​
flowControls
Array
Show child attributes
​
flowControlKey
string
The key of the flow control. See the flow control for more details.
​
waitListSize
integer
The number of messages in the wait list that waits for `parallelism` set in the flow control.
Was this page helpful?
YesNo
Suggest editsRaise issue
Get Flow-Control KeysUpsert a Queue
Assistant
Responses are generated using AI and may contain mistakes.
