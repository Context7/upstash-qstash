Request
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/dlq/restart/dlq_XYZ \
-H "Authorization: Bearer <token>" \
-H "Upstash-Workflow-RunId: my-restarted-workflow-XYZ" 

```

Response
Copy
Ask AI
```
{
  "workflowRunId": "my-restarted-workflow-XYZ",
  "workflowCreatedAt": 1748527971000
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
restart
/
{dlqId}
Try it
Request
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/dlq/restart/dlq_XYZ \
-H "Authorization: Bearer <token>" \
-H "Upstash-Workflow-RunId: my-restarted-workflow-XYZ" 

```

Response
Copy
Ask AI
```
{
  "workflowRunId": "my-restarted-workflow-XYZ",
  "workflowCreatedAt": 1748527971000
}

```

When a workflow run fails, it’s automatically moved to the DLQ (Dead Letter Queue) where it can be analyzed and restarted. The restart feature allows you to start a failed workflow completely over from the beginning, re-executing all steps from scratch. This is useful when you want to ensure a clean execution or when the workflow failure might have been caused by corrupted state that requires a fresh start. When you restart a workflow, completely new workflow run is created using the original workflow’s initial configuration and payload. All previous step results are discarded and the workflow executes as if it’s running for the first time. You can overwrite the retries and flow control settings by passing the respective headers in the restart request.
## 
​
Request
​
dlqId
string
required
The ID of the DLQ message containing the failed workflow run
​
Upstash-Flow-Control-Key
string
Optional. Overwrite the flow control key for the restarted workflow. If not provided, the original workflow run configuration will be reused.
​
Upstash-Flow-Control-Value
string
Optional. Overwrite the flow control values for the restarted workflow. If not provided, the original workflow run configuration will be reused.
​
Upstash-Retries
integer
Optional. Overwrite the retry configuration for the restarted workflow steps.
## 
​
Response
​
workflowRunId
string
The ID of the restarted workflow run
​
workflowCreatedAt
integer
Unix timestamp when the restarted workflow was created
Was this page helpful?
YesNo
Suggest editsRaise issue
Resume Workflow RunBulk Restart Workflow Runs
Assistant
Responses are generated using AI and may contain mistakes.
