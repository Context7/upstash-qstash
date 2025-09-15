Request
Copy
Ask AI
```
curl -X POST "https://qstash.upstash.io/v2/workflows/dlq/callback/my-dlq-id" \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "workflowRunId": "wfr_abcde",
  "workflowCreatedAt": 1680000000000
}

```

POST
/
v2
/
workflows
/
dlq
/
callback
/
{dlqId}
Try it
Request
Copy
Ask AI
```
curl -X POST "https://qstash.upstash.io/v2/workflows/dlq/callback/my-dlq-id" \
  -H "Authorization: Bearer <token>"

```

200 OK
Copy
Ask AI
```
{
  "workflowRunId": "wfr_abcde",
  "workflowCreatedAt": 1680000000000
}

```

If the failure callback for a workflow run has failed, you can use this endpoint to manually trigger the failure callback again. This is useful for ensuring that your system is notified of workflow failures even if the original callback attempt did not succeed. The state of the failure callback for each workflow run is included in the DLQ message response as failureCallbackInfo.state. You can filter for all workflow runs with a failed failure callback by using the failureCallbackState filter when listing workflow runs in the DLQ with the `/v2/workflows/dlq` endpoint.
## 
​
Request
​
dlqId
string
required
The DLQ id of the failed workflow run for which you want to rerun the failure callback. You can find this id when listing all workflow runs in the DLQ with the /v2/workflows/dlq endpoint.
## 
​
Response
​
workflowRunId
string
The ID of the workflow run for which the failure callback was rerun.
​
workflowCreatedAt
integer
Unix timestamp when the workflow run was created.
Was this page helpful?
YesNo
Suggest editsRaise issue
Delete a failed workflow run from the DLQResume Workflow Run
Assistant
Responses are generated using AI and may contain mistakes.
