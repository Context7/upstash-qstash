On this page
You can cancel a running workflow both programatically and from your Upstash Workflow console.
## 
​
Cancelling via console
In your Upstash Workflow console, find the run you’d like to cancel and press the `Cancel Workflow` button on the right side:
## 
​
Cancelling programatically
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.cancel({ ids: "<WORKFLOW_RUN_ID>" });

```

And replace `<WORKFLOW_RUN_ID>` with your actual run ID. See the documentation of `client.cancel` method for more information about other ways of canceling workflows. You can also use the Upstash Workflow REST API to cancel a run programatically.
Was this page helpful?
YesNo
Suggest editsRaise issue
Handle Failed RunsWaiting for Events
Assistant
Responses are generated using AI and may contain mistakes.
