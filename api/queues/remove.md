# Remove a Queue

> Removes a queue

<Warning>
  Resuming or creating a queue may take up to a minute.
  Therefore, it is not recommended to pause or delete a queue during critical operations.
</Warning>

## Request

<ParamField path="queueName" type="string" required>
  The name of the queue to remove.
</ParamField>

## Response

This endpoint returns 200 if the queue is removed successfully,
or it doesn't exist.

<RequestExample>
  ```sh curl theme={"system"}
  curl https://qstash.upstash.io/v2/queues/my-queue \
    -H "Authorization: Bearer <token>"
  ```

  ```js Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/queue/my-queue', {
    method: "DELETE",
    headers: {
      'Authorization': 'Bearer <token>'
    }
  });
  ```

  ```python Python  theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
  }

  response = requests.delete(
    'https://qstash.upstash.io/v2/queue/my-queue',
     headers=headers
  )
  ```

  ```go Go theme={"system"}
  req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/queue/my-queue", nil)
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
