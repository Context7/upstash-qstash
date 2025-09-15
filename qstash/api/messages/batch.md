Batch Messages
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://qstash.upstash.io/v2/batch \
  --header 'Authorization: Bearer <token>'
```

POST
/
v2
/
batch
Try it
Batch Messages
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://qstash.upstash.io/v2/batch \
  --header 'Authorization: Bearer <token>'
```

You can learn more about batching in the batching section.
API playground is not available for this endpoint. You can use the cURL example below.
You can publish to destination, URL Group or queue in the same batch request.
## 
​
Request
The endpoint is `POST https://qstash.upstash.io/v2/batch` and the body is an array of messages. Each message has the following fields:
Copy
Ask AI
```
destination: string
headers: headers object
body: string

```

The headers are identical to the headers in the create endpoint.
cURL
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/batch   -H "Authorization: Bearer XXX" \
    -H "Content-Type: application/json" \
    -d '
    [
      {
          "destination": "myUrlGroup",
          "headers":{
            "Upstash-Delay":"5s",
            "Upstash-Forward-Hello":"123456"
          },
          "body": "Hello World"
      },
      {
          "queue": "test",
          "destination": "https://example.com/destination",
          "headers":{
            "Upstash-Forward-Hello":"789"
          }
      },
      {
          "destination": "https://example.com/destination1",
          "headers":{
            "Upstash-Delay":"7s",
            "Upstash-Forward-Hello":"789"
          }
      },
      {
          "destination": "https://example.com/destination2",
          "headers":{
            "Upstash-Delay":"9s",
            "Upstash-Forward-Hello":"again"
          }
      }
    ]'

```

## 
​
Response
Copy
Ask AI
```
[
  [
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint1.com"
    },
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint2.com"
    }
  ],
  {
    "messageId": "msg_...",
  },
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Enqueue a MessageGet Message
Assistant
Responses are generated using AI and may contain mistakes.
