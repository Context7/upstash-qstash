# List Flow-Control Keys

> List all Flow Control keys

## Response

<ResponseField name="flowControls" type="Array">
  <Expandable>
    <ResponseField name="flowControlKey" type="string">
      The key of the flow control. See the [flow control](/qstash/features/flowcontrol) for more details.
    </ResponseField>

    <ResponseField name="waitListSize" type="integer">
      The number of messages in the wait list that waits for `parallelism` set in the flow control.
    </ResponseField>
  </Expandable>
</ResponseField>

<RequestExample>
  ```sh  theme={"system"}
  curl -X GET https://qstash.upstash.io/v2/flowControl/  -H "Authorization: Bearer <token>"
  ```
</RequestExample>
