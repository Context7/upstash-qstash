```
# Upstash QStash Documentation

Upstash QStash is a serverless messaging and scheduling solution designed for modern cloud applications. It acts as a reliable middleman between your application and target APIs, providing guaranteed message delivery, automatic retries, and scheduling capabilities without requiring infrastructure management. QStash eliminates the complexity of building reliable distributed systems by handling message queuing, retry logic, and failure recovery automatically.

The platform offers both a simple REST API and SDKs for TypeScript and Python, making it easy to integrate into existing workflows. Key features include FIFO queues for ordered delivery, scheduled messages using cron expressions, dead letter queues for failed messages, callbacks for long-running operations, and flow control to prevent endpoint overload. QStash also includes Upstash Workflow, a higher-level SDK that simplifies building complex, durable serverless functions with step-based execution and automatic failure recovery.

## Publishing Messages

### Publish a message to an endpoint

Send a JSON message to a destination URL with automatic retries and delivery guarantees.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://example.com",
    body={
        "hello": "world",
    },
)
```

### Publish with delay and custom headers

Delay message delivery and include custom headers that will be forwarded to your endpoint.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 5m" \
    -H "Upstash-Forward-My-Header: my-value" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  delay: 300, // 5 minutes in seconds
  headers: {
    "My-Header": "my-value",
  },
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://example.com",
    body={
        "hello": "world",
    },
    delay="5m",
    headers={
        "My-Header": "my-value",
    },
)
```

### Configure retries with custom backoff

Set maximum retry attempts and custom retry delay expressions using mathematical functions.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  retries: 3,
  retryDelay: "pow(2, retried) * 1000", // Exponential backoff: 1s, 2s, 4s, 8s
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://example.com",
    body={
        "hello": "world",
    },
    retries=3,
    retry_delay="pow(2, retried) * 1000",
)
```

## Scheduling

### Create a recurring schedule with cron

Schedule messages to be sent periodically using cron expressions.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: 0 0 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "0 0 * * *", // Every day at midnight UTC
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="0 0 * * *",
)
```

### Schedule with timezone support

Create schedules that run in specific timezones using CRON_TZ prefix.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: CRON_TZ=America/New_York 0 4 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "CRON_TZ=America/New_York 0 4 * * *", // 4 AM New York time
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="CRON_TZ=America/New_York 0 4 * * *",
)
```

### List and manage schedules

Retrieve all active schedules and their configurations.

```bash
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const schedules = await client.schedules.list();

for (const schedule of schedules) {
  console.log(`Schedule ${schedule.scheduleId}: ${schedule.cron}`);
}
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
schedules = client.schedule.list()

for schedule in schedules:
    print(f"Schedule {schedule['scheduleId']}: {schedule['cron']}")
```

## Queues (FIFO Ordering)

### Enqueue messages for ordered delivery

Send messages to a queue for guaranteed FIFO (first-in-first-out) delivery.

```bash
curl -XPOST -H 'Authorization: Bearer <QSTASH_TOKEN>' \
            -H "Content-type: application/json" \
            'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' \
            -d '{"message":"Hello, World!"}'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const queue = client.queue({
  queueName: "my-queue"
});

await queue.enqueueJSON({
  url: "https://example.com",
  body: {
    "Hello": "World"
  }
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.enqueue_json(
    queue="my-queue",
    url="https://example.com",
    body={
        "Hello": "World",
    },
)
```

### Configure queue parallelism

Set controlled parallelism limits for queue processing to balance throughput and endpoint capacity.

```bash
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue",
    "parallelism": 5
  }'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const queue = client.queue({
  queueName: "my-queue"
});

await queue.upsert({
  parallelism: 5,
});

// Check queue configuration
const config = await queue.get();
console.log(`Queue parallelism: ${config.parallelism}`);
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.upsert("my-queue", parallelism=5)

# Check queue configuration
config = client.queue.get("my-queue")
print(f"Queue parallelism: {config['parallelism']}")
```

## Callbacks

### Add success and failure callbacks

Receive responses from long-running endpoints without blocking your serverless function.

```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api.example.com \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: https://my-app.example.com/callback' \
  -H 'Upstash-Failure-Callback: https://my-app.example.com/failure' \
  -d '{ "hello": "world" }'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api.example.com",
  body: { hello: "world" },
  callback: "https://my-app.example.com/callback",
  failureCallback: "https://my-app.example.com/failure",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api.example.com",
    body={
        "hello": "world",
    },
    callback="https://my-app.example.com/callback",
    failure_callback="https://my-app.example.com/failure",
)
```

