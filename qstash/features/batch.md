On this page
Publishing is great for sending one message at a time, but sometimes you want to send a batch of messages at once. This can be useful to send messages to a single or multiple destinations. QStash provides the `batch` endpoint to help you with this. If the format of the messages are valid, the response will be an array of responses for each message in the batch. When batching URL Groups, the response will be an array of responses for each destination in the URL Group. If one message fails to be sent, that message will have an error response, but the other messages will still be sent.
You can publish to destination, URL Group or queue in the same batch request.
## 
​
Batching messages with destinations
You can also send messages to the same destination!
cURL
TypeScript
Python
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "destination": "https://example.com/destination1"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'

```

## 
​
Batching messages with URL Groups
If you have a URL Group, you can batch send with the URL Group as well.
cURL
TypeScript
Python
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "destination": "myUrlGroup"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'

```

## 
​
Batching messages with queue
If you have a queue, you can batch send with the queue. It is the same as publishing to a destination, but you need to set the queue name.
cURL
TypeScript
Python
Copy
Ask AI
```
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "queue": "my-queue",
        "destination": "https://example.com/destination1"
      },
      {
        "queue": "my-second-queue",
        "destination": "https://example.com/destination2"
      }
     ]'

```

## 
​
Batching messages with headers and body
You can provide custom headers and a body for each message in the batch.
cURL
TypeScript
Python
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

#### 
​
The response for this will look like
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
URL GroupsCallbacks
Assistant
Responses are generated using AI and may contain mistakes.
