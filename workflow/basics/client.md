On this page
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
Workflow client allows you to interact with your workflow runs. Currently, it has three basic functionality:
  * cancel a running workflow run
  * notify a workflow run waiting for an event
  * get workflow runs waiting for some event

We are planning to add more functionality in the future. See the roadmap for more details.
## 
​
Trigger Workflow
Using the `trigger` method, you can start a workflow run and get its run id.
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
  retries: 3,                   // optional retries in the initial request
  retryDelay: "1000 * (1 + retried)", // optional delay between retries
  delay: "10s"                  // optional delay value
  failureUrl: "https://<YOUR_FAILURE_URL>", // optional failure url
  useFailureFunction: true,     // whether a failure function is defined in the endpoint
  flowControl: {                // optional flow control
    key: "USER_GIVEN_KEY",
    rate: 10,
    parallelism: 5,
    period: "10m"
  },
})

console.log(workflowRunId)
// prints wfr_my-workflow

```

If both `failureUrl` and `useFailureFunction` are provided, `useFailureFunction` takes precedence and the value of the `url` parameter is used as `failureUrl`. If `workflowRunId` parameter isn’t passed, a run id will be generated randomly. If `workflowRunId` is passed, `wfr_` prefix will be added to it. For other alternatives of starting a workflow, see the documentation on starting a workflow run.
## 
​
Get Workflow Logs
Using the `log` method, you can use the List Workflow Runs API:
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" })
const { runs, cursor } = await client.logs({
  // Id of the workflow run to get
  workflowRunId,
  // Number of workflows to get
  count,
  // Workflow state to filter for.
  // One of "RUN_STARTED", "RUN_SUCCESS", "RUN_FAILED", "RUN_CANCELED"
  state,
  // Workflow url to search for. should be an exact match
  workflowUrl,       
  // Unix timestamp when the run was created
  workflowCreatedAt, 
  // Cursor from a previous request to continue the search
  cursor             
})

```

All the parameters above are optional. The response includes `cursor` and `runs`. Using the `cursor`, you can continue the search later. `runs` will be a list of runs. Each run has these fields:
  * `workflowRunId`: ID of the workflow
  * `workflowUrl`: URL of the workflow
  * `workflowState`: State of the workflow run.
  * `workflowRunCreatedAt`: number; Time when the workflow run started (as unix timestamp)
  * `workflowRunCompletedAt`; If run has completed, time when workflow run completed (as unix timestamp)
  * `failureFunction`: Information on the message published when the workflow failed and `failureUrl` or `failureFunction` were called
  * `dlqId`: If the workflow run has failed, DLQ id associated with the workflow run.
  * `workflowRunResponse`: Result returned at the end of the workflow.
  * `invoker`: If the workflow was invoked; run id, url and created time of the invoking workflow.
  * `steps`: List of steps showing the progress of the workflow.

The `steps` field contains a list of steps. Each step is in one of the following three formats:
Single Step
Parallel Steps
Next Step
Copy
Ask AI
```
{
  type: "single";
  // a single step in an array
  steps: [
    {
      // step info...
    }
  ]
}

```

## 
​
Cancel Workflow Runs
There are multiple ways you can cancel workflow runs:
  * pass one or more workflow run ids to cancel them
  * pass a workflow url to cancel all runs starting with this url
  * cancel all pending or active workflow runs


### 
​
Cancel a set of workflow runs
Copy
Ask AI
```
// cancel a single workflow
await client.cancel({ ids: "<WORKFLOW_RUN_ID>" });

// cancel a set of workflow runs
await client.cancel({ ids: ["<WORKFLOW_RUN_ID_1>", "<WORKFLOW_RUN_ID_2>"] });

```

### 
​
Cancel workflows starting with a url
If you have an endpoint called `https://your-endpoint.com` and you want to cancel all workflow runs on it, you can use `urlStartingWith`. Note that this will cancel workflows in all endpoints under `https://your-endpoint.com`.
Copy
Ask AI
```
await client.cancel({ urlStartingWith: "https://your-endpoint.com" });

```

### 
​
Cancel _all_ workflows
To cancel all pending and currently running workflows, you can do it like this:
Copy
Ask AI
```
await client.cancel({ all: true });

```

## 
​
Dead Letter Queue (DLQ)
The DLQ functionality allows you to manage failed workflow runs that have been moved to the dead letter queue.
### 
​
List DLQ Messages
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

// Define filters for the DLQ messages (optional)
const dlqFilters = {
  fromDate: Date.now() - 86400000, // last 24 hours
  toDate: Date.now(),
  url: "https://your-endpoint.com",
  responseStatus: 500
}

// List all DLQ messages
const { messages, cursor } = await client.dlq.list({ filter: dlqFilters });

// List with pagination and filtering
const result = await client.dlq.list({
  cursor,
  count: 10,
  filter: dlqFilters
});


```

### 
​
Resume Failed Workflows
Resume a workflow from where it failed:
Single
Multiple
Copy
Ask AI
```
const { messages } = await client.dlq.list();

const response = await client.dlq.resume({
  dlqId: messages[0].dlqId, // Use the dlqId from the message
  flowControl: {
    key: "my-flow-control-key",
    value: "my-flow-control-value",
  },
  retries: 3,
});


```

### 
​
Restart Failed Workflows
Restart a workflow from the beginning:
Single
Multiple
Copy
Ask AI
```
const { messages } = await client.dlq.list();

const response = await client.dlq.restart({
  dlqId: messages[0].dlqId, // Use the dlqId from the message
  flowControl: {
    key: "my-flow-control-key",
    value: "my-flow-control-value",
  },
  retries: 3,
});


```

The difference between `resume` and `restart`:
  * **Resume** : Continues execution from where the workflow failed
  * **Restart** : Starts execution from the beginning with the same initial payload


### 
​
Retry Failure Function
If a workflow’s `failureFunction` or `failureUrl` request has failed, you can retry it using the `retryFailureFunction` method:
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

// Retry the failure callback for a specific DLQ message
const response = await client.dlq.retryFailureFunction({
  dlqId: "dlq-12345" // The ID of the DLQ message to retry
});

```

This method allows you to retry the failure callback of a workflow run whose `failureUrl` or `failureFunction` request has failed.
## 
​
Notify Waiting Workflow
To notify a workflow waiting for an event, you can use the `notify` method:
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.notify({
  eventId: "my-event-id",
  eventData: "my-data", // data passed to the workflow run
});

```

The data passed in `eventData` will be available to the workflow run in the `eventData` field of the `context.waitForEvent` method.
## 
​
Get Waiters of Event
To get the list of waiters for some event id, you can use the `getWaiters` method:
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const result = await client.getWaiters({
  eventId: "my-event-id",
});

```

Result will be a list of `Waiter` objects:
​
Waiter
Show child attributes
​
url
string
required
URL to call upon notify
​
deadline
number
required
Unix timestamp for when the wait will time out
​
headers
Record<string, string[]>
required
Headers sent in case of notify
​
timeoutUrl
string
URL to call upon timeout
​
timeoutBody
unknown
Body used in timeout request
​
timeoutHeaders
Record<string, string[]>
Headers sent in case of time out
Was this page helpful?
YesNo
Suggest editsRaise issue
Workflow ContextHow Workflow works
Assistant
Responses are generated using AI and may contain mistakes.
