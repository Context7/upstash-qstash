# Enqueue a Message

> Enqueue a message

## Request

<ParamField path="queueName" type="string" required>
  The name of the queue that message will be enqueued on.
  If doesn't exist, it will be created automatically.
</ParamField>

<ParamField path="destination" type="string" required>
  Destination can either be a topic name or id that you configured in the
  Upstash console, a valid url where the message gets sent to, or a valid
  QStash API name like `api/llm`. If the destination is a URL, make sure
  the URL is prefixed with a valid protocol (`http://` or `https://`)
</ParamField>

<Snippet file="qstash-common-request.mdx" />

<ParamField header="Upstash-Deduplication-Id" type="string">
  Id to use while deduplicating messages, so that only one message with
  the given deduplication id is published.
</ParamField>

<ParamField header="Upstash-Content-Based-Deduplication" type="boolean">
  When set to true, automatically deduplicates messages based on their content,
  so that only one message with the same content is published.

  Content based deduplication creates unique deduplication ids based on the
  following message fields:

  * Destination
  * Body
  * Headers
</ParamField>

## Response

<Snippet file="qstash-publish-response.mdx" />

<RequestExample>
  ```sh curl theme={"system"}
  curl -X POST "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com" \
    -H "Authorization: Bearer <token>" \
    -H "Content-Type: application/json" \
    -H "Upstash-Method: POST" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Forward-Custom-Header: custom-value" \
    -d '{"message":"Hello, World!"}'
  ```

  ```js Node theme={"system"}
  const response = await fetch(
    "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com",
    {
      method: "POST",
      headers: {
        Authorization: "Bearer <token>",
        "Content-Type": "application/json",
        "Upstash-Method": "POST",
        "Upstash-Retries": "3",
        "Upstash-Forward-Custom-Header": "custom-value",
      },
      body: JSON.stringify({
        message: "Hello, World!",
      }),
    }
  );
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json',
      'Upstash-Method': 'POST',
      'Upstash-Retries': '3',
      'Upstash-Forward-Custom-Header': 'custom-value',
  }

  json_data = {
      'message': 'Hello, World!',
  }

  response = requests.post(
    'https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com',
     headers=headers,
     json=json_data
  )
  ```

  ```go Go theme={"system"}
  var data = strings.NewReader(`{"message":"Hello, World!"}`)
  req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com", data)
  if err != nil {
    log.Fatal(err)
  }
  req.Header.Set("Authorization", "Bearer <token>")
  req.Header.Set("Content-Type", "application/json")
  req.Header.Set("Upstash-Method", "POST")
  req.Header.Set("Upstash-Retries", "3")
  req.Header.Set("Upstash-Forward-Custom-Header", "custom-value")
  resp, err := http.DefaultClient.Do(req)
  if err != nil {
    log.Fatal(err)
  }
  defer resp.Body.Close()
  ```
</RequestExample>

<ResponseExample>
  ```json URL theme={"system"}
  {
    "messageId": "msd_1234",
    "url": "https://www.example.com"
  }
  ```

  ```json URL Group theme={"system"}
  [
    {
      "messageId": "msd_1234",
      "url": "https://www.example.com"
    },
    {
      "messageId": "msd_5678",
      "url": "https://www.somewhere-else.com",
      "deduplicated": true
    }
  ]
  ```
</ResponseExample>
