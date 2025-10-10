Skip to main content
On this page
## 
​
Overview
Upstash Workflow lets you write **durable, reliable and performant serverless functions**. Get delivery guarantees, automatic retries on failure, scheduling and more without managing any infrastructure.
## 
​
Key Features
## Failure Resilience
If your platform experiences a temporary outage, your workflow can pick up right where it left off, ensuring stability even in unstable environments.
## Long-Running Executions
Run long-running REST endpoints, such as complex AI models or video processing tools, even on serverless platforms with strict time limits.
## Events with Wait/Notify Mechanism
Create workflows that wait for external events before proceeding. Ideal for user confirmations and asynchronous notifications.
## Scheduled Jobs
Run jobs at regular intervals with support for cron expressions. Perfect for recurring tasks like reminders, reports, or newsletters.
## Parallel Runs
Start independent tasks in parallel and wait for them to finish simultaneously, reducing latency.
## Long Delays
Need your code to “sleep” for days, weeks, or even months? Supports long delays beyond serverless time limits.
## Delivery Guarantees
Ensures at-least-once delivery. Failed requests are logged in a Dead Letter Queue to prevent data loss.
## Flow Control
Prevent overwhelming your app or external services by configuring rate per second or parallelism limits.
## Observability
Monitor workflow steps with insights. Filter events to track successes, failures, retries, and stalls.
## 
​
Quickstarts
Workflow supports Next.js, Cloudflare Workers and many more frameworks in TypeScript and Python.
## Next.js
Build a Next.js application with QStash Workflow
## Cloudflare Workers
Use and deploy Upstash Workflow on Cloudflare Workers
## Next.js & FastAPI
Use Upstash Workflow for Python with Next.js and FastAPI
## 
​
Example Use Cases
Here are some example real world use-cases for Upstash Workflow:
## Agents
Use LLM Agents equipped with custom tools to achieve tasks
## AI Data Processing
Download a large dataset without timeouts, process the data in chunks and generate a report.
## Waiting For Events
Control workflow execution with events, log event data and send emails
## Authorization Webhook
Start a workflow from a webhook. Handle user creation, trial management, email reminders and notifications.
## Customer Onboarding
Register a new user, send welcome emails, and periodically check and respond to the user’s activity state with emails.
## E-Commerce Order Fulfillment
Receive an order request, verify the stock, process the payment, and handle order dispatch and customer notifications.
## Image Processing
Manage uploading images to the data store. Apply filters and resize the images to different resolutions in parallel.
## Retry Payments
Retry payments with a day of delay, send emails, and suspend account if payment fails after the retries.
## 
​
How it works
Upstash Workflow builds on the principle of steps. Instead of defining a single, complex piece of business logic, workflows contain multiple individual steps. In case of an error, a failed step is retried individually without needing to re-run any previous steps. Instead of the entire business logic, _each step_ can take up your serverless function execution duration, and many more benefits.
## 
​
Code example
Let’s see a practical implementation of Upstash Workflow using customer onboarding as an example. See our Next.js Quickstart or FastAPI Quickstart for a complete guide.
api/workflow/route.ts
main.py
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";

// Type-safety for starting our workflow
interface InitialData {
  userId: string
  email: string
  name: string
}

export const { POST } = serve<InitialData>(async (context) => {
  const { userId, email, name } = context.requestPayload;

  // Step 1: Send welcome email
  await context.run("send-welcome-email", async () => {
    await sendEmail(email, "Welcome to our service!");
  });

  // Step 2: Wait for 3 days (in seconds)
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);

  // Step 3: AI-generate personalized follow-up message
  const { body: aiResponse } = await context.api.openai.call(
    "generate-personalized-message",
    {
      token: "<OPENAI_API_KEY>",
      operation: "chat.completions.create",
      body: {
        model: "gpt-3.5-turbo",
        messages: [
          { role: "system", content: "You are an assistant creating personalized follow-up messages." },
          { role: "user", content: `Create a short, friendly follow-up message for ${name} who joined our service 3 days ago.` }
        ]
      },
    }
  );

  const personalizedMessage = aiResponse.choices[0].message.content;

  // Step 4: Send personalized follow-up email
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, personalizedMessage);
  });
});

```

Any HTTP request using `context.call`, like the AI-generation above, does not count towards your function’s execution time and does not increase your serverless bill. It can also run for up to 2 hours, completely bypassing any platform-specific function timeouts.
Once your endpoint is ready, you can trigger the workflow via our SDKs or using plain REST. See here for details.
TypeScript SDK
Python SDK
REST
Copy
Ask AI
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: "hello there!",         // Optional body
  headers: { ... },             // Optional headers
  workflowRunId: "my-workflow", // Optional workflow run ID
  retries: 3                    // Optional retries for the initial request
});

```

The above example should give you a rough idea of how a workflow looks in code. For step-by-step instructions on setting up your first workflow with images along the way, see our Next.js Quickstart or FastAPI Quickstart.
* * *
Here are more details about what the `context` object does:
  * context.run
  * context.sleep
  * context.sleepUntil
  * context.call
  * context.waitForEvent
  * context.notify
  * context.cancel

See caveats for more complex API usage and best-practices when using Upstash Workflow.
* * *
Guides on common workflow topics:
  * Cancel a running workflow
  * Wait for External Events
  * Handle failed workflow runs
  * Monitor active workflows in real-time
  * Schedule repeated workflow runs
  * Secure a workflow endpoint
  * Handle workflow route code changes
  * Develop your workflows locally
  * Pricing

If you’re curious about the behind-the-scenes about how we ensure separate step execution or prevent serverless timeouts, we wrote about it here! :) Here is our Upstash Workflow roadmap to see what we planned for the future.
Was this page helpful?
YesNo
Suggest editsRaise issue
Supported Platforms
CtrlI
Assistant
Responses are generated using AI and may contain mistakes.
