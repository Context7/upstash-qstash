# Get Message

> Retrieve a message by its id

## Request

<ParamField path="messageId" type="string" required>
  The id of the message to retrieve.
</ParamField>

<Warning>
  Messages are removed from the database shortly after they're delivered, so you
  will not be able to retrieve a message after. This endpoint is intended to be used
  for accessing messages that are in the process of being delivered/retried.
</Warning>

## Response

<Snippet file="qstash-message-type.mdx" />

<RequestExample>
  ```sh curl theme={"system"}
  curl https://qstash.upstash.io/v2/messages/msg_123 \
    -H "Authorization: Bearer <token>"
  ```

  ```js Node theme={"system"}
  const response = await fetch("https://qstash.upstash.io/v2/messages/msg_123", {
    headers: {
      Authorization: "Bearer <token>",
    },
  });
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
  }

  response = requests.get(
    'https://qstash.upstash.io/v2/messages/msg_123',
    headers=headers
  )
  ```

  ```go Go theme={"system"}
  req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/messages/msg_123", nil)
  if err != nil {
    log.Fatal(err)
  }
  req.Header.Set("Authorization", "Bearer <token>")
  resp, err := http.DefaultClient.Do(req)
  if err != nil {
    log.Fatal(err)
  }
  defer resp.Body.Close()
  ```
</RequestExample>

<ResponseExample>
  ```json 200 OK theme={"system"}
  {
    "messageId": "msg_123",
    "topicName": "myTopic",
    "url":"https://example.com",
    "method": "POST",
    "header": {
      "My-Header": ["my-value"]
    },
    "body": "{\"foo\":\"bar\"}",
    "createdAt": 1620000000000
  }
  ```
</ResponseExample>
