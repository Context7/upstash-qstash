# Get Flow-Control Keys

> Get Information on Flow-Control

## Request

<ParamField path="flowControlKey" type="string">
  The key of the flow control. See the [flow control](/qstash/features/flowcontrol) for more details.
</ParamField>

## Response

<ResponseField name="flowControlKey" type="string">
  The key of of the flow control.
</ResponseField>

<ResponseField name="waitListSize" type="integer">
  The number of messages in the wait list that waits for `parallelism` set in the flow control.
</ResponseField>

<RequestExample>
  ```sh  theme={"system"}
  curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
  ```
</RequestExample>
