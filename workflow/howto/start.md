On this page
You’ve defined your workflow, and the final step is to trigger the endpoint! There are two main ways to start your workflow:
### 
​
1. Using `client.trigger` (Recommended)
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
We recommend using `client.trigger` to start your workflow.
Single Workflow
Multiple Workflows
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" })
const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: "hello there!",         // optional body
  headers: { ... },             // optional headers
  workflowRunId: "my-workflow", // optional workflow run id
  retries: 3                    // optional retries in the initial request
  delay: "10s"                  // optional delay value
  failureUrl: "https://<YOUR_FAILURE_URL>", // optional failure url
  useFailureFunction: true,     // whether a failure function is defined in the endpoint
  flowControl: { ... }          // optional flow control
})

console.log(workflowRunId)
// prints wfr_my-workflow

```

### 
​
2. Sending an HTTP Request
This approach is recommended for quick testing via curl.
If you’ve secured your endpoint with signing keys, only the `trigger` methid will work. Direct calls to the endpoint (e.g., via `curl` or `fetch`) will not be accepted.
  * curl
  * fetch (TypeScript)
  * requests (Python)


Copy
Ask AI
```
curl -X POST https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE> \
     -H "my-header: foo" \
     -d '{"foo": "bar"}'

```

### 
​
Accessing Payload and Headers
When you call the endpoint, the payload and headers you send will be accessible in the context:
  * The payload is available in the `context.requestPayload` field.
  * The headers are available in the `context.headers` field.

For more details, refer to the documentation on the Context object.
Was this page helpful?
YesNo
Suggest editsRaise issue
ExamplesHandle Failed Runs
Assistant
Responses are generated using AI and may contain mistakes.
