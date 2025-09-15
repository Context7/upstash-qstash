On this page
Use the `serve` method to define an endpoint that serves a workflow. It provides a context object that you use to create all of your workflow’s steps. For example, in a Next.js or FastAPI app:
TypeScript
Python
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(async (context) => {
  const result = await context.run("step-1", async () => {
    // define a piece of business logic as step 1
  });

  await context.run("step-2", async () => {
    // define another piece of business logic as step 2
  });
});

```

## 
​
Platform support
Besides Next.js and FastAPI, the `serve` method supports multiple frameworks and platforms. See all supported platforms here.
## 
​
Options
### 
​
`failureUrl`
Use the `failureUrl` option to specify a URL your workflow will call if it exhausted all retries and fails.
Typescript
Python
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    failureUrl: "https://<YOUR-FAILURE-ENDPOINT>/..."
  }
);

```

If you add a `failureUrl` and use `client.trigger` to start your workflow, you should pass `failureUrl` in `client.trigger` too.
If specified, this URL will be called with the failure callback payload, and the error message will be included in the `body` field. The default value is `undefined`, meaning no failure URL is called.
### 
​
`failureFunction`
Use the `failureFunction` to define a function that’s executed when your workflow exhausts all its retries and fails.
TypeScript
Python
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    failureFunction: async ({
      context,      // context during failure
      failStatus,   // failure status
      failResponse, // failure message
      failHeaders   // failure headers
    }) => {
      // handle the failure
    }
  }
);

```

If you add a `failureFunction` and use `client.trigger` to start your workflow, you should pass `useFailureFunction: true` in `client.trigger`.
If both `failureUrl` and `failureFunction` are provided, the failure function takes precedence and the value of `failureUrl` is ignored. By default, `failureFunction` is `undefined`, meaning that no function is executed on failure.
### 
​
`retries`
To specify the number of times QStash will call the workflow endpoint in case of errors, you can use the `verbose` parameter. The default value is 3.
TypeScript
Python
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    retries: 3
  }
);

```

### 
​
`retryDelay`
To specify the delay between retries, you can use the `retryDelay` option.
TypeScript
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    retryDelay: "(retried + 1) * 1000" // delay in milliseconds
  }
);

```

You can refer to the QStash retry delay documentation for more details about retry delay.
### 
​
`flowControl`
To control the rate of requests to your endpoint, use the `rate` and `period` options. To limit the maximum number of concurrent requests, use the `parallelism` option within the `flowControl` settings. See the flow control section for more details.
TypeScript
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    flowControl: { key: "aFlowControlKey",  rate: 10, parallelism: 3 }
  }
);

```

You can also pass only `rate` or `parallelism` if you only need one of the two. By default, there is no rate per second or parallelism limit.
### 
​
`verbose`
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
To gain insights into how the workflow operates, you can enable verbose mode:
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    verbose: true
  }
);

```

Each log entry has the following structure:
Copy
Ask AI
```
{
  timestamp: number,
  workflowRunId: string,
  logLevel: string,
  eventType: string,
  details: unknown,
}

```

The `eventType` can be:
  * `ENDPOINT_START` each time the workflow endpoint is called
  * `RUN_SINGLE` or `RUN_PARALLEL` when step(s) are executed
  * `SUBMIT_STEP` when a single step is executed
  * `SUBMIT_FIRST_INVOCATION` when a new workflow run starts
  * `SUBMIT_CLEANUP` when a workflow run finishes
  * `SUBMIT_THIRD_PARTY_RESULT` when a third-party call result is received (see `context.call`)

Verbose mode is disabled by default.
### 
​
`initialPayloadParser`
When calling the workflow endpoint to start a workflow run, your initial request’s payload is expected to be either empty, a string, or JSON. If your payload differs, you can process it as needed using the `initialPayloadParser` option:
TypeScript
Python
Copy
Ask AI
```
type InitialPayload = {
  foo: string;
  bar: number;
};

// 👇 1: provide initial payload type
export const { POST } = serve<InitialPayload>(
  async (context) => {
    // 👇 3: parsing result is available as requestPayload
    const payload: InitialPayload = context.requestPayload;
  },
  {
    // 👇 2: custom parsing for initial payload
    initialPayloadParser: (initialPayload) => {
      const payload: InitialPayload = parsePayload(initialPayload);
      return payload;
    },
  }
);

