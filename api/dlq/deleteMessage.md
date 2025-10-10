# Delete a message from the DLQ

> Manually remove a message

Delete a message from the DLQ.

## Request

<ParamField path="dlqId" type="string">
  The dlq id of the message you want to remove. You will see this id when
  listing all messages in the dlq with the [/v2/dlq](/qstash/api/dlq/listMessages) endpoint.
</ParamField>

## Response

The endpoint doesn't return anything, a status code of 200 means the message is removed from the DLQ.
If the message is not found in the DLQ, (either is has been removed by you, or automatically), the endpoint returns a 404 status code.

<RequestExample>
  ```sh  theme={"system"}
  curl -X DELETE https://qstash.upstash.io/v2/dlq/my-dlq-id \
    -H "Authorization: Bearer <token>"
  ```
</RequestExample>
