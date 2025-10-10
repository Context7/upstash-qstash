# Cancel Message

> Stop delivery of an existing message

Cancelling a message will remove it from QStash and stop it from being delivered
in the future. If a message is in flight to your API, it might be too late to
cancel.

## Request

<ParamField path="messageId" type="string" required>
  The id of the message to cancel.
</ParamField>

## Response

This endpoint only returns `202 OK`

<RequestExample>
  ```sh curl theme={"system"}
  curl -XDELETE https://qstash.upstash.io/v2/messages/msg_123 \
    -H "Authorization: Bearer <token>"
  ```

  ```js Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/messages/msg_123', {
    method: 'DELETE',
    headers: {
      'Authorization': 'Bearer <token>'
    }
  });
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
  }

  response = requests.delete(
    'https://qstash.upstash.io/v2/messages/msg_123', 
    headers=headers
  )
  ```

  ```go Go theme={"system"}
  req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/messages/msg_123", nil)
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
  ```text 202 Accepted theme={"system"}
  OK
  ```
</ResponseExample>
