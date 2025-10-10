# Upsert URL Group and Endpoint

> Add an endpoint to a URL Group

If the URL Group does not exist, it will be created. If the endpoint does not exist, it will be created.

## Request

<ParamField path="urlGroupName" type="string" required>
  The name of your URL Group (topic). If it doesn't exist yet, it will be created.
</ParamField>

<ParamField body="endpoints" type="Array" required>
  The endpoints to add to the URL Group.

  <Expandable defaultOpen>
    <ParamField body="name" type="string">
      The name of the endpoint
    </ParamField>

    <ParamField body="url" type="string" required>
      The URL of the endpoint
    </ParamField>
  </Expandable>
</ParamField>

## Response

This endpoint returns 200 if the endpoints are added successfully.

<RequestExample>
  ```sh curl theme={"system"}
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

  ```js Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      'endpoints': [
        {
          'name': 'endpoint1',
          'url': 'https://example.com'
        },
        {
          'name': 'endpoint2',
          'url': 'https://somewhere-else.com'
        }
      ]
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
      'endpoints': [
          {
              'name': 'endpoint1',
              'url': 'https://example.com',
          },
          {
              'name': 'endpoint2',
              'url': 'https://somewhere-else.com',
          },
      ],
  }

  response = requests.post(
    'https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints',
    headers=headers, 
    json=json_data
  )
  ```

  ```go Go  theme={"system"}
  var data = strings.NewReader(`{
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
  }`)
  req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", data)
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
