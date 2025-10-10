# Upsert a Queue

> Updates or creates a queue

## Request

<ParamField body="queueName" type="string" required>
  The name of the queue.
</ParamField>

<ParamField body="parallelism" type="int" required>
  The number of parallel consumers consuming from [the queue](/qstash/features/queues).

  <Warning>
    For the parallelism limit, we introduced an easier and less limited API with publish.
    Please check the [Flow Control](/qstash/features/flowcontrol) page for the detailed information.

    Setting parallelism with queues will be deprecated at some point.
  </Warning>
</ParamField>

## Response

This endpoint returns

* 200 if the queue is added successfully.
* 412 if it fails because of the the allowed number of queues limit

<RequestExample>
  ```sh curl theme={"system"}
  curl -XPOST https://qstash.upstash.io/v2/queues/ \
    -H "Authorization: Bearer <token>" \
    -H "Content-Type: application/json" \
    -d '{
      "queueName": "my-queue" , 
      "parallelism" : 5,
    }'
  ```

  ```js Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/queues/', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      "queueName": "my-queue" , 
      "parallelism" : 5,
    })
  });
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json',
  }

  json_data = {
      "queueName": "my-queue" , 
      "parallelism" : 5,
    }

  response = requests.post(
    'https://qstash.upstash.io/v2/queues/',
    headers=headers, 
    json=json_data
  )
  ```

  ```go Go  theme={"system"}
  var data = strings.NewReader(`{
      "queueName": "my-queue" , 
      "parallelism" : 5,
    }`)
  req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/queues/", data)
  if err != nil {
    log.Fatal(err)
  }
  req.Header.Set("Authorization", "Bearer <token>")
  req.Header.Set("Content-Type", "application/json")
  resp, err := http.DefaultClient.Do(req)
  if err != nil {
    log.Fatal(err)
  }
  defer resp.Body.Close()
  ```
</RequestExample>
