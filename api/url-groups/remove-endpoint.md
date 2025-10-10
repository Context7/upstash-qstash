# Remove Endpoints

> Remove one or more endpoints

Remove one or multiple endpoints from a URL Group. If all endpoints have been removed, the URL Group will be deleted.

## Request

<ParamField path="urlGroupName" type="string" required>
  The name of your URL Group. If it doesn't exist, we return an error.
</ParamField>

<ParamField body="endpoints" type="Array" required>
  The endpoints to be removed from to the URL Group.

  <Expandable defaultOpen>
    Either `name` or `url` must be provided

    <ParamField body="name" type="string">
      The name of the endpoint
    </ParamField>

    <ParamField body="url" type="string">
      The URL of the endpoint
    </ParamField>
  </Expandable>
</ParamField>

## Response

This endpoint simply returns 200 OK if the endpoints have been removed successfully.

<RequestExample>
  ```sh curl theme={"system"}
  curl -XDELETE https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
    -H "Authorization: Bearer <token>" \
    -H "Content-Type: application/json" \
    -d '{
      "endpoints": [
        {
          "name": "endpoint1",
        },
        {
          "url": "https://somewhere-else.com"
        }
      ]
    }'
  ```

  ```js Node theme={"system"}
  const response = await fetch("https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", {
    method: "DELETE",
    headers: {
      Authorization: "Bearer <token>",
      "Content-Type": "application/json",
    },
    body: {
      endpoints: [
        {
          name: "endpoint1",
        },
        {
          url: "https://somewhere-else.com",
        },
      ],
    },
  });
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json',
  }

  data = {
     "endpoints": [
        {
          "name": "endpoint1",
        },
        {
          "url": "https://somewhere-else.com"
        }
      ]
  }

  response = requests.delete(
    'https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints',
    headers=headers,
    data=data
  )
  ```

  ```go Go theme={"system"}
  var data = strings.NewReader(`{
    "endpoints": [
      {
        "name": "endpoint1",
      },
      {
        "url": "https://somewhere-else.com"
      }
    ]
  }`)
  req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", data)
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
