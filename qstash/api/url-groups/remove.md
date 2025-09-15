curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/topics/my-url-group \
  -H "Authorization: Bearer <token>"

```

DELETE
/
v2
/
topics
/
{urlGroupName}
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/topics/my-url-group \
  -H "Authorization: Bearer <token>"

```

The URL Group and all its endpoints are removed. In flight messages in the URL Group are not removed but you will not be able to send messages to the topic anymore.
## 
​
Request
​
urlGroupName
string
required
The name of the URL Group to remove.
## 
​
Response
This endpoint returns 200 if the URL Group is removed successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Remove EndpointsGet Flow-Control Keys
Assistant
Responses are generated using AI and may contain mistakes.
