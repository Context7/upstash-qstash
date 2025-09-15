curl
Node
Python
Go
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "endpoints": [
      {
        "name": "endpoint1",
        "url": "https://example.com"
      },
      {
        "name": "endpoint2",
        "url": "https://somewhere-else.com"
      }
    ]
  }'

```

POST
/
v2
/
topics
/
{urlGroupName}
/
endpoints
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "endpoints": [
      {
        "name": "endpoint1",
        "url": "https://example.com"
      },
      {
        "name": "endpoint2",
        "url": "https://somewhere-else.com"
      }
    ]
  }'

```

If the URL Group does not exist, it will be created. If the endpoint does not exist, it will be created.
## 
​
Request
​
urlGroupName
string
required
The name of your URL Group (topic). If it doesn’t exist yet, it will be created.
​
endpoints
Array
required
The endpoints to add to the URL Group.
Hide child attributes
​
name
string
The name of the endpoint
​
url
string
required
The URL of the endpoint
## 
​
Response
This endpoint returns 200 if the endpoints are added successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Bulk Cancel MessagesGet a URL Group
Assistant
Responses are generated using AI and may contain mistakes.
