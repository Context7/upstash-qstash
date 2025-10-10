# Remove Schedule

> Remove a schedule

## Request

<ParamField path="scheduleId" type="string">
  The schedule id to remove
</ParamField>

## Response

This endpoint simply returns 200 OK if the schedule is removed successfully.

<RequestExample>
  ```sh curl theme={"system"}
  curl -XDELETE https://qstash.upstash.io/v2/schedules/scd_123 \
    -H "Authorization: Bearer <token>"
  ```

  ```javascript Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/schedules/scd_123', {
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
    'https://qstash.upstash.io/v2/schedules/scd_123', 
    headers=headers
  )
  ```

  ```go Go  theme={"system"}
  req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/schedules/scd_123", nil)
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
