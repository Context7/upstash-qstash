# List URL Groups

> List all your URL Groups

## Request

No parameters

## Response

<ResponseField name="" type="Array" required>
  <Expandable defaultOpen>
    <ResponseField name="createdAt" type="int" required>
      The creation time of the URL Group. UnixMilli
    </ResponseField>

    <ResponseField name="updatedAt" type="int" required>
      The update time of the URL Group. UnixMilli
    </ResponseField>

    <ResponseField name="name" type="string" required>
      The name of the URL Group.
    </ResponseField>

    <ResponseField name="endpoints" type="Array" required>
      <Expandable defaultOpen>
        <ParamField body="name" type="string" required>
          The name of the endpoint.
        </ParamField>

        <ParamField body="url" type="string" required>
          The URL of the endpoint
        </ParamField>
      </Expandable>
    </ResponseField>
  </Expandable>
</ResponseField>

<RequestExample>
  ```sh curl theme={"system"}
  curl https://qstash.upstash.io/v2/topics \
    -H "Authorization: Bearer <token>"
  ```

  ```js Node theme={"system"}
  const response = await fetch("https://qstash.upstash.io/v2/topics", {
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
    'https://qstash.upstash.io/v2/topics',
    headers=headers
  )
  ```

  ```go Go theme={"system"}
  req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/topics", nil)
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
  [
    {
    
      "createdAt": 1623345678001,
      "updatedAt": 1623345678001,
      "name": "my-url-group",
      "endpoints": [
        {
          "name": "my-endpoint",
          "url": "https://my-endpoint.com"
        }
      ]
    },
    // ...
  ]
  ```
</ResponseExample>
