On this page
A workflow’s context is a JavaScript object provided by the serve function and is used to define your workflow endpoint. This context object offers utility methods for creating workflow steps, managing delays, and performing timeout-resistant HTTP calls.
api/workflow/route.ts
main.py
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(
  // 👇 the workflow context
  async (context) => {
    // ...
  }
);

```

This context object provides utility methods to create workflow steps, wait for certain periods of time or perform timeout-resistant HTTP calls. Further, the context object provides all request headers, the incoming request payload and current workflow ID.
## 
​
Context Object Properties
  * `qstashClient`: QStash client used by the serve method
  * `workflowRunId`: Current workflow run ID
  * `url`: Publically accessible workflow endpoint URL
  * `failureUrl`: URL for workflow failure notifications.
  * `requestPayload`: Incoming request payload
  * `rawInitialPayload`: String version of the initial payload
  * `headers`: Request headers
  * `env`: Environment variables


## 
​
Core Workflow Methods
### 
​
context.run
Defines and executes a workflow step.
Serial execution (TypeScript)
Parallel execution (TypeScript)
Serial execution (Python)
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload;

  const result1 = await context.run("step-1", async () => {
    return someWork(input);
  });

  await context.run("step-2", async () => {
    someOtherWork(result1);
  });
});


```

### 
​
context.sleep
Pauses workflow execution for a specified duration.
Always `await` a `sleep` action to properly pause execution.
TypeScript
Python
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";

export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;

  const user = await context.run("sign-in", async () => {
    const signedInUser = await signIn(userData);
    return signedInUser;
  });

  // 👇 Wait for one day (in seconds)
  await context.sleep("wait-until-welcome-email", "1d");

  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});

```

### 
​
context.sleepUntil
Pauses workflow execution until a specific timestamp.
Always await a `sleepUntil` action to properly pause execution.
TypeScript
Python
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";

export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;

  const user = await context.run("sign-in", async () => {
    return signIn(userData);
  });

  // 👇 Calculate the date for one week from now
  const oneWeekFromNow = new Date();
  oneWeekFromNow.setDate(oneWeekFromNow.getDate() + 7);

  // 👇 Wait until the calculated date
  await context.sleepUntil("wait-for-one-week", oneWeekFromNow);

  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});

```

### 
​
context.call
Performs an HTTP call as a workflow step, allowing for longer response times. Can take up to 15 minutes or 2 hours, depending on your QStash plans max HTTP connection timeout.
TypeScript
Python
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<{ topic: string }>(async (context) => {
  const request = context.requestPayload;

  const {
    status, // response status
    headers, // response headers
    body, // response body
  } = await context.call(
    "generate-long-essay", // Step name
    {
      url: "https://api.openai.com/v1/chat/completions", // Endpoint URL
      method: "POST",
      body: {
        // Request body
        model: "gpt-4o",
        messages: [
          {
            role: "system",
            content:
              "You are a helpful assistant writing really long essays that would cause a normal serverless function to timeout.",
          },
          { role: "user", content: request.topic },
        ],
      },
      headers: {
        // request headers
        authorization: `Bearer ${process.env.OPENAI_API_KEY}`,
      },
    }
  );
});


```

If you want to call OpenAI, you can also use `context.api.openai.call`.
If the endpoint you request does not return a success response (status code 200-299),  
`context.call` will still be treated as successful, and the workflow will continue executing.  
As a result, `failureFunction` or `failureUrl` will not be invoked.To handle non-success cases, you can check the `status` field in the response and implement custom logic as needed.
context.call parameters are:
  * `url`: The URL to send the HTTP request to.
  * `method`: The HTTP method to use for the request (e.g., GET, POST, PUT, etc.). Defaults to GET.
  * `body`: Body to use in the request
  * `headers`: An object representing the HTTP headers to include in the request.
  * `retries`: The number of retry attempts to make if the request fails. Retries use exponential backoff. Defaults to 0 (no retries).
  * `retryDelay`: Delay between retries (in milliseconds). By default, uses exponential backoff. You can use mathematical expressions and the special variable `retried` (current retry attempt count starting from 0). Examples: `1000`, `pow(2, retried)`, `max(10, pow(2, retried))`.
  * `flowControl`: To limit the number of calls made to your endpoint. See Flow Control for more details. The default is no limit. 
    * `key`: The key to use for flow control.
    * `rate`: The maximum number of calls per second.
    * `parallelism`: The maximum number of calls that can be active at the same time.
    * `period`: Time window over which the rate limit is enforced.
  * `timeout`: The maximum duration to wait for a response from the endpoint, in seconds. If retries are enabled, this timeout applies individually to each retry attempt.
  * `workflow`: If you are using `serveMany`, you can call another workflow defined under the same `serveMany` method by passing it to the `workflow` parameter of `context.call`.

context.call attempts to parse the response body as JSON. If this is not possible, the body is returned as it is. In TypeScript, you can declare the expected result type as follows:
Copy
Ask AI
```
type ResultType = {
  field1: string,
  field2: number
};

