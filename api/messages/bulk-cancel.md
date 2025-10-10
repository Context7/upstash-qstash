# Bulk Cancel Messages

> Stop delivery of multiple messages at once

Bulk cancel allows you to cancel multiple messages at once.

<Note>
  Cancelling a message will remove it from QStash and stop it from being delivered
  in the future. If a message is in flight to your API, it might be too late to
  cancel.
</Note>

<Warning>
  If you provide a set of message IDs in the body of the request, only those messages will be cancelled.

  If you include filter parameters in the request body, only the messages that match the filters will be canceled.

  If the `messageIds` array is empty, QStash will cancel all of your messages.

  If no body is sent, QStash will also cancel all of your messages.
</Warning>

This operation scans all your messages and attempts to cancel them.
If an individual message cannot be cancelled, it will not continue and will return an error message.
Therefore, some messages may not be cancelled at the end.
In such cases, you can run the bulk cancel operation multiple times.

<Note>
  You can filter the messages to cancel by including filter parameters in the request body.
</Note>

## Request

<ParamField body="messageIds" type="Array">
  The list of message IDs to cancel.
</ParamField>

<ParamField body="queueName" type="string">
  Filter messages to cancel by queue name.
</ParamField>

<ParamField body="url" type="string">
  Filter messages to cancel by destination URL.
</ParamField>

<ParamField body="topicName" type="string">
  Filter messages to cancel by URL Group (topic) name.
</ParamField>

<ParamField body="fromDate" type="number">
  Filter messages to cancel by starting date, in milliseconds (Unix timestamp). This is inclusive.
</ParamField>

<ParamField body="toDate" type="number">
  Filter messages to cancel by ending date, specified in milliseconds (Unix timestamp). This is inclusive.
</ParamField>

<ParamField body="scheduleId" type="string">
  Filter messages to cancel by schedule ID.
</ParamField>

<ParamField body="callerIP" type="string">
  Filter messages to cancel by IP address of publisher.
</ParamField>

## Response

A cancelled object with the number of cancelled messages.

```JSON  theme={"system"}
{
  "cancelled": number
}
```

<RequestExample>
  ```sh curl theme={"system"}
  curl -XDELETE https://qstash.upstash.io/v2/messages/ \
     -H "Content-Type: application/json" \
    -H "Authorization: Bearer <token>" \
    -d '{"messageIds": ["msg_id_1", "msg_id_2", "msg_id_3"]}'
  ```

  ```js Node theme={"system"}
  const response = await fetch('https://qstash.upstash.io/v2/messages', {
    method: 'DELETE',
    headers: {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json',
      body: {
          messageIds: [
              "msg_id_1",
              "msg_id_2",
              "msg_id_3",
          ],
      },
    }
  });
  ```

  ```python Python theme={"system"}
  import requests

  headers = {
      'Authorization': 'Bearer <token>',
      'Content-Type': 'application/json',
  }

  data = {
    "messageIds": [
      "msg_id_1",
      "msg_id_2",
      "msg_id_3"
    ]
  }

  response = requests.delete(
    'https://qstash.upstash.io/v2/messages',
    headers=headers,
    data=data
  )
  ```

  ```go Go theme={"system"}
  var data = strings.NewReader(`{
    "messageIds": [
      "msg_id_1",
      "msg_id_2",
      "msg_id_3"
    ]
  }`)
  req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/messages", data)
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

<ResponseExample>
  ```json 202 Accepted theme={"system"}
  {
    "cancelled": 10
  }
  ```
</ResponseExample>
