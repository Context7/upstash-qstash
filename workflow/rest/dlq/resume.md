Request
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/dlq/resume/dlq_XYZ
-H "Authorization: Bearer <token>" 
-H "Upstash-Workflow-RunId: my-resumed-workflow-XYZ" 

```

Response
Copy
Ask AI
```
{
  "workflowRunId": "my-resumed-workflow-XYZ",
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
resume
/
{dlqId}
Try it
Request
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/dlq/resume/dlq_XYZ
-H "Authorization: Bearer <token>" 
-H "Upstash-Workflow-RunId: my-resumed-workflow-XYZ" 

```

Response
Copy
Ask AI
```
{
  "workflowRunId": "my-resumed-workflow-XYZ",
  "workflowCreatedAt": 1748527971000
}

```

When a workflow run fails, it’s automatically moved to the DLQ (Dead Letter Queue) where it can be analyzed and resumed. The resume feature allows you to continue a failed workflow run from exactly where it failed, without re-executing successfully completed steps. This is particularly useful for long-running workflows where you don’t want to lose progress from successful steps when a single step fails. When you resume a workflow, a fresh workflow run is created. All data from successfully executed steps is maintained. You can overwrite the workflow’s run ID, retries and flow control settings by passing the respective headers in the resume request.
You can make changes to the workflow code as long as these changes come after the failed steps. However, making changes before the failed step will break the code and is not allowed.For more details, check out Handle workflow route code changes page.
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
Optional. Overwrite the flow control key for the resumed workflow. If not provided, the original workflow run configuration will be reused.
​
Upstash-Flow-Control-Value
string
Optional. Overwrite the flow control values for the resumed workflow. If not provided, the original workflow run configuration will be reused.
​
Upstash-Retries
integer
Optional. Overwrite the retry configuration for the resumed workflow steps.
## 
​
Response
​
workflowRunId
string
The ID of the resumed workflow run
​
workflowCreatedAt
integer
Unix timestamp when the resumed workflow run was created
Was this page helpful?
YesNo
Suggest editsRaise issue
Rerun Failure Callback for Workflow RunRestart Workflow Run
Assistant
Responses are generated using AI and may contain mistakes.