const result = await context.call<ResultType>( ... );

```

The context.call method can make requests to any public API endpoint. However, it cannot:
  * Make requests to localhost (unless you set up a local tunnel, here’s how)
  * Make requests to internal Upstash QStash endpoints


### 
​
context.api
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
In addition to context.call, another way to make third party requests is to use the context.api namespace. Under this namespace, you can find integrations for OpenAI, Anthropic and Resend. With context.api, you can call the available integrations in a typesafe manner.
OpenAI
Anthropic
Resend
Copy
Ask AI
```
const { status, body } = await context.api.openai.call("Call OpenAI", {
  token: "<OPENAI_API_KEY>",
  operation: "chat.completions.create",
  body: {
    model: "gpt-4o",
    messages: [
      {
        role: "system",
        content: "Assistant says 'hello!'",
      },
      { role: "user", content: "User shouts back 'hi!'" },
    ],
  },
});

```

We are planning to add more integrations over time. You can learn more about these integrations under the integrations section.
### 
​
context.waitForEvent
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
Stops the workflow run until it is notified externally to continue. There is also a timeout setting which makes the workflow continue if it’s not notified within the time frame.
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<{ topic: string }>(async (context) => {
  const request = context.requestPayload;

  const {
    eventData, // data passed in notify
    timeout, // boolean denoting whether the step was notified or timed out
  } = await context.waitForEvent("wait for some event", "my-event-id", {
    timeout: "1000s", // 1000 second timeout
  });
});


```

Default timeout value is 7 days. A workflow run waiting for event can be notified in two ways:
  * `context.notify`: Notify step explained below
  * `client.notify`: Notify method of the Workflow Client.


### 
​
context.notify
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
Notifies workflows waiting for an event with some payload.
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<{ topic: string }>(async (context) => {
  const payload = context.requestPayload;

  const {
    notifyResponse, // result of notify, which is a list of notified waiters
  } = await context.notify("notify step", "my-event-Id", payload);
});


```

`notifyResponse` is a list of `NotifyResponse` objects:
Copy
Ask AI
```
export type NotifyResponse = {
  waiter: Waiter;
  messageId: string;
  error: string;
  workflowRunId: string;
  workflowCreatedAt: number;
};

```

More details about the `Waiter` object:
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
### 
​
context.invoke
Triggers another workflow run and waits for its completion. The workflow continues when the invoked workflow finishes, whether successfully, with failure, or is canceled. The `body` is the data returned by the invoked workflow, if any is returned.
Copy
Ask AI
```
const { body, isFailed, isCanceled } = await context.invoke(
  "invoke another workflow",
  {
    workflow: anotherWorkflow,
    body: "test",
    header: {...}, // headers to pass to anotherWorkflow (optional)
    retries,       // number of retries (optional, default: 3)
    retryDelay,    // delay between retries (optional, uses exponential backoff by default)
    flowControl,   // flow control settings (optional)
    workflowRunId  // workflowRunId to set (optional)
  }
);

```

Only workflows that served together can invoke each other. To learn more about how you can serve multiple workflows together, checkout Invoke other workflows guide.
### 
​
context.cancel
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
The methods we listed so far were all for defining a workflow step. `context.cancel` is different. `context.cancel` allows you to cancel the current workflow:
Copy
Ask AI
```
export const { POST } = serve<{ topic: string }>(async (context) => {
  const payload = context.requestPayload

  const result = await context.run("check if canceled", () => { ... });

  if (result.cancel) {
    await context.cancel() // cancel the workflow run
  }
})

```

The run will be labeled as cancelled, so failure function is not triggered in this case, and no dlq entries generated.
## 
​
Error handling and retries
  * `context.run` automatically retries on failures. Default is 3 retries with exponential backoff.
  * `context.call` doesn’t retry by default. If you wish to add retry, you can use `retries` option.
  * Both `context.call` and `context.invoke` support the `retryDelay` parameter to customize the delay between retry attempts. You can use mathematical expressions with functions like `pow`, `sqrt`, `min`, `max`, etc., and the variable `retried` (current retry attempt count).
  * `WorkflowNonRetryableError` allows you to fail workflow on will without going into retry cycle. The run will be labeled as failed, triggering the failure function and creating a dlq entry:


Copy
Ask AI
```
export const { POST } = serve<{ topic: string }>(async (context) => {
  const payload = context.requestPayload

  const result = await context.run("check if failed", () => { ... });

  if (result.fail) {
    throw new WorkflowNonRetryableError("error message")  // fail the workflow run
  }
})

```

  * Future releases will allow more configuration of retry behavior.


## 
​
Limitations and Plan-Specific-Features
  * Sleep durations and HTTP timeouts vary based on your QStash plan.
  * See your plan’s “Max Delay” and “Max HTTP Connection Timeout” for specific limits.


Was this page helpful?
YesNo
Suggest editsRaise issue
Create a workflowWorkflow Client
Assistant
Responses are generated using AI and may contain mistakes.