```

### 
​
`url`
Since a workflow run involves multiple calls to the workflow endpoint, the `serve` method needs to know where your endpoint is hosted. Typically, your workflow infers this using the `request.url` field. However, if you use a proxy or a local tunnel for development, you may want to override the URL inferred from `request.url`:
TypeScript
Python
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    url: "https://<YOUR-DEPLOYED-APP>.com/api/workflow"
  }
);

```

By default, `url` is `undefined`, and the URL is inferred from `request.url`.
### 
​
`baseUrl`
An alternative to the `url` option is the `baseUrl` option. While `url` replaces the entire URL inferred from `request.url`, `baseUrl` only changes the base of the URL:
TypeScript
Python
Copy
Ask AI
```
export const { POST } = serve<string>(
  async (context) => {
    ...
  },
  // options:
  {
    baseUrl: "<LOCAL-TUNNEL-PUBLIC-URL>"
  }
);

```

The default value of `baseUrl` is `undefined`. If you have multiple endpoints and you don’t want to set `baseUrl` in every single one, you can set the `UPSTASH_WORKFLOW_URL` environment variable to apply `baseUrl` across your entire application. Setting this environment variable is especially useful during local development. In production, `baseUrl` or `UPSTASH_WORKFLOW_URL` are not necessary.
* * *
## 
​
Further options
The following options can be considered convenience methods. They are intended to support edge cases or testing pipelines and are **not required for regular use**.
### 
​
`qstashClient`
The `qstashClient` option allows you to pass a QStash Client explicitly. This can be helpful when using multiple QStash clients in the same project with different environment variables.
TypeScript
Python
Copy
Ask AI
```
import { Client } from "@upstash/qstash";
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(
  async (context) => { ... },
  {
    qstashClient: new Client({ token: process.env.QSTASH_TOKEN })
  }
);

```

By default, a `qstashClient` is initialized as:
TypeScript
Python
Copy
Ask AI
```
new Client({
  baseUrl: process.env.QSTASH_URL!,
  token: process.env.QSTASH_TOKEN!,
});

```

### 
​
`receiver`
You can pass a QStash Receiver to verify that **every** request the endpoint receives comes from QStash, preventing anyone from triggering your workflow.
TypeScript
Python
Copy
Ask AI
```
import { Receiver } from "@upstash/qstash";
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<string>(
  async (context) => { ... },
  {
    receiver: new Receiver({
      // 👇 grab these variables from your QStash dashboard
      currentSigningKey: process.env.QSTASH_CURRENT_SIGNING_KEY!,
      nextSigningKey: process.env.QSTASH_NEXT_SIGNING_KEY!,
    })
  }
);

```

The default receiver is automatically used if the environment variables `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY` are set. If you want to turn off the Receiver, remove these environment variables or pass `receiver: undefined` in the options. Note that this will skip any verification that requests are coming from QStash and allow anyone to start your workflow.
### 
​
`env`
By default, the SDK uses `process.env` to initialize the QStash client and the receiver (if the two environment variables are set). If `process.env` doesn’t exist, the SDK won’t be able to access the environment variables. In this case, you can either pass `qstashClient` and `receiver` options or use the `env` option. If you pass `env`, this `env` will be used instead of `process.env`:
TypeScript
Python
Copy
Ask AI
```
import { Receiver } from "@upstash/qstash";
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<string>(
  async (context) => {
    // the env option will be available in the env field of the context:
    const env = context.env;
  },
  {
    receiver: new Receiver({
      // 👇 grab these variables from your QStash dashboard
      currentSigningKey: process.env.QSTASH_CURRENT_SIGNING_KEY!,
      nextSigningKey: process.env.QSTASH_NEXT_SIGNING_KEY!,
    }),
  }
);

```

### 
​
`disableTelemetry`
This feature is not yet available in workflow-py. See our Roadmap for feature parity plans and Changelog for updates.
By default, Workflow SDK sends telemetry about SDK version, framework or runtime. You can set `disableTelemetry` to `false` if you wish to disable this behavior.
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<string>(
  async (context) => { ... },
  {
    disableTelemetry: true
  }
);

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Next.js & FlaskWorkflow Context
Assistant
Responses are generated using AI and may contain mistakes.
