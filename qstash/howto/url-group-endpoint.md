On this page
QStash allows you to group multiple APIs together into a single namespace, called a `URL Group` (Previously, it was called `Topics`). Read more about URL Groups here. There are two ways to create endpoints and URL Groups: The UI and the REST API.
## 
​
UI
Go to console.upstash.com/qstash and click on the `URL Groups` tab. Afterwards you can create a new URL Group by giving it a name. Keep in mind that URL Group names are restricted to alphanumeric, underscore, hyphen and dot characters. After creating the URL Group, you can add endpoints to it:
## 
​
API
You can create a URL Group and endpoint using the console or REST API.
cURL
Typescript
Python
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

Was this page helpful?
YesNo
Suggest editsRaise issue
Publish MessagesHandling Failures
Assistant
Responses are generated using AI and may contain mistakes.