### Handle callback responses in Next.js

Process callback payloads with signature verification to ensure authenticity.

```javascript
// pages/api/callback.js
import { verifySignature } from "@upstash/qstash/nextjs";

function handler(req, res) {
  // Callback body structure:
  // {
  //   status: 200,
  //   header: { "key": ["value"] },
  //   body: "YmFzZTY0IGVuY29kZWQgcm9keQ==", // base64 encoded
  //   retried: 2,
  //   maxRetries: 3,
  //   sourceMessageId: "msg_xxx",
  //   url: "http://myurl.com",
  //   method: "GET",
  //   sourceHeader: { "key": "value" },
  //   sourceBody: "YmFzZTY0kZWQgcm9keQ==",
  //   createdAt: "1701198447054"
  // }

  // Decode base64 response body
  const decoded = atob(req.body.body);
  console.log("Response from target:", decoded);

  // Process the response
  console.log(`Message ${req.body.sourceMessageId} completed`);
  console.log(`Retried ${req.body.retried} times`);

  return res.status(200).end();
}

export default verifySignature(handler);

export const config = {
  api: {
    bodyParser: false,
  },
};
```

## Batch Operations

### Batch publish to multiple destinations

Send multiple messages in a single request to different URLs or URL groups.

```bash
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '[
      {
        "destination": "https://example.com/destination1",
        "headers": {
          "Upstash-Delay": "5s",
          "Upstash-Forward-Hello": "123456"
        },
        "body": "Hello World"
      },
      {
        "destination": "https://example.com/destination2",
        "headers": {
          "Upstash-Delay": "7s"
        }
      }
    ]'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.batchJSON([
  {
    url: "https://example.com/destination1",
    delay: 5,
    body: "Hello World",
    headers: {
      hello: "123456",
    },
  },
  {
    url: "https://example.com/destination2",
    delay: 7,
    body: {
      Some: "Data",
    },
  },
]);

// Response structure:
// [
//   { "messageId": "msg_..." },
//   { "messageId": "msg_..." }
// ]
console.log(`Sent ${res.length} messages`);
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
response = client.message.batch_json(
    [
        {
            "url": "https://example.com/destination1",
            "delay": "5s",
            "body": {"hello": "world"},
            "headers": {"random": "header"},
        },
        {
            "url": "https://example.com/destination2",
            "delay": "1m",
            "body": {"more": "data"},
        },
    ]
)

for msg_response in response:
    print(f"Message ID: {msg_response['messageId']}")
```

### Batch enqueue to queues

Enqueue multiple messages to different queues in a single batch request.

```bash
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '[
      {
        "queue": "my-queue",
        "destination": "https://example.com/destination1"
      },
      {
        "queue": "my-second-queue",
        "destination": "https://example.com/destination2"
      }
    ]'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const res = await client.batchJSON([
  {
    queueName: "my-queue",
    url: "https://example.com/destination1",
  },
  {
    queueName: "my-second-queue",
    url: "https://example.com/destination2",
  },
]);
```

```python
from qstash import QStash
from qstash.message import BatchRequest

client = QStash("<QSTASH_TOKEN>")

messages = [
    BatchRequest(
        queue="my-queue",
        url="https://example.com/endpoint1",
        body="message 1",
        retries=3
    ),
    BatchRequest(
        queue="my-second-queue",
        url="https://example.com/endpoint2",
        body="message 2",
        retries=3
    ),
]

client.message.batch(messages)
```

## Monitoring and Logs

### Get message logs with filtering

Retrieve event logs for published messages to track delivery status.

```bash
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = await client.logs();

for (const log of logs.events) {
  console.log(`${log.time}: ${log.state} - Message ${log.messageId}`);
  console.log(`  URL: ${log.url}`);
  console.log(`  Status: ${log.responseStatus}`);
}
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
logs = client.event.list()

for event in logs:
    print(f"{event['time']}: {event['state']} - Message {event['messageId']}")
    print(f"  URL: {event['url']}")
```

### Get message details

Retrieve details for a specific message by its ID (only available while message is being processed).

