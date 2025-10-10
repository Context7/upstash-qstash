# Batch Messages

> Send multiple messages in a single request

You can learn more about batching in the [batching section](/qstash/features/batch).

<Note>
  API playground is not available for this endpoint. You can use the cURL example below.
</Note>

<Info>You can publish to destination, URL Group or queue in the same batch request.</Info>

## Request

The endpoint is `POST https://qstash.upstash.io/v2/batch` and the body is an array of
messages. Each message has the following fields:

```
destination: string
headers: headers object
body: string
```

The headers are identical to the headers in the [create](/qstash/api/publish#request) endpoint.

```shell cURL theme={"system"}
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

## Response

```json  theme={"system"}
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
