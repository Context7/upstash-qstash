# Get Signing Keys

> Retrieve your signing keys

## Response

<ResponseField name="current" type="string" required>
  Your current signing key.
</ResponseField>

<ResponseField name="next" type="string" required>
  The next signing key.
</ResponseField>

<RequestExample>
  ```sh curl theme={"system"}
  curl https://qstash.upstash.io/v2/keys \
    -H "Authorization: Bearer <token>"
  ```

  ```javascript Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/keys', {
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

  response = requests.get(
    'https://qstash.upstash.io/v2/keys',
     headers=headers
  )
  ```

  ```go Go  theme={"system"}
  req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/keys", nil)
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
  { "current": "sig_123", "next": "sig_456" }
  ```
</ResponseExample>