```bash
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

try {
  const message = await client.messages.get("msg_123");
  console.log(`Message ${message.messageId} to ${message.url}`);
  console.log(`Created: ${new Date(message.createdAt).toISOString()}`);
  console.log(`Body: ${message.body}`);
} catch (error) {
  console.log("Message already delivered or not found");
}
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

try:
    message = client.message.get("msg_123")
    print(f"Message {message['messageId']} to {message['url']}")
    print(f"Body: {message['body']}")
except Exception as e:
    print("Message already delivered or not found")
```

## Upstash Workflow

### Create a workflow with steps

Build durable workflows with step-based execution that automatically recovers from failures.

```typescript
// api/workflow/route.ts (Next.js)
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";

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

  // Step 2: Wait for 3 days
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);

  // Step 3: AI-generate personalized message
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

```python
# main.py (FastAPI)
from upstash_workflow import Workflow, WorkflowContext
from fastapi import FastAPI

app = FastAPI()
workflow = Workflow(qstash_token="<QSTASH_TOKEN>")

@app.post("/workflow")
async def workflow_endpoint(request: dict):
    async def workflow_logic(context: WorkflowContext):
        user_id = request["userId"]
        email = request["email"]
        name = request["name"]

        # Step 1: Send welcome email
        await context.run("send-welcome-email", lambda: send_email(email, "Welcome!"))

        # Step 2: Wait for 3 days
        await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3)

        # Step 3: Send follow-up
        await context.run("send-follow-up", lambda: send_email(email, "How are you?"))

    return await workflow.execute(workflow_logic)
```

### Trigger a workflow

Start a workflow execution using the Workflow client.

```typescript
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const { workflowRunId } = await client.trigger({
  url: "https://my-app.example.com/api/workflow",
  body: {
    userId: "user_123",
    email: "user@example.com",
    name: "John Doe"
  },
  headers: {
    "Content-Type": "application/json"
  },
  workflowRunId: "onboarding-user-123", // Optional custom ID
  retries: 3 // Retries for the initial request
});

console.log(`Workflow started with ID: ${workflowRunId}`);
```

```python
from upstash_workflow import Client

client = Client(token="<QSTASH_TOKEN>")

workflow_run = client.trigger(
    url="https://my-app.example.com/api/workflow",
    body={
        "userId": "user_123",
        "email": "user@example.com",
        "name": "John Doe"
    },
    workflow_run_id="onboarding-user-123",
    retries=3
)

print(f"Workflow started with ID: {workflow_run['workflowRunId']}")
```

```bash
curl -XPOST https://qstash.upstash.io/v2/publish/https://my-app.example.com/api/workflow \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Workflow-RunId: onboarding-user-123" \
  -H "Upstash-Retries: 3" \
  -d '{
    "userId": "user_123",
    "email": "user@example.com",
    "name": "John Doe"
  }'
```

## Client Configuration

### Initialize client with retry configuration

Configure the QStash client with custom retry behavior for API requests.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
  retry: {
    retries: 3,
    backoff: retry_count => 2 ** retry_count * 20, // Custom exponential backoff
  },
});

// Disable retries completely
const clientNoRetry = new Client({
  token: "<QSTASH_TOKEN>",
  retry: false,
});
```

```python
from qstash import QStash

# Python SDK handles retries internally
client = QStash("<QSTASH_TOKEN>")

# Both sync and async versions available
from qstash import AsyncQStash

async_client = AsyncQStash("<QSTASH_TOKEN>")
```

## Summary

Upstash QStash provides a comprehensive serverless messaging platform that handles the complexity of distributed systems. The primary use cases include background job processing for long-running tasks that exceed serverless function timeouts, scheduled tasks using cron expressions for recurring operations like reports or cleanup jobs, and reliable message delivery with automatic retries and dead letter queues for failed messages. Developers can implement FIFO queues for ordered message processing, use callbacks to handle responses from asynchronous operations, and leverage batch operations to efficiently send multiple messages in a single request.

The platform integrates seamlessly with modern serverless frameworks like Next.js, Cloudflare Workers, and Vercel, providing SDKs in TypeScript and Python alongside a RESTful API. Upstash Workflow extends QStash's capabilities by offering a higher-level abstraction for building complex, durable workflows with step-based execution, automatic failure recovery, and support for long delays beyond typical serverless limits. Whether building simple background jobs, complex multi-step workflows, or scheduled tasks, QStash eliminates infrastructure management while ensuring message delivery guarantees and providing comprehensive observability through logs and monitoring.

```

