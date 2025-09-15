curl
Workflow SDK
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/workflows/runs \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -d '{"workflowUrl": "https://example.com"}'

```

202 Accepted
Copy
Ask AI
```
{
  "cancelled": 10
}

```

DELETE
/
v2
/
workflows
/
runs
Try it
curl
Workflow SDK
Node
Python
Go
Copy
Ask AI
```
curl -XDELETE https://qstash.upstash.io/v2/workflows/runs \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -d '{"workflowUrl": "https://example.com"}'

```

202 Accepted
Copy
Ask AI
```
{
  "cancelled": 10
}

```

Bulk cancel allows you to cancel multiple workflow runs at once.
If you provide a list of workflow run IDs in the request body, only those specific workflow runs will be canceled.If you include the workflow URL parameter, all workflow runs matching the URL filter will be canceled.If the request body is empty, all workflow runs will be canceled.
This operation scans all your workflow runs and attempts to cancel them. If a specific workflow run cannot be canceled, it will return an error message. Therefore, some workflow runs may not be cancelled at the end. In such cases, you can run the bulk cancel operation multiple times.
## 
​
Request
​
workflowRunIds
Array
The list of workflow run IDs to cancel.
​
workflowUrl
string
The prefix filter to match workflow run URLs. Workflow runs with URLs starting with this prefix will be canceled.
## 
​
Response
A cancelled object with the number of cancelled workflow runs.
Copy
Ask AI
```
{
  "cancelled": number
}

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Cancel WorkflowList workflow runs
Assistant
Responses are generated using AI and may contain mistakes.
