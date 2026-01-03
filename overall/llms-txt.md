```
### Install and Run Next.js App with QStash

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This snippet covers the initial setup of a Next.js project, including installation of the QStash package and running the development server. It requires Node.js and npm to be installed.

```bash
npx create-next-app@latest qstash-bg-job
cd qstash-bg-job
npm install @upstash/qstash
npm run dev
```

--------------------------------

### Project Setup with C3 (npm)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

This command uses npm to initiate a new Cloudflare worker project using the create-cloudflare-cli (C3). It guides the user through project configuration, including directory, template, and language selection. C3 also installs Wrangler for testing and deployment.

```shell
npm create cloudflare@latest
```

--------------------------------

### GET /v2/schedules - List All Schedules

Source: https://upstash.com/docs/qstash/overall/apiexamples

Retrieve a list of all scheduled messages.

```APIDOC
## GET /v2/schedules

### Description
Retrieve a list of all scheduled messages.

### Method
GET

### Endpoint
`https://qstash.upstash.io/v2/schedules`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example (cURL)
```shell
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer XXX"
```

### Request Example (TypeScript SDK)
```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
const scheds = await client.schedules.list();
```

### Response
#### Success Response (200)
- **schedules** (array) - An array of schedule objects.

#### Response Example
```json
{
  "schedules": [
    {
      "id": "sch_abc123",
      "cron": "* * * * *",
      "url": "https://example.com",
      "createdAt": 1678886400
    }
  ]
}
```
```

--------------------------------

### Install Vercel CLI for deployment

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This bash command installs the Vercel Command Line Interface (CLI) globally on your system. The Vercel CLI is used for deploying projects to Vercel, a platform for frontend developers.

```bash
npm install -g vercel
```

--------------------------------

### Project Setup with C3 (yarn)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

This command uses yarn to initiate a new Cloudflare worker project using the create-cloudflare-cli (C3). It guides the user through project configuration, including directory, template, and language selection. C3 also installs Wrangler for testing and deployment.

```shell
yarn create cloudflare@latest
```

--------------------------------

### GET /v2/logs - Get Message Logs

Source: https://upstash.com/docs/qstash/overall/apiexamples

Retrieve logs for all published messages. Filtering options may be available.

```APIDOC
## GET /v2/logs

### Description
Retrieve logs for all published messages. Filtering options may be available.

### Method
GET

### Endpoint
`https://qstash.upstash.io/v2/logs`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example (cURL)
```shell
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

### Request Example (TypeScript SDK)
```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = await client.logs()
```

### Response
#### Success Response (200)
- **logs** (array) - An array of log objects, each containing message details and status.

#### Response Example
```json
{
  "logs": [
    {
      "messageId": "msg_abc123",
      "url": "https://example.com",
      "status": "delivered",
      "timestamp": 1678886400
    }
  ]
}
```
```

--------------------------------

### Initialize AWS CDK Project and Install Dependencies

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This snippet demonstrates the bash commands to create a new AWS CDK project using TypeScript, install the Upstash QStash SDK, and set up the basic file structure for a Lambda function.

```bash
mkdir my-app
cd my-app
cdk init app -l typescript
npm i esbuild @upstash/qstash
mkdir lambda
touch lambda/index.ts
```

--------------------------------

### POST /v2/publish/{url}

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a simple JSON message to a specified endpoint.

```APIDOC
## POST /v2/publish/{url}

### Description
Publish a simple JSON message to a specified endpoint.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<url>`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to publish the message to.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Publish Messages to FIFO Queue with QStash

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish messages to a queue for First-In, First-Out (FIFO) processing. This example demonstrates how to enqueue a JSON message using cURL, the TypeScript SDK, or the Python SDK. Replace 'XXX' with your token and 'my-queue' with your queue name.

```shell
curl -XPOST -H 'Authorization: Bearer XXX' \
                -H "Content-type: application/json" \
                'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' 
                -d '{"message":"Hello, World!"}'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queue = client.queue({
  queueName: "my-queue"
})

await queue.enqueueJSON({
  url: "https://example.com",
  body: {
    "Hello": "World"
  }
})
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
# Async version is also available
```

--------------------------------

### POST /v2/publish/{url} with Custom Headers

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a message to an endpoint and include custom headers in the request.

```APIDOC
## POST /v2/publish/{url} with Custom Headers

### Description
Publish a message to an endpoint and include custom headers in the request.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<url>`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to publish the message to.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

#### Headers
- **Upstash-Forward-{Header-Name}** (string) - Optional - Custom header to forward to the target endpoint. Replace `{Header-Name}` with the desired header name.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Install Upstash Packages with npm

Source: https://upstash.com/docs/qstash/recipes/periodic-data-updates

Installs the required Upstash QStash and Redis packages for a Next.js project. These packages enable integration with QStash for scheduled tasks and Redis for data storage.

```bash
npm install @upstash/qstash @upstash/redis
```

--------------------------------

### Publish Messages in Batch with QStash

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish multiple messages in a single request using QStash's batch functionality. This example shows how to send a batch of messages via cURL, TypeScript SDK, or Python SDK. Ensure you replace 'XXX' with your authorization token.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "destination": "https://example.com/destination1"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.batchJSON([
  {
    url: "https://example.com/destination1",
  },
  {
    url: "https://example.com/destination2",
  },
]);
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.batch_json(
    [
        {
            "url": "https://example.com/destination1",
        },
        {
            "url": "https://example.com/destination2",
        },
    ]
)
# Async version is also available
```

--------------------------------

### Deploy Python App to Vercel CLI

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Commands to install the Vercel CLI globally and then initiate the deployment process for the Python application. This assumes the application is set up for deployment in the current directory.

```bash
npm install -g vercel
vercel
```

--------------------------------

### Deploy Application with Flyctl

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Deploys the application to the Fly.io platform. This command assumes the Fly.io CLI is installed and configured.

```bash
flyctl deploy
```

--------------------------------

### POST /v2/publish/{url} with Delay

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a message to an endpoint with a specified delay before it is sent.

```APIDOC
## POST /v2/publish/{url} with Delay

### Description
Publish a message to an endpoint with a specified delay before it is sent.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<url>`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to publish the message to.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

#### Headers
- **Upstash-Delay** (string) - Optional - The delay duration (e.g., "5m", "1h").

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Deploy project using Vercel CLI

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This bash command initiates the deployment process for your project using the Vercel CLI. It guides you through the deployment steps, such as selecting a scope and project settings, and ultimately deploys your application to Vercel.

```bash
vercel
```

--------------------------------

### Get QStash Message Logs

Source: https://upstash.com/docs/qstash/overall/apiexamples

Retrieve logs for published messages, with optional filtering capabilities. This allows monitoring message delivery and processing.

```shell
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = await client.logs()
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.event.list()
# Async version is also available
```

--------------------------------

### POST /v2/enqueue/{queue_name}/{url}

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publishes messages to a specified FIFO queue. Messages are processed in the order they are enqueued.

```APIDOC
## POST /v2/enqueue/{queue_name}/{url}

### Description
Enqueues a message into a specified FIFO queue for ordered processing. If the queue does not exist, it may be created.

### Method
POST

### Endpoint
`/v2/enqueue/<queue_name>/<url>`

### Parameters
#### Path Parameters
- **queue_name** (string) - Required - The name of the FIFO queue.
- **url** (string) - Required - The URL to send the message to.

#### Query Parameters
None

#### Request Body
- **message** (object) - Required - The JSON payload of the message to be sent.

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Should be set to "application/json".

### Request Example
```json
{
  "message": "Hello, World!"
}
```

### Response
#### Success Response (200)
(No specific response body detailed in the provided text, but typically a confirmation of message enqueuing)

#### Response Example
(Not provided in the source text)
```

--------------------------------

### Install Upstash Redis Package

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Installs the necessary Python package 'upstash-redis' to interact with Upstash Redis databases. This package provides the client for database operations.

```bash
pip install upstash-redis
```

--------------------------------

### POST /v2/publish/{urlGroup}

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a JSON message to multiple endpoints defined in a URL group using a fan-out pattern.

```APIDOC
## POST /v2/publish/{urlGroup}

### Description
Publish a JSON message to multiple endpoints defined in a URL group using a fan-out pattern.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<urlGroup>`

### Parameters
#### Path Parameters
- **urlGroup** (string) - Required - The name of the URL group to publish the message to.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### POST /v2/batch

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publishes multiple messages in a single request. This is useful for efficiency when sending many messages.

```APIDOC
## POST /v2/batch

### Description
Allows publishing multiple messages in a single API request, improving efficiency for bulk operations.

### Method
POST

### Endpoint
`/v2/batch`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **messages** (array of objects) - Required - An array where each object represents a message with at least a `destination` field.
  - **destination** (string) - Required - The URL for the message.

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Should be set to "application/json".

### Request Example
```json
[
  {
    "destination": "https://example.com/destination1"
  },
  {
    "destination": "https://example.com/destination2"
  }
]
```

### Response
#### Success Response (200)
(No specific response body detailed in the provided text, but typically a confirmation of batch processing)

#### Response Example
(Not provided in the source text)
```

--------------------------------

### POST /v2/schedules/{url}

Source: https://upstash.com/docs/qstash/overall/apiexamples

Schedules a task to run once a day at a specified cron time. The task will be sent to the provided URL.

```APIDOC
## POST /v2/schedules/{url}

### Description
Schedules a task to run at a specific time using cron syntax. The task will be sent to the specified URL.

### Method
POST

### Endpoint
`/v2/schedules/<url>`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to send the scheduled task to.

#### Query Parameters
None

#### Request Body
None (headers are used for configuration)

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Cron** (string) - Required - Cron expression defining the schedule (e.g., "0 0 * * *").
- **Content-type** (string) - Required - Should be set to "application/json".

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
(No specific response body detailed in the provided text, but typically a confirmation of schedule creation)

#### Response Example
(Not provided in the source text)
```

--------------------------------

### POST /v2/publish/:url - Publish Message with Callback URLs

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a JSON message to a specified URL and configure callback URLs for success and failure notifications.

```APIDOC
## POST /v2/publish/:url

### Description
Publish a JSON message to a specified URL and configure callback URLs for success and failure notifications.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<url>`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Callback** (string) - Optional - URL to send the response to upon successful delivery.
- **Upstash-Failure-Callback** (string) - Optional - URL to send the response to upon delivery failure.
- **Content-type** (string) - Required - `application/json`.

### Request Body
- **body** (object) - Required - The JSON payload to send.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Request Example (TypeScript SDK)
```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  callback: "https://example.com/callback",
  failureCallback: "https://example.com/failure",
});
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.
- **delay** (integer) - The delay in seconds before the message will be delivered.

#### Response Example
```json
{
  "messageId": "msg_abc123",
  "delay": 0
}
```
```

--------------------------------

### Deploy Golang App on fly.io: Launch and Configure

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Launches a new application on fly.io, automatically detecting the Go environment. This process generates a `fly.toml` configuration file and prompts for app name, region, and other settings. It advises against immediate deployment, allowing for environment variable setup.

```bash
$ flyctl launch
Creating app in /Users/andreasthomas/github/upstash/qstash-examples/fly.io/go
Scanning source code
Detected a Go app
Using the following build configuration:
        Builder: paketobuildpacks/builder:base
        Buildpacks: gcr.io/paketo-buildpacks/go
? App Name (leave blank to use an auto-generated name):
Automatically selected personal organization: Andreas Thomas
? Select region: fra (Frankfurt, Germany)
Created app winer-cherry-9545 in organization personal
Wrote config file fly.toml
? Would you like to setup a Postgresql database now? No
? Would you like to deploy now? No
Your app is ready. Deploy with `flyctl deploy`
```

--------------------------------

### Automate QStash Job Creation with Python SDK

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

This snippet shows how to use the QStash Python SDK to programmatically create a scheduled job. It requires a QStash token and specifies the destination URL and cron schedule for the job. Ensure you have the 'qstash' library installed.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://YOUR_URL.vercel.app/api",
    cron="0 12 * * *",
)
```

--------------------------------

### QStash JWT Header Example

Source: https://upstash.com/docs/qstash/features/security

An example of the JWT header used in the 'Upstash-Signature' for request verification. This header specifies the algorithm and token type.

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

--------------------------------

### Upstash Workflow - Trigger Workflow

Source: https://upstash.com/docs/qstash/overall/llms-txt

Start a workflow execution using the Workflow client.

```APIDOC
## POST /v2/publish/{workflow_url}

### Description
Start a workflow execution using the Workflow client.

### Method
POST

### Endpoint
/v2/publish/{workflow_url}

### Parameters
#### Path Parameters
- **workflow_url** (string) - Required - The URL of the workflow endpoint.

#### Query Parameters
None

#### Request Body
- **userId** (string) - Required - The ID of the user.
- **email** (string) - Required - The email address of the user.
- **name** (string) - Required - The name of the user.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - application/json
- **Upstash-Workflow-RunId** (string) - Optional - Custom ID for the workflow run.
- **Upstash-Retries** (integer) - Optional - Number of retries for the initial request.

### Request Example (cURL)
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

### Response
#### Success Response (200)
- **workflowRunId** (string) - The ID of the triggered workflow run.

#### Response Example
```json
{
  "workflowRunId": "wf_abc123"
}
```
```

--------------------------------

### QStash Signature Verification via SDK

Source: https://upstash.com/docs/qstash/howto/signature

This section details how to use the QStash SDKs to verify incoming request signatures. It provides code examples for TypeScript, Python, and Go.

```APIDOC
## QStash Signature Verification via SDK

QStash SDKs provide a `Receiver` type that simplifies signature verification.

### Request Example (TypeScript)
```typescript
import { Receiver } from "@upstash/qstash";

const receiver = new Receiver({
  currentSigningKey: "YOUR_CURRENT_SIGNING_KEY",
  nextSigningKey: "YOUR_NEXT_SIGNING_KEY",
});

// ... in your request handler

const signature = req.headers["Upstash-Signature"];
const body = req.body;

const isValid = await receiver.verify({
  body,
  signature,
  url: "YOUR-SITE-URL",
});
```

### Request Example (Python)
```python
from qstash import Receiver

receiver = Receiver(
    current_signing_key="YOUR_CURRENT_SIGNING_KEY",
    next_signing_key="YOUR_NEXT_SIGNING_KEY",
)

# ... in your request handler

signature, body = req.headers["Upstash-Signature"], req.body

receiver.verify(
    body=body,
    signature=signature,
    url="YOUR-SITE-URL",
)
```

### Request Example (Golang)
```go
import "github.com/qstash/qstash-go"

receiver := qstash.NewReceiver("<CURRENT_SIGNING_KEY>", "NEXT_SIGNING_KEY")

// ... in your request handler

signature := req.Header.Get("Upstash-Signature")
body, err := io.ReadAll(req.Body)
// handle err

err := receiver.Verify(qstash.VerifyOptions{
    Signature: signature,
    Body:      string(body),
    Url:       "YOUR-SITE-URL", // optional
})
// handle err
```

<Warning>Depending on the environment, the body might be parsed into an object by the HTTP handler if it is JSON. Ensure you use the raw body string as is. For example, converting the parsed object back to a string (e.g., JSON.stringify(object)) may cause inconsistencies and result in verification failure.</Warning>
```

--------------------------------

### QStash Library Installation

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Installs the official Upstash QStash library for Node.js. This library provides the necessary tools to interact with QStash services, including receiving and verifying webhooks.

```bash
npm install @upstash/qstash
```

--------------------------------

### Get Queue Details

Source: https://upstash.com/docs/qstash/features/queues

Retrieve the current configuration details for a specific queue, including its parallelism settings.

```APIDOC
## GET /v2/queues/{queueName}

### Description
Retrieves the details of a specific queue.

### Method
GET

### Endpoint
`/v2/queues/{queueName}`

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to retrieve details for.

### Response
#### Success Response (200)
- **queueName** (string) - The name of the queue.
- **parallelism** (integer) - The current parallelism setting for the queue.

#### Response Example
```json
{
  "queueName": "my-queue",
  "parallelism": 5
}
```
```

--------------------------------

### POST /v2/publish/{url}

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publishes a single message to a specified URL with configurable retry attempts. If the message fails, QStash will retry sending it up to the specified limit.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a single message to a given URL. Allows configuring the maximum number of retries before considering the message undeliverable.

### Method
POST

### Endpoint
`/v2/publish/<url>`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to send the message to.

#### Query Parameters
None

#### Request Body
- **message** (object) - Required - The JSON payload of the message to be sent.

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Retries** (string) - Optional - The maximum number of times to retry sending the message (e.g., "3").
- **Content-type** (string) - Required - Should be set to "application/json".

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
(No specific response body detailed in the provided text, but typically a confirmation of message publishing)

#### Response Example
(Not provided in the source text)
```

--------------------------------

### List QStash Schedules

Source: https://upstash.com/docs/qstash/overall/apiexamples

Retrieve a list of all schedules that have been created within the QStash service. This is useful for managing scheduled messages.

```shell
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer XXX"
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
const scheds = await client.schedules.list();
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.list()
# Async version is also available
```

--------------------------------

### Run QStash CLI Dev Server with NPX

Source: https://upstash.com/docs/qstash/howto/local-development

Use NPX to run the QStash CLI development server. This command starts the server locally, allowing you to test QStash features. You can specify a different port using the -port flag. This method is convenient for quick local testing.

```bash
npx @upstash/qstash-cli dev

# Start on a different port
npx @upstash/qstash-cli dev -port=8081
```

--------------------------------

### Set QStash Callback URLs

Source: https://upstash.com/docs/qstash/overall/apiexamples

Configure success and failure callback URLs to receive endpoint responses. If the endpoint doesn't respond, the failure callback is used.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  callback: "https://example.com/callback",
  failureCallback: "https://example.com/failure",
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
    callback="https://example.com/callback",
    failure_callback="https://example.com/failure",
)
# Async version is also available
```

--------------------------------

### QStash API Authentication with Query Parameter

Source: https://upstash.com/docs/qstash/api/messages

This section explains how to authenticate API requests using the `qstash_token` query parameter when setting headers is not possible.

```APIDOC
## QStash API Authentication with Query Parameter

### Description
If you cannot set the `Authorization` header, you can authenticate your requests by appending the `qstash_token` query parameter to your request URL with your `QSTASH_TOKEN`.

### Method
All HTTP methods (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/*?qstash_token=<QSTASH_TOKEN>`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash authentication token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the operation.

#### Response Example
```json
{
  "message": "Request processed successfully"
}
```
```

--------------------------------

### Set Max Retry Count for Message Publishing with QStash

Source: https://upstash.com/docs/qstash/overall/apiexamples

Configure the maximum number of retries for sending a message before it's sent to the dead-letter queue. This example shows how to set retries to 3 using cURL, TypeScript SDK, or Python SDK. Replace 'XXX' with your token and specify your target URL and message body.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  retries: 3,
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
)
# Async version is also available
```

--------------------------------

### QStash JWT Payload Example

Source: https://upstash.com/docs/qstash/features/security

An example of the JWT payload found in the 'Upstash-Signature' header. It includes issuer, subject, expiration, not-before, issued-at, JWT ID, and a base64 encoded hash of the request body.

```json
{
  "iss": "Upstash",
  "sub": "https://qstash-remote.requestcatcher.com/test",
  "exp": 1656580612,
  "nbf": 1656580312,
  "iat": 1656580312,
  "jti": "jwt_67kxXD6UBAk7DqU6hzuHMDdXFXfP",
  "body": "qK78N0k3pNKI8zN62Fq2Gm-_LtWkJk1z9ykio3zZvY4="
}
```

--------------------------------

### Create Workflow with Steps (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Define and execute workflows using the Upstash Workflow SDK for Python, integrated with FastAPI. This example showcases sequential steps including sending emails and managing workflow context, executed via an asynchronous endpoint.

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

--------------------------------

### Publish Message to Endpoint using QStash API

Source: https://upstash.com/docs/qstash/overall/apiexamples

Demonstrates publishing a JSON message to a specified endpoint using cURL, the Typescript SDK, and the Python SDK. Requires authentication token and target URL. Outputs a confirmation of message publication.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
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
# Async version is also available
```

--------------------------------

### Get Message Details (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message using its ID with the Upstash QStash SDK for Python. The client is initialized with a QStash token, and the get method fetches message information. Errors are caught and logged if the message is unavailable.

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

--------------------------------

### Authenticate with Bearer Token using cURL

Source: https://upstash.com/docs/qstash/api/publish

Demonstrates how to include your QSTASH_TOKEN in the Authorization header for API requests. This is the standard method for authentication.

```bash
curl https://qstash.upstash.io/v2/publish/... \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### QStash API Authentication with Query Parameter

Source: https://upstash.com/docs/qstash/api/dlq/listMessages

Alternatively, you can authenticate by appending your QStash Token as a query parameter (`qstash_token`) if setting headers is not possible.

```APIDOC
## QStash API Authentication with Query Parameter

### Description
This method uses the `qstash_token` query parameter for authentication, useful in environments where headers cannot be set.

### Method
Any (e.g., POST, GET)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
(Varies based on the specific endpoint called)

#### Response Example
(Varies based on the specific endpoint called)
```

--------------------------------

### Handling Callbacks in Next.js

Source: https://upstash.com/docs/qstash/features/callbacks

Provides a Next.js API route example for handling incoming callbacks from Upstash QStash. It includes decoding the base64-encoded message body and using the `verifySignature` function from `@upstash/qstash/nextjs` to ensure the request's authenticity. The `bodyParser` is disabled to allow manual body parsing.

```javascript
// pages/api/callback.js

import { verifySignature } from "@upstash/qstash/nextjs";

function handler(req, res) {
  // responses from qstash are base64-encoded
  const decoded = atob(req.body.body);
  console.log(decoded);

  return res.status(200).end();
}

export default verifySignature(handler);

export const config = {
  api: {
    bodyParser: false,
  },
};
```

--------------------------------

### Schedule Daily Task with QStash

Source: https://upstash.com/docs/qstash/overall/apiexamples

Schedule a task to run once a day using QStash. This can be done via cURL, the TypeScript SDK, or the Python SDK. The cron syntax '0 0 * * *' ensures the task runs at midnight every day. Ensure you replace 'XXX' with your actual authorization token and 'https://example.com' with your target URL.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Cron: 0 0 * * *" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "0 0 * * *",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="0 0 * * *",
)
# Async version is also available
```

--------------------------------

### QStash API Authentication using Query Parameter

Source: https://upstash.com/docs/qstash/api/messages/get

This section explains how to authenticate your QStash API requests using the `qstash_token` query parameter when setting headers is not possible.

```APIDOC
## QStash API Authentication using Query Parameter

### Description
When setting the `Authorization` header is not feasible, you can authenticate your QStash API requests by including your `QSTASH_TOKEN` as the `qstash_token` query parameter.

### Method
This example uses cURL, but the principle applies to any HTTP client.

### Endpoint
`https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>` (Example endpoint)

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
(Response details depend on the specific endpoint being called)

#### Response Example
(Response example depends on the specific endpoint being called)
```

--------------------------------

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/queues/upsert

This section explains how to authenticate QStash API requests using the `qstash_token` query parameter when header authentication is not possible.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
When setting the `Authorization` header is not feasible, authenticate QStash API requests by appending the `qstash_token` query parameter to your request URL.

### Method
N/A (Applies to all methods)

### Endpoint
N/A (Applies to all endpoints)

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash authentication token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
No specific response for authentication, but subsequent requests will be authorized.
```

--------------------------------

### Publish Message with Custom Headers (cURL)

Source: https://upstash.com/docs/qstash/howto/publishing

Example of publishing a message using cURL, including custom headers.

```APIDOC
## Publish Message with Custom Headers (cURL)

### Description
This example demonstrates how to publish a JSON message with a custom forwardable header using cURL.

### Method
POST

### Endpoint
`/publish/https://example.com`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.
- **headers** (object) - Optional - Key-value pairs for custom headers. Prefixed with `Upstash-Forward-` in the actual request.

### Request Example
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the publish operation.

#### Response Example
```json
{
  "status": "published"
}
```

### Delivered Message Details
// body
{
  "hello": "world"
}

// headers
My-Header:      my-value
Content-Type:   application/json
```

--------------------------------

### Set Up ngrok Tunnel and Publish Message

Source: https://upstash.com/docs/qstash/howto/local-tunnel

ngrok is a powerful tool for creating secure tunnels to your local server. This snippet shows how to set up ngrok with your authentication token, start a tunnel to your application's port, and then use curl to publish a message to your tunneled endpoint via QStash.

```bash
ngrok config add-authtoken XXX
```

```bash
$ ngrok http 3000
```

```bash
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://e02f-2a02-810d-af40-5284-b139-58cc-89df-b740.eu.ngrok.io/api/webhooks'
```

--------------------------------

### QStash API Authentication

Source: https://upstash.com/docs/qstash/api/publish

This section details how to authenticate requests to the QStash API using either a Bearer Token in the header or a query parameter.

```APIDOC
## QStash API Authentication Methods

### Description
To access QStash API endpoints, you must authenticate your requests. QStash supports authentication via a Bearer Token in the request header or as a query parameter.

### Authentication via Bearer Token (Header)
This is the recommended method for authentication.

**Method:** `Authorization` Header
**Format:** `Authorization: Bearer <QSTASH_TOKEN>`

### Authentication via Query Parameter
Use this method if you cannot set request headers.

**Method:** Query Parameter
**Format:** `?qstash_token=<QSTASH_TOKEN>`

### Request Example (cURL with Bearer Token)
```bash
curl https://qstash.upstash.io/v2/publish/ -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Request Example (cURL with Query Parameter)
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Security Note
Always keep your QSTASH_TOKEN secure and reset it if you suspect it has been compromised.
```

--------------------------------

### QStash API Authentication Methods

Source: https://upstash.com/docs/qstash/api/events/list

This section details how to authenticate your API requests to QStash, either by including your QSTASH_TOKEN in the Authorization header or as a query parameter.

```APIDOC
## QStash API Authentication

### Description
Authenticate your requests to the QStash API by providing your `QSTASH_TOKEN`.

### Method
Authentication can be performed using either the `Authorization` header or a query parameter.

### Endpoint
N/A (Applies to all QStash API endpoints)

### Parameters
#### Request Header
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

#### Query Parameters
- **qstash_token** (string) - Required - Your `QSTASH_TOKEN`

### Request Example (Bearer Token)
```bash
curl https://qstash.upstash.io/v2/publish/\n  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Request Example (Query Parameter)
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
Authentication is verified before the actual endpoint response is returned. If authentication fails, an appropriate error response will be provided by the API.
```

--------------------------------

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/schedules/create

Authenticate QStash API requests by including your QSTASH_TOKEN as a query parameter when headers cannot be used.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
This method shows how to authenticate API requests by providing your `QSTASH_TOKEN` as a query parameter. This is useful in environments where setting request headers is not possible.

### Method
All HTTP Methods (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your `QSTASH_TOKEN`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/some-topic?qstash_token=<YOUR_QSTASH_TOKEN>
```

### Response
#### Success Response (200)
Responses vary based on the specific endpoint called.

#### Response Example
(Example depends on the specific endpoint)
```

--------------------------------

### Create Workflow with Steps (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Build durable workflows with step-based execution using the Upstash Workflow SDK for TypeScript within a Next.js environment. This example demonstrates sending emails, sleeping for a duration, calling an external API (OpenAI), and running sequential steps with error recovery.

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

--------------------------------

### Initialize Golang Project for fly.io

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Initializes a new Golang project directory and sets up go module management, preparing it for deployment on fly.io.

```bash
mkdir flyio-go
cd flyio-go
go mod init flyio-go
```

--------------------------------

### QStash API Authentication with Bearer Token

Source: https://upstash.com/docs/qstash/api/dlq/listMessages

Authenticate your API requests by including your QStash Token in the `Authorization` header as a Bearer Token.

```APIDOC
## QStash API Authentication with Bearer Token

### Description
This method uses the `Authorization` header to pass your QStash token.

### Method
Any (e.g., POST, GET)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/ \ 
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
(Varies based on the specific endpoint called)

#### Response Example
(Varies based on the specific endpoint called)
```

--------------------------------

### QStash API Authentication using Bearer Token

Source: https://upstash.com/docs/qstash/api/messages/get

This section details how to authenticate your QStash API requests using the `Authorization` header with a Bearer Token.

```APIDOC
## QStash API Authentication using Bearer Token

### Description
Authenticate your requests to the QStash API by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer Token.

### Method
This example uses cURL, but the principle applies to any HTTP client.

### Endpoint
`https://qstash.upstash.io/v2/publish/...` (Example endpoint)

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\ldots \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
(Response details depend on the specific endpoint being called)

#### Response Example
(Response example depends on the specific endpoint being called)
```

--------------------------------

### Publish Message with Delay using QStash API

Source: https://upstash.com/docs/qstash/overall/apiexamples

Illustrates how to schedule a message publication with a delay using cURL, Typescript SDK, and Python SDK. The message will be held by QStash for the specified duration before being sent to the endpoint. Requires authentication, URL, and delay parameter.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 5m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  delay: 300,
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
)
# Async version is also available
```

--------------------------------

### Create Python Project Directory

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Initializes a new directory for the Python application and navigates into it. This is the first step in setting up the project structure.

```bash
mkdir clean-db-cron
cd clean-db-cron
```

--------------------------------

### Get Message Details

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message by its ID. This is only available while the message is being processed.

```APIDOC
## GET /v2/messages/{messageId}

### Description
Retrieve details for a specific message by its ID. This is only available while the message is being processed.

### Method
GET

### Endpoint
/v2/messages/{messageId}

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The ID of the message to retrieve.

#### Query Parameters
None

#### Request Body
None

### Request Example
```bash
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier of the message.
- **url** (string) - The URL the message was sent to.
- **createdAt** (integer) - The timestamp when the message was created.
- **body** (string) - The content of the message.

#### Response Example
```json
{
  "messageId": "msg_123",
  "url": "https://example.com/webhook",
  "createdAt": 1678886400,
  "body": "{\"key\": \"value\"}"
}
```
```

--------------------------------

### Publish Message to URL Group using QStash API

Source: https://upstash.com/docs/qstash/overall/apiexamples

Shows how to publish a JSON message to a URL group for fan-out distribution using cURL, Typescript SDK, and Python SDK. Requires authentication and the URL group name. The message will be sent to all registered endpoints in the group.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/myUrlGroup'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  urlGroup: "myUrlGroup",
  body: {
    hello: "world",
  },
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url_group="my-url-group",
    body={
        "hello": "world",
    },
)
# Async version is also available
```

--------------------------------

### Publish Message with Custom Header using QStash API

Source: https://upstash.com/docs/qstash/overall/apiexamples

Demonstrates adding a custom header to a published message using cURL, Typescript SDK, and Python SDK. This allows passing additional metadata to the target endpoint. Requires authentication, URL, and specification of the custom header.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
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
    headers={
        "My-Header": "my-value",
    },
)
# Async version is also available
```

--------------------------------

### QStash API Endpoint to Start Background Job

Source: https://upstash.com/docs/qstash/features/background-jobs

This Next.js API route handler, written in TypeScript, receives user data and uses the Upstash QStash client to publish a JSON message. This message invokes a separate API endpoint that contains the actual background job logic. It dynamically constructs the URL for the background job endpoint. Requires your QStash token.

```typescript
import { Client } from "@upstash/qstash";

const qstashClient = new Client({
  token: "YOUR_TOKEN",
});

export async function POST(request: Request) {
  const body = await request.json();
  const users: string[] = body.users;
  // If you know the public URL of the email API, you can use it directly
  const rootDomain = request.url.split('/').slice(0, 3).join('/');
  const emailAPIURL = `${rootDomain}/api/send-email`; // ie: https://yourapp.com/api/send-email

  // Tell QStash to start the background job.
  // For proper error handling, refer to the quick start.
  await qstashClient.publishJSON({
    url: emailAPIURL,
    body: {
      users
    }
  });

  return new Response("Job started", { status: 200 });
}

```

--------------------------------

### Configure QStash Retry Delay

Source: https://upstash.com/docs/qstash/overall/apiexamples

Customize the delay between message delivery retry attempts using mathematical expressions. Supports exponential backoff and other functions. Default is exponential backoff.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  retries: 3,
  retryDelay: "pow(2, retried) * 1000", // 2^retried * 1000ms
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
    retry_delay="pow(2, retried) * 1000",  # 2^retried * 1000ms
)
# Async version is also available
```

--------------------------------

### Authenticate with Query Parameter using cURL

Source: https://upstash.com/docs/qstash/api/publish

Shows how to pass your QSTASH_TOKEN as a query parameter in the URL. This method is useful in environments where setting request headers is not feasible.

```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

### Get QStash Queue Configuration

Source: https://upstash.com/docs/qstash/features/queues

Retrieves the current configuration, including parallelism settings, for a specified QStash queue. This allows you to inspect the settings of an existing queue.

```bash
curl https://qstash.upstash.io/v2/queues/my-queue \
    -H "Authorization: Bearer <token>"
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

  const queue = client.queue({
    queueName: "my-queue"
  })

  const res = await queue.get()
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.get("my-queue")
```

--------------------------------

### Deploy App with Fly.io

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Instructions on deploying your application using the Fly.io CLI.

```APIDOC
## Deploy the App

Fly.io makes deployment simple with a single command.

### Method

`flyctl` command

### Command

`flyctl deploy`

### Description

This command deploys your application to the Fly.io platform.
```

--------------------------------

### Schedule a Message to a Queue

Source: https://upstash.com/docs/qstash/features/schedules

This example shows how to schedule a message to be added to a specified queue at a set time. It includes implementations in TypeScript and cURL. The `queueName` option in the client or the `Upstash-Queue-Name` header in cURL is used to designate the target queue. Replace placeholders as necessary.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
  queueName: "yourQueueName",
});
```

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -H "Upstash-Queue-Name: yourQueueName" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

### POST /v2/publish/:url - Publish Message with Custom Retry Delay

Source: https://upstash.com/docs/qstash/overall/apiexamples

Publish a JSON message to a specified URL with custom retry settings. You can configure the number of retries and the delay between attempts using mathematical expressions.

```APIDOC
## POST /v2/publish/:url

### Description
Publish a JSON message to a specified URL with custom retry settings. You can configure the number of retries and the delay between attempts using mathematical expressions.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/<url>`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Retry-Delay** (string) - Optional - Mathematical expression for retry delay (e.g., `pow(2, retried) * 1000`).
- **Upstash-Retries** (integer) - Optional - Number of retry attempts.
- **Content-type** (string) - Required - `application/json`.

### Request Body
- **body** (object) - Required - The JSON payload to send.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Request Example (TypeScript SDK)
```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  retries: 3,
  retryDelay: "pow(2, retried) * 1000", // 2^retried * 1000ms
});
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.
- **delay** (integer) - The delay in seconds before the message will be delivered.

#### Response Example
```json
{
  "messageId": "msg_abc123",
  "delay": 0
}
```
```

--------------------------------

### Authenticate with Bearer Token Header

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessage

This method demonstrates how to include your QStash token in the 'Authorization' header for API requests. It's the recommended approach when possible.

```cURL
curl https://qstash.upstash.io/v2/publish/ \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Publish Message with Custom Headers (Python)

Source: https://upstash.com/docs/qstash/howto/publishing

Example of publishing a JSON message with custom headers using the Upstash QStash Python client.

```APIDOC
## Publish Message with Custom Headers (Python)

### Description
This example demonstrates publishing a JSON message with custom headers using the Upstash QStash Python client.

### Method
POST

### Endpoint
(Client-side abstraction, maps to `/publish`)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **url** (string) - Required - The URL of the destination.
- **body** (dict) - Required - The dictionary representing the JSON payload of the message.
- **headers** (dict) - Optional - Key-value pairs for custom headers to be forwarded.

### Request Example
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    headers={
        "my-header": "my-value",
    },
)
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Run QStash CLI Dev Server with Binary

Source: https://upstash.com/docs/qstash/howto/local-development

Instructions for running the QStash CLI development server after downloading the binary directly. Extract the archive file and then execute the 'qstash dev' command from your terminal. This method bypasses package managers.

```bash
$ ./qstash dev
```

--------------------------------

### QStash API Authentication

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessages

This section details how to authenticate your API requests to QStash using either a Bearer Token in the Authorization header or the `qstash_token` query parameter.

```APIDOC
## Bearer Token Authentication

### Description
Authenticate your QStash API requests by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer Token.

### Method
Any HTTP method (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/publish/...`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\ldots \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

## Query Parameter Authentication

### Description
If you cannot set headers, you can authenticate by appending the `qstash_token` query parameter to your request URL.

### Method
Any HTTP method (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\ldots?qstash_token=<QSTASH_TOKEN>
```

### Security Note
Always keep your token secure. Reset it if you suspect it has been compromised.
```

--------------------------------

### QStash API Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/queues/upsert

This section describes how to authenticate QStash API requests using a Bearer Token in the Authorization header.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
Authenticate QStash API requests by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer token.

### Method
N/A (Applies to all methods)

### Endpoint
N/A (Applies to all endpoints)

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\n  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
No specific response for authentication, but subsequent requests will be authorized.
```

--------------------------------

### Publish JSON Message using Upstash QStash SDK (TypeScript)

Source: https://upstash.com/docs/qstash/howto/publishing

Provides a TypeScript example using the Upstash QStash client to publish a JSON message. It shows how to initialize the client with a token, specify the destination URL, the message body as a JavaScript object, and custom headers. The SDK abstracts the HTTP request details.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://example.com",
    body: { "hello": "world" },
    headers: { "my-header": "my-value" },
});
```

--------------------------------

### QStash API Authentication with Bearer Token

Source: https://upstash.com/docs/qstash/api/messages

This section details how to authenticate API requests using the Bearer Token method by including your QSTASH_TOKEN in the Authorization header.

```APIDOC
## QStash API Authentication with Bearer Token

### Description
Authenticate your requests to the QStash API by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer Token. This is the recommended method for authentication.

### Method
All HTTP methods (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/... \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the operation.

#### Response Example
```json
{
  "message": "Request processed successfully"
}
```
```

--------------------------------

### Publish Message with Custom Headers (TypeScript)

Source: https://upstash.com/docs/qstash/howto/publishing

Example of publishing a JSON message with custom headers using the Upstash QStash TypeScript client.

```APIDOC
## Publish Message with Custom Headers (TypeScript)

### Description
This example shows how to publish a JSON message with custom headers using the Upstash QStash TypeScript client.

### Method
POST

### Endpoint
(Client-side abstraction, maps to `/publish`)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **url** (string) - Required - The URL of the destination.
- **body** (object) - Required - The JSON payload of the message.
- **headers** (object) - Optional - Key-value pairs for custom headers to be forwarded.

### Request Example
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://example.com",
  body: { "hello": "world" },
  headers: { "my-header": "my-value" },
});
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Deploy AWS CDK Stack

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This command deploys your AWS CDK stack to the cloud. It requires the AWS CDK CLI to be installed and configured. Running this command will provision or update AWS resources defined in your CDK stack. You may be prompted to confirm necessary permissions.

```bash
cdk deploy
```

--------------------------------

### QStash Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/messages/batch

If you cannot set the Authorization header, you can authenticate your QStash API requests by appending your QSTASH_TOKEN as a query parameter named `qstash_token`.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
In environments where setting the `Authorization` header is not feasible, you can authenticate your QStash API requests by appending your `QSTASH_TOKEN` as a query parameter named `qstash_token` to the endpoint URL.

### Method
Any (e.g., GET, POST, PUT, DELETE)

### Endpoint
Any QStash API endpoint

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your Qstash API token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/your-topic-or-url?qstash_token=YOUR_QSTASH_TOKEN
```

### Response
#### Success Response (200)
Responses will vary based on the specific endpoint being called.

#### Response Example
```json
{
  "message": "Request successful"
}
```
```

--------------------------------

### QStash API Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/schedules/create

Authenticate QStash API requests by including your QSTASH_TOKEN in the Authorization header as a Bearer Token.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
This method shows how to authenticate API requests by providing your `QSTASH_TOKEN` in the `Authorization` header.

### Method
All HTTP Methods (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/some-topic \
  -H "Authorization: Bearer <YOUR_QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
Responses vary based on the specific endpoint called.

#### Response Example
(Example depends on the specific endpoint)
```

--------------------------------

### Create a Schedule to a URL Group

Source: https://upstash.com/docs/qstash/features/schedules

This code illustrates how to schedule messages to be published to a URL Group using its name or ID. The examples are provided for TypeScript, Python, and cURL, enabling flexible integration into different projects. Remember to substitute placeholders like '<QSTASH_TOKEN>' and '<URL_GROUP_ID_OR_NAME>' with your specific values.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "urlGroupName",
  cron: "* * * * *",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="url-group-name",
    cron="* * * * *",
)
```

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/<URL_GROUP_ID_OR_NAME>'
```

--------------------------------

### Publishing with Helicone Analytics in QStash (TypeScript)

Source: https://upstash.com/docs/qstash/integrations/llm

Demonstrates how to publish a JSON message with Helicone analytics enabled for LLM usage monitoring. This requires a QStash client and custom provider setup, passing the Helicone API key via environment variables.

```typescript
import { Client, custom } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
});

await client.publishJSON({
  api: {
    name: "llm",
    provider: custom({
      token: "XXX",
      baseUrl: "https://api.together.xyz",
    }),
    analytics: { name: "helicone", token: process.env.HELICONE_API_KEY! },
  },
  body: {
    model: "meta-llama/Llama-3-8b-chat-hf",
    messages: [
      {
        role: "user",
        content: "hello",
      },
    ],
  },
  callback: "https://oz.requestcatcher.com/",
});
```

--------------------------------

### Next.js UI to Start Background Job

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This React component provides a user interface for triggering a background job in a Next.js application. It uses the `useState` hook to manage loading and message states. A button click calls the `startBackgroundJob` function (imported from `./actions`) and updates the UI to show a loading indicator or the result of the operation, including the message ID if successful.

```typescript
"use client"
import { startBackgroundJob } from "@/app/actions";
import { useState } from "react";

export default function Home() {
  const [loading, setLoading] = useState(false);
  const [msg, setMsg] = useState("");

  async function handleClick() {
    setLoading(true);
    const messageId = await startBackgroundJob();
    if (messageId) {
      setMsg(`Started job with ID ${messageId}`);
    } else {
      setMsg("Failed to start background job");
    }
    setLoading(false);
  }

  return (
    <main className="flex flex-col h-lvh items-center justify-center">
      <button onClick={handleClick} disabled={loading} className="btn btn-primary w-1/2 h-56 bg-green-500 text-xl sm:text-3xl rounded-lg hover:bg-green-600 disabled:bg-gray-500">
        Start Background Job
      </button>

      {loading && <div className="text-2xl mt-8">Loading...</div>}
      {msg && <p className="text-center text-lg">{msg}</p>}
    </main>
  );
}
```

--------------------------------

### Bundle and Zip Lambda Function (Makefile)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

This script automates the process of installing Python dependencies (pyjwt), copying the Lambda function code, and creating a zip archive for deployment to AWS. It ensures all necessary components are bundled correctly.

```yaml
zip:
    rm -rf dist
	pip3 install --target ./dist pyjwt
	cp lambda_function.py ./dist/lambda_function.py
	cd dist && zip -r lambda.zip .
	mv ./dist/lambda.zip ./
```

--------------------------------

### Batch Messages with Headers and Body (TypeScript)

Source: https://upstash.com/docs/qstash/features/batch

Programmatically send batched messages with custom headers and bodies using the QStash TypeScript client. This example demonstrates creating an array of message objects, each with potential properties like urlGroup, url, delay, body, and headers. The `batchJSON` method handles the batching logic.

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

  // Each message is the same as the one you would send with the publish endpoint
  const msgs = [
    {
      urlGroup: "myUrlGroup",
      delay: 5,
      body: "Hello World",
      headers: {
        hello: "123456",
      },
    },
    {
      url: "https://example.com/destination1",
      delay: 7,
      headers: {
        hello: "789",
      },
    },
    {
      url: "https://example.com/destination2",
      delay: 9,
      headers: {
        hello: "again",
      },
      body: {
        Some: "Data",
      },
    },
  ];

  const res = await client.batchJSON(msgs);
```

--------------------------------

### GET /v2/logs

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves event logs for published messages, allowing you to track delivery status, errors, and retry attempts. Filtering options can be applied to narrow down the search results.

```APIDOC
## GET /v2/logs

### Description
Retrieves event logs for published messages to track delivery status, errors, and retry attempts.

### Method
GET

### Endpoint
/v2/logs

### Parameters
#### Path Parameters
None

#### Query Parameters
- **from** (string) - Optional. Filter logs from a specific timestamp.
- **to** (string) - Optional. Filter logs up to a specific timestamp.
- **messageId** (string) - Optional. Filter logs for a specific message ID.
- **limit** (number) - Optional. The maximum number of logs to return.
- **cursor** (string) - Optional. Cursor for pagination.

#### Request Body
None

### Request Example
```bash
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
An object containing a list of log events, each with details about the message delivery.

#### Response Example
```json
{
  "events": [
    {
      "time": "1701198447054",
      "state": "delivered",
      "messageId": "msg_xxx",
      "url": "http://myurl.com",
      "responseStatus": 200
    }
  ],
  "nextCursor": "..."
}
```
```

--------------------------------

### QStash Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/messages/batch

Authenticate your QStash API requests by including your QSTASH_TOKEN in the 'Authorization' header as a Bearer token. This is the recommended method for authentication.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
Authenticate your QStash API requests by including your `QSTASH_TOKEN` in the `Authorization` header. This is the standard and recommended method for securing your API calls.

### Method
Any (e.g., GET, POST, PUT, DELETE)

### Endpoint
Any QStash API endpoint

### Parameters
#### Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/your-topic-or-url \
  -H "Authorization: Bearer YOUR_QSTASH_TOKEN"
```

### Response
#### Success Response (200)
Responses will vary based on the specific endpoint being called.

#### Response Example
```json
{
  "message": "Request successful"
}
```
```

--------------------------------

### Initialize QStash Client (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes the QStash client using the Python SDK. The Python SDK handles retries internally, abstracting this complexity from the developer. Both synchronous and asynchronous client versions are available.

```python
from qstash import QStash

# Python SDK handles retries internally
client = QStash("<QSTASH_TOKEN>")

# Both sync and async versions available
from qstash import AsyncQStash

async_client = AsyncQStash("<QSTASH_TOKEN>")
```

--------------------------------

### QStash API Authentication

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessage

This section details the two methods for authenticating requests to the QStash API: using a Bearer Token in the Authorization header or the qstash_token query parameter.

```APIDOC
## QStash API Authentication

### Description
Requests to the QStash API require authentication. You can authenticate either by providing your `QSTASH_TOKEN` in the `Authorization` header as a Bearer token or by including it as a `qstash_token` query parameter.

### Method
All requests to QStash API endpoints require authentication.

### Endpoints
All QStash API endpoints.

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.

### Request Example (Bearer Token)
```bash
curl https://qstash.upstash.io/v2/publish/...
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Request Example (Query Parameter)
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Notes
- Always keep your token secure.
- Reset your token if you suspect it has been compromised.
```

--------------------------------

### Authenticate with Bearer Token using cURL

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessages

This snippet demonstrates how to include your QStash token in the request header using the 'Authorization: Bearer <QSTASH_TOKEN>' format with cURL. This is the recommended method for authentication.

```shell
curl https://qstash.upstash.io/v2/publish/\
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Publish to URL Group using TypeScript

Source: https://upstash.com/docs/qstash/howto/publishing

This TypeScript example shows how to publish a JSON message to a URL Group using the Upstash QStash client library. It requires initializing the client with a QStash token and then calling the `publishJSON` method with the `urlGroup` and `body` parameters. The method returns a promise that resolves with the publish response.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    urlGroup: "my-url-group",
    body: { "hello": "world" },
});
```

--------------------------------

### Initialize AWS Lambda Project Structure (Bash)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

Creates a new directory for the AWS Lambda project and initializes an empty Python file for the Lambda function handler. This sets up the basic file structure required for the project.

```bash
mkdir aws-lambda
cd aws-lambda
touch lambda_function.py
```

--------------------------------

### Handle Callback Responses in Next.js

Source: https://upstash.com/docs/qstash/overall/llms-txt

Process callback payloads in a Next.js API route, including signature verification for authenticity. It decodes the base64 encoded response body and logs relevant information. Ensure the `@upstash/qstash/nextjs` library is installed.

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

--------------------------------

### QStash API Authentication Methods

Source: https://upstash.com/docs/qstash/api/enqueue

The QStash API requires authentication for all requests. You can authenticate using either a Bearer Token in the Authorization header or by including the `qstash_token` as a query parameter.

```APIDOC
## QStash API Authentication

### Description
This section details the authentication methods for the QStash API, including the use of Bearer Tokens and query parameters.

### Authentication Methods

1.  **Bearer Token (Recommended)**
    *   **Method**: `Authorization: Bearer <QSTASH_TOKEN>`
    *   **Description**: Add your `QSTASH_TOKEN` to the `Authorization` header of your request.
    *   **Endpoint Example**: `https://qstash.upstash.io/v2/publish/...
`
    *   **Request Example (cURL)**:
        ```bash
        curl https://qstash.upstash.io/v2/publish/\
          -H "Authorization: Bearer <QSTASH_TOKEN>"
        ```

2.  **Query Parameter**
    *   **Method**: `qstash_token=<QSTASH_TOKEN>`
    *   **Description**: Use this method if setting headers is not possible. Append your `QSTASH_TOKEN` as a query parameter to the URL.
    *   **Endpoint Example**: `https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
`
    *   **Request Example (cURL)**:
        ```bash
        curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
        ```

### Security Recommendation
Always keep your token safe and reset it if you suspect it has been compromised.
```

--------------------------------

### Overwrite an Existing Schedule

Source: https://upstash.com/docs/qstash/features/schedules

This functionality allows you to update an existing schedule by providing its `scheduleId`. The examples cover TypeScript and cURL, demonstrating how to modify a schedule's configuration or destination. Ensure you replace `<QSTASH_TOKEN>` and `existingScheduleId` with your actual values.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  scheduleId: "existingScheduleId",
  cron: "* * * * *",
});
```

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -H "Upstash-Schedule-Id: existingScheduleId" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

### Run QStash CLI Dev Server with Docker

Source: https://upstash.com/docs/qstash/howto/local-development

This snippet demonstrates how to run the QStash CLI development server using a Docker image. First, pull the latest QStash Docker image from the public ECR repository. Then, run the container, mapping port 8080 to expose the development server.

```bash
# Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

# Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev
```

--------------------------------

### Trigger Workflow (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Start a workflow execution with the Upstash Workflow client in Python. This function takes the workflow URL, request body, and optional parameters such as a custom workflow run ID and retry count, returning the ID of the initiated workflow run.

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

--------------------------------

### QStash API Authentication Methods

Source: https://upstash.com/docs/qstash/api/dlq/getMessage

QStash API requests require authentication. You can authenticate using a Bearer Token in the Authorization header or by including the qstash_token as a query parameter.

```APIDOC
## QStash API Authentication

### Description
Authentication is required for all QStash API endpoints. This section details the two methods for authenticating your requests: using a Bearer Token in the `Authorization` header or passing the `qstash_token` as a query parameter.

### Method
Authentication can be performed using either HTTP Headers or Query Parameters.

### Endpoints
All QStash API endpoints.

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token, used when header authentication is not feasible.

### Request Example (Header Authentication)
```bash
curl https://qstash.upstash.io/v2/publish/... \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Request Example (Query Parameter Authentication)
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Security Note
Always keep your token secure. Reset it if you suspect it has been compromised.
```

--------------------------------

### Publish Webhook with QStash

Source: https://upstash.com/docs/qstash/howto/webhook

Configure a QStash publish request to act as your webhook receiver. This method allows for request configurations like retries and timeouts via HTTP headers or query parameters. Headers prefixed with `Upstash-Forward-` are forwarded by default, or all headers can be forwarded by setting `Upstash-Header-Forward: true`.

```text
https://qstash.upstash.io/v2/publish/https://example.com/api/webhook?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

### Get Message Logs with Filtering in QStash

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve event logs for published messages to monitor their delivery status using QStash. This allows tracking message lifecycles and identifying potential issues. Requires a QStash token for authentication.

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

--------------------------------

### Get Message Details

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message using its ID. This functionality is available only while the message is being processed. It requires a QStash token for authentication and returns message metadata upon successful retrieval.

```bash
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Get Message Details (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message using its ID with the Upstash QStash SDK for TypeScript. This function requires a QStash client initialized with a token and returns message details or logs an error if the message is not found or already delivered.

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

--------------------------------

### Handling Callbacks in Your API

Source: https://upstash.com/docs/qstash/features/callbacks

This section provides information on the structure of the callback payload received from QStash and how to handle it, including signature verification.

```APIDOC
## Callback Payload Structure

### Description
When QStash sends a callback, the request body will be a JSON object containing details about the message delivery.

### Parameters
#### Request Body
- **status** (number) - The HTTP status code of the delivery attempt.
- **header** (object) - Response headers from the delivery attempt.
- **body** (string) - Base64 encoded response body of the delivery attempt.
- **retried** (number) - The number of times the message delivery was retried.
- **maxRetries** (number) - The maximum number of retries configured for the message.
- **sourceMessageId** (string) - The ID of the original message that triggered the callback.
- **topicName** (string) - The name of the topic if the message was part of a topic.
- **endpointName** (string) - The name of the endpoint if it was named within a topic.
- **url** (string) - The destination URL of the message that triggered the callback.
- **method** (string) - The HTTP method used for the message delivery.
- **sourceHeader** (object) - The HTTP headers of the original message.
- **sourceBody** (string) - Base64 encoded body of the original message.
- **notBefore** (string) - Unix timestamp (in milliseconds) when the message was scheduled for delivery.
- **createdAt** (string) - Unix timestamp (in milliseconds) when the message was created.
- **scheduleId** (string) - The ID of the schedule if the message was triggered by a schedule.
- **callerIP** (string) - The IP address from which the message was published.

### Request Example
```json
{
  "status": 200,
  "header": { "key": ["value"] },
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==",
  "retried": 0,
  "maxRetries": 3,
  "sourceMessageId": "msg_xxx",
  "topicName": "myTopic",
  "endpointName": "myEndpoint",
  "url": "http://myurl.com",
  "method": "GET",
  "sourceHeader": { "key": "value" },
  "sourceBody": "YmFzZTY0kZWQgcm9keQ==",
  "notBefore": "1701198458025",
  "createdAt": "1701198447054",
  "scheduleId": "scd_xxx",
  "callerIP": "178.247.74.179"
}
```

## Handling Callbacks in Next.js

### Description
Example code demonstrating how to handle QStash callbacks in a Next.js API route, including decoding the base64 body and verifying the signature.

### Method
POST

### Endpoint
`/api/callback` (Example)

### Parameters
#### Request Body
- **body** (string) - The raw request body from QStash, containing the base64 encoded callback payload.

### Request Example
```javascript
// pages/api/callback.js

import { verifySignature } from "@upstash/qstash/nextjs";

function handler(req, res) {
  // responses from qstash are base64-encoded
  const decoded = atob(req.body.body);
  console.log(decoded);

  return res.status(200).end();
}

export default verifySignature(handler);

export const config = {
  api: {
    bodyParser: false,
  },
};
```

### Note
Remember to verify the signature of incoming callback requests to ensure their authenticity. See [Request Signing](/qstash/features/security/#request-signing-optional) for more details.
```

--------------------------------

### Configuring Callbacks with Headers

Source: https://upstash.com/docs/qstash/features/callbacks

Explains how to configure callbacks (both regular and failure) using specific HTTP headers, including timeout, retries, delay, method, and header forwarding.

```APIDOC
## Configuring Callbacks with Headers

### Description
Callbacks, including failure callbacks, can be configured using specific HTTP headers prefixed with `Upstash-Callback` or `Upstash-Failure-Callback`. These headers allow customization of the callback behavior.

### Available Headers

For **regular callbacks**: 
- `Upstash-Callback-Timeout`
- `Upstash-Callback-Retries`
- `Upstash-Callback-Delay`
- `Upstash-Callback-Method`

For **failure callbacks**: 
- `Upstash-Failure-Callback-Timeout`
- `Upstash-Failure-Callback-Retries`
- `Upstash-Failure-Callback-Delay`
- `Upstash-Failure-Callback-Method`

### Forwarding Headers to Callbacks

You can forward custom headers to your callback endpoints by using the `Upstash-Callback-Forward-<HeaderName>` or `Upstash-Failure-Callback-Forward-<HeaderName>` prefix.

- `Upstash-Callback-Forward-MyCustomHeader`
- `Upstash-Failure-Callback-Forward-MyCustomHeader`
```

--------------------------------

### Golang: QStash Webhook Handler and Verification Logic

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Sets up an HTTP server to listen for incoming webhooks. It reads the request body, retrieves signing keys and the signature from headers, and uses the `verify` function to validate the request signature. Upon successful verification, it proceeds to business logic.

```go
func main() {
	port := os.Getenv("PORT")
	if port == "" {
		port = "8080"
	}

	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		defer r.Body.Close()

		currentSigningKey := os.Getenv("QSTASH_CURRENT_SIGNING_KEY")
		nextSigningKey := os.Getenv("QSTASH_NEXT_SIGNING_KEY")
		tokenString := r.Header.Get("Upstash-Signature")

		body, err := io.ReadAll(r.Body)
		if err != nil {
			http.Error(w, err.Error(), http.StatusInternalServerError)
			return
		}

		err = verify(body, tokenString, currentSigningKey)
		if err != nil {
			fmt.Printf("Unable to verify signature with current signing key: %v", err)
			err = verify(body, tokenString, nextSigningKey)
		}

		if err != nil {
			http.Error(w, err.Error(), http.StatusUnauthorized)
			return
		}

		// handle your business logic here

		w.WriteHeader(http.StatusOK)

	})

	fmt.Println("listening on", port)
	err := http.ListenAndServe(":"+port, nil)
	if err != nil {
		panic(err)
	}
}
```

--------------------------------

### Deno - Receive and Verify QStash Webhooks

Source: https://upstash.com/docs/qstash/quickstarts/deno-deploy

This TypeScript code snippet demonstrates how to set up an HTTP server in a Deno deploy project to receive webhooks from QStash. It utilizes the Upstash QStash SDK to verify the incoming request's signature using provided signing keys stored as environment variables. The handler logs whether the signature is valid and returns an appropriate HTTP response. Dependencies include Deno's standard HTTP server and the Upstash QStash SDK.

```typescript
import { serve } from "https://deno.land/std@0.142.0/http/server.ts";
import { Receiver } from "https://deno.land/x/upstash_qstash@v0.1.4/mod.ts";

serve(async (req: Request) => {
  const r = new Receiver({
    currentSigningKey: Deno.env.get("QSTASH_CURRENT_SIGNING_KEY")!,
    nextSigningKey: Deno.env.get("QSTASH_NEXT_SIGNING_KEY")!,
  });

  const isValid = await r
    .verify({
      signature: req.headers.get("Upstash-Signature")!,
      body: await req.text(),
    })
    .catch((err: Error) => {
      console.error(err);
      return false;
    });

  if (!isValid) {
    return new Response("Invalid signature", { status: 401 });
  }

  console.log("The signature was valid");

  // do work

  return new Response("OK", { status: 200 });
});
```

--------------------------------

### Integrate Server Action with Button Click in Next.js

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This client-side TypeScript code updates the Next.js home page to call the `startBackgroundJob` server action when the button is clicked. It imports the server action and defines an asynchronous `handleClick` function to handle the button's `onClick` event.

```tsx
"use client"
import { startBackgroundJob } from "@/app/actions"

export default function Home() {
  async function handleClick() {
    await startBackgroundJob()
  }

  return (
    <main className="flex h-lvh items-center justify-center">
      <button
        onClick={handleClick}
        className="btn btn-primary w-1/2 h-56 bg-green-500 text-xl sm:text-3xl rounded-lg hover:bg-green-600"
      >
        Start Background Job
      </button>
    </main>
  )
}
```

--------------------------------

### API Cron Route for Scraping and Storing Bitcoin Price in Next.js

Source: https://upstash.com/docs/qstash/recipes/periodic-data-updates

A Next.js API route (`/pages/api/cron.ts`) that acts as a cron job. It fetches the current Bitcoin price from a public API, stores it in Redis with a timestamp using `redis.zadd`, and verifies incoming requests using `@upstash/qstash/nextjs`. The `bodyParser` is disabled to allow `verifySignature` to access the raw request body.

```typescript
import {
  NextApiRequest,
  NextApiResponse,
} from "next";
import { Redis } from "@upstash/redis";

import { verifySignature } from "@upstash/qstash/nextjs";

/**
 * You can use any database you want, in this case we use Redis
 */
const redis = Redis.fromEnv();

/**
 * Load the current bitcoin price in USD and store it in our database at the
 * current timestamp
 */
async function handler(_req: NextApiRequest, res: NextApiResponse) {
  try {
    /**
     * The API returns something like this:
     * ```json
     * {
     *   "USD": {
     *     "last": 123
     *   },
     *   ...
     * }
     * ```
     */
    const raw = await fetch("https://blockchain.info/ticker");
    const prices = await raw.json();
    const bitcoinPrice = prices["USD"]["last"] as number;

    /**
     * After we have loaded the current bitcoin price, we can store it in the
     * database together with the current time
     */
    await redis.zadd("bitcoin-prices", {
      score: Date.now(),
      member: bitcoinPrice,
    });

    res.send("OK");
  } catch (err) {
    res.status(500).send(err);
  } finally {
    res.end();
  }
}

/**
 * Wrap your handler with `verifySignature` to automatically reject all
 * requests that are not coming from Upstash.
 */
export default verifySignature(handler);

/**
 * To verify the authenticity of the incoming request in the `verifySignature`
 * function, we need access to the raw request body.
 */
export const config = {
  api: {
    bodyParser: false,
  },
};

```

--------------------------------

### Publishing Messages with Callbacks

Source: https://upstash.com/docs/qstash/features/callbacks

This section details how to publish messages using QStash and specify a callback URL to receive delivery status or results.

```APIDOC
## POST /v2/publish

### Description
Publishes a message and specifies a callback URL to receive information about the message delivery or execution.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to which the message will be published.

#### Headers
- **Content-Type** (string) - Required - `application/json`
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`
- **Upstash-Callback** (string) - Required - The URL to which QStash will send callback information.

#### Request Body
- **body** (object) - Required - The JSON payload of the message to be published.

### Request Example
```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api... \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_xxx"
}
```
```

--------------------------------

### Expose Local Server with localtunnel.me

Source: https://upstash.com/docs/qstash/howto/local-tunnel

Use localtunnel.me to create a public URL for your local development server. This tool is simple to use and requires only the port your application is running on. It's useful for quickly testing QStash integrations.

```bash
npx localtunnel --port 3000
```

--------------------------------

### Key Rotation Logic in Pseudocode

Source: https://upstash.com/docs/qstash/howto/roll-signing-keys

Illustrates the core logic for rotating signing keys. It shows how the 'current' key is updated to the 'next' key, and a new 'next' key is generated. This pseudocode is language-agnostic and represents the fundamental steps involved in key rolling.

```pseudocode
currentKey = nextKey
nextKey = generateNewKey()
```

--------------------------------

### Bash - Publish a Message to QStash

Source: https://upstash.com/docs/qstash/quickstarts/deno-deploy

This bash script demonstrates how to publish a message to QStash using `curl`. It sends a POST request to the QStash publish endpoint with a JSON payload. The request requires an Authorization header with a Bearer token and a Content-Type header set to application/json. Replace `<QSTASH_TOKEN>` with your actual QStash token and the URL with your Deno deploy project's public URL.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://early-frog-33.deno.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### Configure QStash Client with Custom Retries (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes the QStash client with custom retry settings, including the number of retries and a custom exponential backoff function. This allows fine-grained control over request resilience. The client can also be configured to disable retries completely.

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

--------------------------------

### Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/authentication

Explains how to authenticate API requests by passing the `qstash_token` as a query parameter, useful in environments where headers are not accessible.

```APIDOC
## Query Parameter Authentication

### Description
When setting request headers is not feasible, authenticate your QStash API requests by appending the `qstash_token` as a query parameter to your request URL.

### Method
POST (example, actual method depends on the endpoint)

### Endpoint
`https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>` (example, actual endpoint depends on the operation)

### Parameters
#### Path Parameters
None

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.

#### Request Body
None (for authentication itself, actual requests will have bodies)

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
Depends on the specific API endpoint called.

#### Response Example
```json
{
  "message": "Request successful"
}
```
```

--------------------------------

### QStash Environment Variables for Next.js

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This snippet shows the necessary environment variables to configure QStash in a Next.js project. These include the QStash token and signing keys, which are essential for authenticating with the QStash service and verifying incoming messages.

```bash
# Copy all three from your QStash dashboard
QSTASH_TOKEN=
QSTASH_CURRENT_SIGNING_KEY=
QSTASH_NEXT_SIGNING_KEY=
```

--------------------------------

### Create Next.js UI for Background Job Trigger

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This TypeScript code defines the main page of a Next.js application, featuring a button to initiate a background job. It uses client-side rendering and expects a `handleClick` function to be defined for button clicks. The `use client` directive is essential for interactivity.

```tsx
"use client"

export default function Home() {
  return (
    <main className="flex h-lvh items-center justify-center">
      <button
        onClick={handleClick}
        className="btn btn-primary w-1/2 h-56 bg-green-500 text-xl sm:text-3xl rounded-lg hover:bg-green-600"
      >
        Start Background Job
      </button>
    </main>
  )
}
```

--------------------------------

### Upstash Workflow - Create Workflow

Source: https://upstash.com/docs/qstash/overall/llms-txt

Build durable workflows with step-based execution that automatically recovers from failures.

```APIDOC
## POST /api/workflow

### Description
Build durable workflows with step-based execution that automatically recovers from failures.

### Method
POST

### Endpoint
/api/workflow

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **userId** (string) - Required - The ID of the user.
- **email** (string) - Required - The email address of the user.
- **name** (string) - Required - The name of the user.

### Request Example (Next.js)
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

### Response
#### Success Response (200)
- **workflowRunId** (string) - The ID of the workflow run.

#### Response Example
```json
{
  "workflowRunId": "wf_abc123"
}
```
```

--------------------------------

### Manual QStash Signature Verification

Source: https://upstash.com/docs/qstash/howto/signature

This section outlines the steps for manually verifying QStash request signatures without using the SDKs.

```APIDOC
## Manual Verification

If you don't want to use the SDKs, you can implement your own verifier either by using an open-source library or by manually processing the JWT.

The exact implementation depends on the language of your choice and the library if you use one. Instead here are the steps you need to follow:

1.  Split the JWT into its header, payload and signature
2.  Verify the signature
3.  Decode the payload and verify the claims
    *   `iss`: The issuer must be `Upstash`.
    *   `sub`: The subject must the url of your API.
    *   `exp`: Verify the token has not expired yet.
    *   `nbf`: Verify the token is already valid.
    *   `body`: Hash the raw request body using `SHA-256` and compare it with the `body` claim.

You can also reference the implementation in our [Typescript SDK](https://github.com/upstash/sdk-qstash-ts/blob/main/src/receiver.ts#L82).

After you have verified the signature and the claims, you can be sure the request came from Upstash and process it accordingly.
```

--------------------------------

### Publishing Messages with Callbacks (cURL, TypeScript, Python)

Source: https://upstash.com/docs/qstash/features/callbacks

Demonstrates how to publish messages with a callback URL using cURL, the Upstash QStash TypeScript client, and the Python client. The 'Upstash-Callback' header or callback option is used to specify the URL where delivery status notifications should be sent. Ensure the callback URL is valid and accessible.

```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api... \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  callback: "https://my-callback...",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    callback="https://my-callback...",
)
```

--------------------------------

### Next.js Frontend Page Component

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This component provides a button to trigger a background job. It uses React's useState hook to manage loading and message states, and calls the `startBackgroundJob` server action. It's designed for a Next.js application.

```tsx
"use client"
import { startBackgroundJob } from "@/app/actions";
import { useState } from "react";

export default function Home() {
  const [loading, setLoading] = useState(false);
  const [msg, setMsg] = useState("");

    async function handleClick() {
      setLoading(true);
      const messageId = await startBackgroundJob();
      if (messageId) {
        setMsg(`Started job with ID ${messageId}`);
      } else {
        setMsg("Failed to start background job");
      }
      setLoading(false);
    }

    return (
      <main className="flex flex-col h-lvh items-center justify-center">
        <button onClick={handleClick} disabled={loading} className="btn btn-primary w-1/2 h-56 bg-green-500 text-xl sm:text-3xl rounded-lg hover:bg-green-600 disabled:bg-gray-500">
          Start Background Job
        </button>

        {loading && <div className="text-2xl mt-8">Loading...</div>}
        {msg && <p className="text-center text-lg">{msg}</p>}
      </main>
    );

  }


```

--------------------------------

### Initializing QStash Receiver (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Initializes a new `Receiver` instance with the provided signing keys from the environment variables. This instance will be used to verify incoming webhook signatures.

```typescript
const receiver = new Receiver({
  currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
  nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
});
```

--------------------------------

### Schedules API with Timezone

Source: https://upstash.com/docs/qstash/features/schedules

Demonstrates how to create a schedule with a specific timezone using the QStash client in TypeScript, Python, and cURL.

```APIDOC
## Schedules API with Timezone

### Description
This endpoint allows you to create a schedule for asynchronous task execution. You can specify a timezone for the cron expression to control when the task runs.

### Method
POST

### Endpoint
/v2/schedules

### Parameters
#### Query Parameters
- **destination** (string) - Required - The URL to which the task will be sent.
- **cron** (string) - Required - The cron expression defining the schedule. Use `CRON_TZ=[Timezone]` prefix to specify a timezone (e.g., `CRON_TZ=America/New_York 0 4 * * *`).

### Request Body
* **body** (object) - Optional - The payload to send with the request.
  - **field** (any) - Description

### Request Example
#### TypeScript
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "CRON_TZ=America/New_York 0 4 * * *",
});
```

#### Python
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="CRON_TZ=America/New_York 0 4 * * *",
)
```

#### cURL
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: CRON_TZ=America/New_York 0 4 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

### Response
#### Success Response (200)
- **scheduleId** (string) - The unique identifier for the created schedule.

#### Response Example
```json
{
  "scheduleId": "schedule_abc123"
}
```
```

--------------------------------

### Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/authentication

Demonstrates how to authenticate API requests using a Bearer Token in the Authorization header.

```APIDOC
## Bearer Token Authentication

### Description
Authenticate your requests to the QStash API by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer token.

### Method
POST (example, actual method depends on the endpoint)

### Endpoint
`https://qstash.upstash.io/v2/publish/...` (example, actual endpoint depends on the operation)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None (for authentication itself, actual requests will have bodies)

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/ப்புகளை\
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
Depends on the specific API endpoint called.

#### Response Example
```json
{
  "message": "Request successful"
}
```
```

--------------------------------

### Set Upstash QStash Signing Keys on fly.io

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Sets the Qstash signing keys as secrets for the fly.io application using the `flyctl secrets set` command. These environment variables (`QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY`) are crucial for the webhook signature verification process within the Golang application.

```bash
flyctl secrets set QSTASH_CURRENT_SIGNING_KEY=...
flyctl secrets set QSTASH_NEXT_SIGNING_KEY=...
```

--------------------------------

### Publish JSON Message using Upstash QStash Library (Python)

Source: https://upstash.com/docs/qstash/howto/publishing

Illustrates how to publish a JSON message using the Upstash QStash Python library. It shows client initialization with an API token, and then uses the `publish_json` method to send the message, specifying the URL, body as a Python dictionary, and custom headers.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    headers={
        "my-header": "my-value",
    },
)
```

--------------------------------

### Publishing LLM Requests with Anthropic

Source: https://upstash.com/docs/qstash/integrations/anthropic

Demonstrates how to publish an LLM request to Anthropic using QStash. Specify `api` as `llm` with the `anthropic()` provider and use the `Upstash-Callback` header for asynchronous responses.

```APIDOC
## POST /publish

### Description
Publishes an LLM request to Anthropic through QStash, allowing for asynchronous processing and callback handling.

### Method
POST

### Endpoint
/v2/publish

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API and provider.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Anthropic provider configuration.
    - **token** (string) - Required - Your Anthropic API token.
- **body** (object) - Required - The LLM request payload for Anthropic.
  - **model** (string) - Required - The Anthropic model to use (e.g., "claude-3-5-sonnet-20241022").
  - **messages** (array) - Required - An array of message objects for the chat conversation.
- **callback** (string) - Optional - URL to send the LLM response to asynchronously.

### Request Example
```json
{
  "api": {
    "name": "llm",
    "provider": {
      "name": "anthropic",
      "token": "<ANTHROPIC_TOKEN>"
    }
  },
  "body": {
    "model": "claude-3-5-sonnet-20241022",
    "messages": [{"role": "user", "content": "Summarize recent tech trends."}]
  },
  "callback": "https://example.com/callback"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Build and Zip Script for AWS Lambda Deployment

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This script, added to your package.json, automates the build process for your AWS Lambda deployment. It uses esbuild to bundle and minify your TypeScript code into a single JavaScript file, then creates a zip archive of the output for easy upload to AWS Lambda.

```json
{
  "scripts": {
    "build": "rm -rf ./dist; esbuild index.ts --bundle --minify --sourcemap --platform=node --target=es2020 --outfile=dist/index.js && cd dist && zip -r index.zip index.js*"
  }
}
```

--------------------------------

### Python HTTP Server for Public Endpoint

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Exposes the Redis cleanup logic as a public HTTP POST endpoint using Python's built-in 'http.server' module. This allows external services like QStash to trigger the cleanup. It inherits from BaseHTTPRequestHandler and implements the do_POST method.

```python
from http.server import BaseHTTPRequestHandler
from upstash_redis import Redis

redis = Redis(url="https://YOUR_REDIS_URL", token="YOUR_TOKEN")

def delete_all_entries():
  keys = redis.keys("*") # Match all keys
  redis.delete(*keys)


class handler(BaseHTTPRequestHandler):
  def do_POST(self):
    delete_all_entries()
    self.send_response(200)
    self.end_headers()
```

--------------------------------

### Send Single Email with Resend using qstash-js

Source: https://upstash.com/docs/qstash/integrations/resend

Demonstrates how to send a single email using the qstash-js SDK and the Resend provider. Requires QSTASH_TOKEN and RESEND_TOKEN. The body accepts parameters supported by the Resend Send Email API.

```typescript
import { Client, resend } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
  api: {
    name: "email",
    provider: resend({ token: "<RESEND_TOKEN>" }),
  },
  body: {
    from: "Acme <onboarding@resend.dev>",
    to: ["delivered@resend.dev"],
    subject: "Hello World",
    html: "<p>It works!</p>",
  },
});
```

--------------------------------

### List Schedules (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves a list of all active schedules and their configurations from Upstash QStash using a cURL command. Requires a QSTASH_TOKEN.

```bash
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Authentication using Query Parameter

Source: https://upstash.com/docs/qstash/api/flow-control/get

If setting headers is not possible, you can authenticate by appending your QSTASH_TOKEN as a query parameter named `qstash_token` to your API requests.

```APIDOC
## Authenticate API Requests with Query Parameter

### Description
When it's not feasible to set an HTTP header, you can authenticate your requests by including your `QSTASH_TOKEN` as a query parameter named `qstash_token` directly in the URL.

### Method
Any (e.g., GET, POST, PUT, DELETE)

### Endpoint
Any Qstash API endpoint

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your Qstash authentication token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/your-topic-or-endpoint?qstash_token=YOUR_QSTASH_TOKEN
```

### Response
#### Success Response (200 OK)
Responses will vary depending on the specific endpoint, but a successful authentication will allow access to the requested resource.

#### Response Example
(Varies by endpoint)
```

--------------------------------

### List Schedules (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves a list of all active schedules using the Upstash QStash client for Python and prints their IDs and cron configurations. Requires a QSTASH_TOKEN.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
schedules = client.schedule.list()

for schedule in schedules:
    print(f"Schedule {schedule['scheduleId']}: {schedule['cron']}")
```

--------------------------------

### Golang: QStash Webhook Receiver Imports

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Imports necessary Go packages for handling HTTP requests, reading request bodies, cryptographic operations (SHA256, Base64), JWT parsing, and accessing environment variables for webhook signature verification.

```go
package main

import (
	"crypto/sha256"
	"encoding/base64"
	"fmt"
	"github.com/golang-jwt/jwt/v4"
	"io"
	"net/http"
	"os"
	"time"
)
```

--------------------------------

### Trigger Workflow (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initiate a workflow execution using the Upstash Workflow client in TypeScript. This client allows triggering workflows by providing the target URL, request payload, headers, and optional parameters like a custom workflow run ID and retry count.

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

--------------------------------

### Create a Schedule to a Specific URL

Source: https://upstash.com/docs/qstash/features/schedules

This snippet demonstrates how to create a schedule to publish a message to a specific URL at a recurring interval defined by a cron expression. It utilizes the Upstash QStash client libraries for TypeScript and Python, as well as a cURL command for direct API interaction. Ensure you replace placeholders like '<QSTASH_TOKEN>' and '<URL>' with your actual credentials and destination.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="* * * * *",
)
```

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

### Add Success and Failure Callbacks (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a message with specified success and failure callback URLs using a cURL command. This allows receiving responses from long-running endpoints without blocking. Requires QSTASH_TOKEN.

```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api.example.com \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: https://my-app.example.com/callback' \
  -H 'Upstash-Failure-Callback: https://my-app.example.com/failure' \
  -d '{ "hello": "world" }'
```

--------------------------------

### Publishing a Message with Failure Callback

Source: https://upstash.com/docs/qstash/features/callbacks

Demonstrates how to publish a message with a failure callback URL using cURL, TypeScript, and Python.

```APIDOC
## POST /v2/publish/<DESTINATION_URL>

### Description
Publishes a message to a specified destination URL and configures a failure callback URL.

### Method
POST

### Endpoint
`/v2/publish/<DESTINATION_URL>`

### Parameters
#### Headers
- **Content-Type** (string) - Required - `application/json`
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`
- **Upstash-Failure-Callback** (string) - Optional - The URL to send a callback to if the message delivery fails after all retries.

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example (cURL)
```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

### Request Example (TypeScript)
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  failureCallback: "https://my-callback...",
});
```

### Request Example (Python)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    failure_callback="https://my-callback...",
)
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_xxx"
}
```
```

--------------------------------

### Publish Message with Failure Callback

Source: https://upstash.com/docs/qstash/howto/handling-failures

Publish a message to QStash and specify a URL to be called if the message fails to be delivered. This allows for custom failure handling logic such as logging or alerting. Supported by cURL, TypeScript, and Python.

```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  failureCallback: "https://my-callback...",
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    failure_callback="https://my-callback...",
)
```

--------------------------------

### Create Schedule

Source: https://upstash.com/docs/qstash/features/schedules

Creates a new schedule to publish a message at a specified cron interval. You can schedule to a specific URL, a URL group, or add to a queue. Existing schedules can be overwritten by providing a `scheduleId`.

```APIDOC
## POST /v2/schedules/{destination}

### Description
Creates a schedule to publish a message periodically based on a cron expression.

### Method
POST

### Endpoint
`/v2/schedules/{destination}`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL to send the message to, a URL group name/ID, or a queue name.

#### Headers
- **Upstash-Cron** (string) - Required - The cron expression defining the schedule's timing.
- **Upstash-Schedule-Id** (string) - Optional - An existing schedule ID to overwrite.
- **Upstash-Queue-Name** (string) - Optional - The name of the queue to add the message to.
- **Authorization** (string) - Required - Bearer token for authentication.

#### Request Body
- **(object)** - Optional - Any additional data to send with the message.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **scheduleId** (string) - The ID of the created or updated schedule.

#### Response Example
```json
{
  "scheduleId": "yourScheduleId"
}
```
```

--------------------------------

### Configure Queue Parallelism (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Configures the parallelism for a queue using the Upstash QStash client for Python. Requires a QSTASH_TOKEN and queue name to set the concurrency limit.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.upsert("my-queue", parallelism=5)

# Check queue configuration
config = client.queue.get("my-queue")
print(f"Queue parallelism: {config['parallelism']}")
```

--------------------------------

### Configure Queue Parallelism (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Sets or updates the parallelism limit for a queue using a cURL command. Requires a QSTASH_TOKEN, queue name, and the desired parallelism level.

```bash
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue",
    "parallelism": 5
  }'
```

--------------------------------

### Schedules API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Manage schedules with timezone support and retrieve a list of all active schedules.

```APIDOC
## POST /v2/schedules/{destination}

### Description
Creates a schedule that runs at a specific time, supporting timezone configuration using the `CRON_TZ` prefix.

### Method
POST

### Endpoint
`/v2/schedules/{destination}`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL to send the scheduled message to.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Cron** (string) - Required - The CRON expression with optional `CRON_TZ` prefix for timezone.
- **Content-Type** (string) - Required - `application/json`

#### Request Body
- **body** (object) - Required - The JSON payload to send with the scheduled message.

### Request Example
```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json"
    -H "Upstash-Cron: CRON_TZ=America/New_York 0 4 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message.

#### Response Example
```json
{
  "message": "Schedule created successfully."
}
```

## GET /v2/schedules

### Description
Retrieves a list of all active schedules and their configurations.

### Method
GET

### Endpoint
`/v2/schedules`

### Parameters
#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example
```bash
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
- **schedules** (array) - An array of schedule objects.
  - **scheduleId** (string) - The unique identifier for the schedule.
  - **cron** (string) - The CRON expression for the schedule.
  - **destination** (string) - The URL the schedule sends messages to.

#### Response Example
```json
{
  "schedules": [
    {
      "scheduleId": "sched_123",
      "cron": "CRON_TZ=America/New_York 0 4 * * *",
      "destination": "https://example.com"
    }
  ]
}
```
```

--------------------------------

### Combine Rate, Parallelism, and Period Limits (TypeScript, cURL)

Source: https://upstash.com/docs/qstash/features/flowcontrol

This snippet demonstrates combining rate, parallelism, and period limits for QStash Flow Control. It allows you to specify the maximum number of calls within a time window (`rate` and `period`) and the maximum number of concurrent active calls (`parallelism`) simultaneously. The `USER_GIVEN_KEY` is used to apply these combined settings.

```TypeScript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, parallelism: 20, period: "1m" },
});
```

```cURL
curl -XPOST -H 'Authorization: Bearer XXX' \
              -H "Content-type: application/json" \
              -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
              -H "Upstash-Flow-Control-Value:rate=10,parallelism=20,period=1m" \
             'https://qstash.upstash.io/v2/publish/https://example.com' \
              -d '{"message":"Hello, World!"}'
```

--------------------------------

### Queues API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Manage queues for guaranteed FIFO message delivery and configure queue parallelism.

```APIDOC
## POST /v2/enqueue/{queueName}/{destination}

### Description
Enqueues a message to a specified queue for guaranteed FIFO (first-in-first-out) delivery.

### Method
POST

### Endpoint
`/v2/enqueue/{queueName}/{destination}`

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue.
- **destination** (string) - Required - The URL to send the message to.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - `application/json`

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```bash
curl -XPOST -H 'Authorization: Bearer <QSTASH_TOKEN>'
            -H "Content-type: application/json"
            'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com'
            -d '{"message":"Hello, World!"}'
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the enqueued message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```

## POST /v2/queues/

### Description
Configures or updates the parallelism settings for a queue.

### Method
POST

### Endpoint
`/v2/queues/`

### Parameters
#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - `application/json`

#### Request Body
- **queueName** (string) - Required - The name of the queue.
- **parallelism** (integer) - Required - The maximum number of concurrent messages to process.

### Request Example
```bash
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue",
    "parallelism": 5
  }'
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message.

#### Response Example
```json
{
  "message": "Queue configuration updated."
}
```
```

--------------------------------

### Next.js Server Action to Publish to QStash

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This server action uses the `@upstash/qstash` client to publish a JSON message to a specified URL. It requires the QSTASH_TOKEN environment variable to be set. The function returns a response object which includes the message ID upon successful publishing.

```ts
"use server"
import { Client } from "@upstash/qstash";

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!,
});

export async function startBackgroundJob() {
  try {
    const response = await qstashClient.publishJSON({
      "url": "https://qstash-bg-job.vercel.app/api/long-task",
      body: {
        "hello": "world"
      }
    });

```

--------------------------------

### Publish a Message to QStash

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

This section details how to publish a message to Upstash QStash using a cURL request.

```APIDOC
## Publish a Message

Publish messages to QStash using the `/v2/publish` endpoint.

### Method

`POST`

### Endpoint

`https://qstash.upstash.io/v2/publish/<YOUR_APP_PUBLIC_URL>`

### Parameters

#### Path Parameters

- **YOUR_APP_PUBLIC_URL** (string) - Required - The public URL of your deployed application (e.g., `https://your-app-name.fly.dev`).

#### Headers

- **Authorization** (string) - Required - Bearer token for authentication (`Bearer <QSTASH_TOKEN>`)
- **Content-Type** (string) - Required - `application/json`

#### Request Body

- **(any JSON object)** - Required - The message payload to be published.

### Request Example

```json
{
  "hello": "world"
}
```

### cURL Example

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://winter-cherry-9545.fly.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{\"hello\": \"world\"}"
```

### Response

#### Success Response (200 OK)

Indicates the message was successfully published to QStash.

#### Response Example

```json
{
  "messageId": "msg_xxxxxx"
}
```
```

--------------------------------

### Send Batch Emails with Resend using qstash-js

Source: https://upstash.com/docs/qstash/integrations/resend

Shows how to send multiple emails in a single request using the qstash-js SDK with Resend's batch functionality. Set `batch: true` in the provider options. The body is an array of email configurations.

```typescript
await client.publishJSON({
  api: {
    name: "email",
    provider: resend({ token: "<RESEND_TOKEN>", batch: true }),
  },
  body: [
    {
      from: "Acme <onboarding@resend.dev>",
      to: ["foo@gmail.com"],
      subject: "Hello World",
      html: "<h1>It works!</h1>",
    },
    {
      from: "Acme <onboarding@resend.dev>",
      to: ["bar@outlook.com"],
      subject: "World Hello",
      html: "<p>It works!</p>",
    },
  ],
});
```

--------------------------------

### Publish Chat Completion Request using QStash

Source: https://upstash.com/docs/qstash/integrations/llm

Publishes a single chat completion request to an LLM API via QStash. It requires QStash and LLM API tokens, the message body, and a callback URL for asynchronous processing. This method is suitable for immediate, non-queued LLM calls.

```javascript
import { Client, upstash } from "@upstash/qstash";

const client = new Client({
    token: "<QSTASH_TOKEN>",
});

const result = await client.publishJSON({
    api: { name: "llm", provider: openai({ token: "_OPEN_AI_TOKEN_"}) },
    body: {
        model: "gpt-3.5-turbo",
        messages: [
            {
            role: "user",
            content: "Write a hello world program in Rust.",
            },
        ],
    },
    callback: "https://abc.requestcatcher.com/",
});

console.log(result);
```

```python
from qstash import QStash
from qstash.chat import upstash

q = QStash("<QSTASH_TOKEN>")

result = q.message.publish_json(
    api={"name": "llm", "provider": openai("<OPENAI_API_KEY>")},
    body={
        "model": "gpt-3.5-turbo",
        "messages": [
            {
                "role": "user",
                "content": "Write a hello world program in Rust.",
            }
        ],
    },
    callback="https://abc.requestcatcher.com/",
)

print(result)
```

--------------------------------

### Schedule with Timezone Support (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Schedules a message to be sent at a specific time in a given timezone using the CRON_TZ prefix. Requires a QSTASH_TOKEN and specifies the destination URL and the cron schedule.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json" \
    -H "Upstash-Cron: CRON_TZ=America/New_York 0 4 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

### Initialize Upstash QStash client in Next.js server action

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This TypeScript code initializes the Upstash QStash client within a Next.js server action. It requires the QSTASH_TOKEN environment variable for authentication. This client is then used to interact with the QStash service for managing background jobs.

```typescript
import { Client } from "@upstash/qstash"

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!,
})

export async function startBackgroundJob() {
```

--------------------------------

### Enqueue Messages for Ordered Delivery (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Sends a message to a specific queue for guaranteed FIFO (first-in-first-out) delivery using a cURL command. Requires a QSTASH_TOKEN, queue name, destination URL, and the message payload.

```bash
curl -XPOST -H 'Authorization: Bearer <QSTASH_TOKEN>'
            -H "Content-type: application/json" 
            'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' \
            -d '{"message":"Hello, World!"}'
```

--------------------------------

### POST /v2/schedules/:url

Source: https://upstash.com/docs/qstash/overall/llms-txt

Create a recurring schedule to send messages to a destination URL at specified intervals using cron expressions.

```APIDOC
## POST /v2/schedules/:url

### Description
Creates a recurring schedule to send messages to a destination URL. Messages are sent based on a defined cron expression.

### Method
POST

### Endpoint
`/v2/schedules/:url`

### Parameters
#### Path Parameters
- **url** (string) - Required - The destination URL for the scheduled messages.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication (`Bearer <QSTASH_TOKEN>`)
- **Content-type** (string) - Required - Set to `application/json` for JSON payloads.
- **Upstash-Cron** (string) - Required - The cron expression defining the schedule (e.g., `0 0 * * *` for midnight UTC daily).

#### Request Body
- **body** (object) - Optional - The JSON payload to send with each scheduled message. If not provided, an empty JSON object `{}` is sent.

### Request Example
```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: 0 0 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

### Response
#### Success Response (200)
- **scheduleId** (string) - The unique identifier for the created schedule.

#### Response Example
```json
{
  "scheduleId": "sch_xyz789"
}
```
```

--------------------------------

### Schedule with Timezone Support (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Creates a schedule for sending messages with timezone support using the Upstash QStash client for TypeScript. Requires a QSTASH_TOKEN, destination URL, and a cron string with timezone.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "CRON_TZ=America/New_York 0 4 * * *", // 4 AM New York time
});
```

--------------------------------

### List Schedules (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Fetches all active schedules using the Upstash QStash client for TypeScript and iterates through them, logging their IDs and cron configurations. Requires a QSTASH_TOKEN.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const schedules = await client.schedules.list();

for (const schedule of schedules) {
  console.log(`Schedule ${schedule.scheduleId}: ${schedule.cron}`);
}
```

--------------------------------

### Background Job Logic API Endpoint

Source: https://upstash.com/docs/qstash/features/background-jobs

This TypeScript API endpoint is designed to be invoked by QStash to perform the actual background job. It receives a list of users and iterates through them to send emails using a hypothetical 'sendEmail' function. This endpoint should contain the potentially long-running logic.

```typescript
// This is a public API endpoint that will be invoked by QStash.
// It contains the logic for the background job and may take a long time to execute.
import { sendEmail } from "your-email-library";

export async function POST(request: Request) {
  const body = await request.json();
  const users: string[] = body.users;

  // Send emails to the users
  for (const user of users) {
    await sendEmail(user);
  }

  return new Response("Job started", { status: 200 });
}

```

--------------------------------

### Receiving Messages

Source: https://upstash.com/docs/qstash/howto/receiving

When a message is published, QStash delivers it to your specified destination. This section details the structure of the HTTP request your API will receive, including custom and standard headers, and the message body.

```APIDOC
## Receiving Messages

### Description
This endpoint describes how QStash delivers messages to your API. It details the headers and body format of the incoming request.

### Method
POST (Implied, as QStash is sending data to your API)

### Endpoint
Your registered webhook endpoint

### Headers
QStash forwards headers prefixed with `Upstash-Forward-` and includes several standard headers:

- `User-Agent` (string) - Set to `Upstash-QStash`
- `Content-Type` (string) - The original `Content-Type` header of the published message
- `Upstash-Topic-Name` (string) - The URL Group (topic) name, if applicable
- `Upstash-Signature` (string) - Signature for verifying the message origin
- `Upstash-Retried` (integer) - Number of retries performed (starts at 0)
- `Upstash-Message-Id` (string) - The unique ID of the message
- `Upstash-Schedule-Id` (string) - The ID of the schedule, if the message is schedule-related
- `Upstash-Caller-Ip` (string) - The IP address of the message publisher

### Request Body
- **body** (any) - The message body is delivered as is, without modification. The format (JSON, string, etc.) matches what was originally sent by the publisher.

### Response
- **Status Code**: QStash expects a successful HTTP status code (e.g., 2xx) to acknowledge successful message delivery. Non-2xx status codes may trigger retries.

### Signature Verification
- Refer to the [QStash signature documentation](/qstash/howto/signature) for detailed instructions on how to verify incoming message signatures.
```

--------------------------------

### POST /v2/topics/:urlGroupName/endpoints

Source: https://upstash.com/docs/qstash/howto/url-group-endpoint

Create a URL Group and add multiple endpoints to it using the QStash REST API. A URL Group allows you to namespace multiple APIs together.

```APIDOC
## POST /v2/topics/:urlGroupName/endpoints

### Description
Creates a URL Group (if it doesn't exist) and adds the specified endpoints to it. URL Groups help in organizing multiple APIs under a single namespace.

### Method
POST

### Endpoint
`/v2/topics/:urlGroupName/endpoints`

### Parameters
#### Path Parameters
- **urlGroupName** (string) - Required - The name of the URL Group to create or update.

#### Query Parameters
None

#### Request Body
- **endpoints** (array) - Required - A list of endpoint objects to add to the URL Group.
  - **name** (string) - Required - The name of the endpoint.
  - **url** (string) - Required - The URL of the endpoint.

### Request Example
```json
{
  "endpoints": [
    {
      "name": "endpoint1",
      "url": "https://example.com"
    },
    {
      "name": "endpoint2",
      "url": "https://somewhere-else.com"
    }
  ]
}
```

### Response
#### Success Response (200 OK)
This endpoint typically returns a 200 OK status upon successful creation or update. Specific response body details may vary, but it usually indicates success.

#### Response Example
(No specific response body example provided in the source documentation, but success is indicated by a 200 status code.)

### Example Usage (cURL)
```bash
curl -XPOST https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "endpoints": [
      {
        "name": "endpoint1",
        "url": "https://example.com"
      },
      {
        "name": "endpoint2",
        "url": "https://somewhere-else.com"
      }
    ]
  }'
```

### Example Usage (TypeScript)
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.addEndpoints({
  name: "urlGroupName",
  endpoints: [
    { name: "endpoint1", url: "https://example.com" },
    { name: "endpoint2", url: "https://somewhere-else.com" },
  ],
});
```

### Example Usage (Python)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.url_group.upsert_endpoints(
    url_group="url-group-name",
    endpoints=[
        {"name": "endpoint1", "url": "https://example.com"},
        {"name": "endpoint2", "url": "https://somewhere-else.com"},
    ],
)
```
```

--------------------------------

### Schedule with Timezone Support (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Schedules a message with timezone support using the Upstash QStash client for Python. Requires a QSTASH_TOKEN, destination URL, and a cron string specifying the timezone.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="CRON_TZ=America/New_York 0 4 * * *",
)
```

--------------------------------

### Publish Message with Delay and Custom Headers

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publish a JSON message with a specified delay and custom headers. The delay is defined in minutes, and custom headers are forwarded to the target endpoint. Requires a QStash token and the target URL.

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

--------------------------------

### POST /api/callback

Source: https://upstash.com/docs/qstash/overall/llms-txt

Handles callback responses from Upstash QStash in a Next.js application. It includes signature verification to ensure the authenticity of incoming payloads. The callback body contains details about the message status, headers, encoded body, retry information, and source message details.

```APIDOC
## POST /api/callback

### Description
Handles callback responses from Upstash QStash in a Next.js application. It includes signature verification to ensure the authenticity of incoming payloads. The callback body contains details about the message status, headers, encoded body, retry information, and source message details.

### Method
POST

### Endpoint
/api/callback

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **status** (number) - The HTTP status code of the callback response.
- **header** (object) - Headers associated with the callback response.
- **body** (string) - The base64 encoded body of the callback response.
- **retried** (number) - The number of times the message has been retried.
- **maxRetries** (number) - The maximum number of retries allowed.
- **sourceMessageId** (string) - The ID of the original message.
- **url** (string) - The URL that received the callback.
- **method** (string) - The HTTP method used for the callback.
- **sourceHeader** (object) - Headers from the original source.
- **sourceBody** (string) - The base64 encoded body from the original source.
- **createdAt** (string) - The timestamp when the callback was created.

### Request Example
```json
{
  "status": 200,
  "header": { "key": ["value"] },
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==",
  "retried": 2,
  "maxRetries": 3,
  "sourceMessageId": "msg_xxx",
  "url": "http://myurl.com",
  "method": "GET",
  "sourceHeader": { "key": "value" },
  "sourceBody": "YmFzZTY0kZWQgcm9keQ==",
  "createdAt": "1701198447054"
}
```

### Response
#### Success Response (200)
Returns a 200 OK status to acknowledge the callback processing.

#### Response Example
(No content)
```

--------------------------------

### Configure Queue Parallelism (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Configures the parallelism for a queue using the Upstash QStash client for TypeScript. Allows setting the number of concurrent messages processed. Requires a QSTASH_TOKEN and queue name.

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

--------------------------------

### Publish Webhook Receiver

Source: https://upstash.com/docs/qstash/howto/webhook

Configure your webhook URL as a QStash publish request to act as an intermediary. This allows for additional control over webhook requests such as delay, retries, and timeouts.

```APIDOC
## POST /v2/publish/{webhook_url}

### Description
Publish a message to a specified webhook URL via QStash.

### Method
POST

### Endpoint
`/v2/publish/{webhook_url}`

### Parameters
#### Path Parameters
- **webhook_url** (string) - Required - The URL of your webhook endpoint.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.
- **upstash-retries** (integer) - Optional - Number of retries for the request.
- **upstash-delay** (string) - Optional - Delay before sending the request (e.g., "100s").
- **upstash-header-forward** (boolean) - Optional - Whether to forward all incoming request headers.

#### Request Body
- **body** (object) - Optional - The payload to send to the webhook.

### Request Example
```json
{
  "body": {
    "message": "Hello, QStash!"
  }
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Publish JSON Message to QStash

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This code snippet shows how to publish a JSON message to a QStash background job. It requires the `@upstash/qstash` SDK and a QStash client initialized with an API token. The `publishJSON` method takes a URL and a message body as input and returns a promise that resolves with the message ID.

```typescript
import { Client } from "@upstash/qstash";

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!,
});

export async function startBackgroundJob() {
  try {
    const response = await qstashClient.publishJSON({
      "url": "https://qstash-bg-job.vercel.app/api/long-task",
      body: {
        "hello": "world"
      }
    });
    return response.messageId;
  } catch (error) {
    console.error(error);
    return null;
  }
}
```

--------------------------------

### Publishing a Message with Failure Callback

Source: https://upstash.com/docs/qstash/howto/handling-failures

This endpoint allows you to publish a message to a destination URL and specify a failure callback URL. If the message fails to be published, the specified callback URL will be invoked.

```APIDOC
## POST /v2/publish/<DESTINATION_URL>

### Description
Publishes a message to a given URL and optionally provides a callback URL to be invoked upon failure.

### Method
POST

### Endpoint
`/v2/publish/<DESTINATION_URL>`

### Parameters
#### Path Parameters
- **DESTINATION_URL** (string) - Required - The URL to which the message will be published.

#### Headers
- **Content-Type** (string) - Required - Set to `application/json`.
- **Authorization** (string) - Required - Bearer token for authentication (e.g., `Bearer <QSTASH_TOKEN>`).
- **Upstash-Failure-Callback** (string) - Optional - The URL to call if the message fails to publish.

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Upsert Queue Configuration

Source: https://upstash.com/docs/qstash/features/queues

Configure or update queue settings, such as parallelism. This allows for controlled throughput by defining how many messages can be processed concurrently.

```APIDOC
## POST /v2/queues/

### Description
Creates or updates a queue with specified configuration, including parallelism.

### Method
POST

### Endpoint
`/v2/queues/`

### Parameters
#### Request Body
- **queueName** (string) - Required - The name of the queue to create or update.
- **parallelism** (integer) - Optional - The number of concurrent messages to process. Defaults to 1.

### Request Example
```json
{
  "queueName": "my-queue",
  "parallelism": 5
}
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message indicating the queue was updated.

#### Response Example
```json
{
  "message": "Queue updated successfully"
}
```
```

--------------------------------

### POST /v2/batch

Source: https://upstash.com/docs/qstash/features/batch

Sends a batch of messages to specified destinations, URL Groups, or queues. This endpoint allows for flexible message publishing in a single API call.

```APIDOC
## POST /v2/batch

### Description
Sends a batch of messages to specified destinations, URL Groups, or queues. This endpoint allows for flexible message publishing in a single API call.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/batch

### Parameters
#### Request Body
- **Array of message objects** (array) - Required - An array where each object represents a message to be sent. Each message object can include properties like `destination`, `urlGroup`, `queue`, `url`, `body`, `method`, `headers`, `contentType`, `delay`, `notBefore`, `retries`, etc., depending on the target.

### Request Example
```json
[
  {
    "destination": "https://example.com/destination1"
  },
  {
    "destination": "myUrlGroup"
  },
  {
    "queue": "my-queue",
    "destination": "https://example.com/destination2"
  }
]
```

### Response
#### Success Response (200)
- **Array of response objects** (array) - An array containing the response for each message processed in the batch. Individual responses will indicate success or failure.

#### Response Example
```json
[
  {
    "status": 200,
    "messageId": "msg_abc123"
  },
  {
    "status": 200,
    "messageId": "msg_def456"
  },
  {
    "status": 400,
    "error": "Invalid message format"
  }
]
```
```

--------------------------------

### Publish Message using cURL

Source: https://upstash.com/docs/qstash/howto/publishing

Demonstrates how to publish a JSON message to a specified URL using cURL. This involves setting the Authorization header, custom forward headers prefixed with 'Upstash-Forward-', Content-Type, and the JSON body. The destination URL is part of the request.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

--------------------------------

### Publish Message to QStash

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Publishes a JSON message to a specified QStash endpoint. Requires a valid QStash token and the public URL of the target application. The destination URL is typically the application's name on Fly.io.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://winter-cherry-9545.fly.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### POST /v2/publish

Source: https://upstash.com/docs/qstash/overall/getstarted

Publish a message to a specified URL. The message can be in any format (JSON, XML, binary, etc.) and is limited to 1 MB.

```APIDOC
## POST /v2/publish

### Description
Publishes a message to a specified webhook URL. Supports various content types and includes an authorization token.

### Method
POST

### Endpoint
`/v2/publish/https://<your-api-url>`

### Parameters
#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the format of the message body (e.g., `application/json`).

#### Request Body
- **(any)** - Required - The message payload, which can be JSON, XML, binary, or any other format up to 1 MB in size.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200 OK)
- **messageId** (string) - A unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### POST /v2/publish/:url

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publish a JSON message to a destination URL with guaranteed delivery and automatic retries. This is the core endpoint for sending messages.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a JSON message to a specified destination URL. QStash ensures reliable delivery with automatic retries.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Path Parameters
- **url** (string) - Required - The destination URL to send the message to.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication (`Bearer <QSTASH_TOKEN>`)
- **Content-type** (string) - Required - Set to `application/json` for JSON payloads.
- **Upstash-Delay** (string) - Optional - Delay message delivery (e.g., `5m`).
- **Upstash-Forward-My-Header** (string) - Optional - Custom headers to forward to the endpoint (e.g., `Upstash-Forward-My-Header: my-value`).
- **Upstash-Retries** (integer) - Optional - Maximum number of retry attempts (e.g., `3`).
- **Upstash-Retry-Delay** (string) - Optional - Custom retry delay expression (e.g., `pow(2, retried) * 1000`).

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 5m" \
    -H "Upstash-Forward-My-Header: my-value" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Queue Image Processing Task with QStash in Next.js

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This code snippet shows how to publish a JSON message to QStash to queue an image processing task. It requires the `@upstash/qstash` client and uses environment variables for authentication. The message contains the URL of the processing endpoint and the request body with the image ID. This enables asynchronous processing and automatic retries.

```tsx
import { Client } from "@upstash/qstash"
import { NextResponse } from "next/server"

const client = new Client({ token: process.env.QSTASH_TOKEN! })

export const POST = async (req: Request) => {
  // Image uploading logic

  // 👇 Once uploading is done, queue an image processing task
  const result = await client.publishJSON({
    url: "https://your-api-endpoint.com/process-image",
    body: { imageId: "123" },
  })

  return NextResponse.json({
    message: "Image queued for processing!",
    qstashMessageId: result.messageId,
  })
}
```

--------------------------------

### Publish to QStash via CURL

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This snippet demonstrates how to send a POST request to the QStash API to publish a message. It includes setting the Authorization header with your QStash token and Content-Type to application/json, along with the message payload. Ensure you replace `<YOUR-LAMBDA-URL>` with your actual Lambda function URL and `<QSTASH-TOKEN>` with your valid QStash token.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/<YOUR-LAMBDA-URL>" \
-H "Authorization: Bearer <QSTASH-TOKEN>" \
-H "Content-Type: application/json" \
-d "{ \"hello\": \"world\"}"
```

--------------------------------

### Send Batched Anthropic LLM Requests with QStash

Source: https://upstash.com/docs/qstash/integrations/anthropic

Sends multiple LLM requests to Anthropic in a single batch using QStash's `batchJSON` function. Each request specifies the Anthropic provider and a unique callback URL for asynchronous handling.

```typescript
import { anthropic, Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const result = await client.batchJSON([
  {
    api: { name: "llm", provider: anthropic({ token: "<ANTHROPIC_TOKEN>" }) },
    body: {
      model: "claude-3-5-sonnet-20241022",
      messages: [
        {
          role: "user",
          content: "Describe the latest in AI research.",
        },
      ],
    },
    callback: "https://example.com/callback1",
  },
  {
    api: { name: "llm", provider: anthropic({ token: "<ANTHROPIC_TOKEN>" }) },
    body: {
      model: "claude-3-5-sonnet-20241022",
      messages: [
        {
          role: "user",
          content: "Outline the future of remote work.",
        },
      ],
    },
    callback: "https://example.com/callback2",
  },
  // Add more requests as needed
]);

console.log(result);
```

--------------------------------

### Add Success and Failure Callbacks (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a JSON message with specified success and failure callback URLs using the Upstash QStash client for Python. Facilitates asynchronous processing of endpoint responses. Requires QSTASH_TOKEN.

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

--------------------------------

### Batch messages to URL Groups or destinations (cURL, TypeScript, Python)

Source: https://upstash.com/docs/qstash/features/batch

Efficiently send messages to one or more URL Groups, or a mix of URL Groups and direct destinations, within a single batch request. This feature simplifies managing messages targeted at predefined URL Group configurations.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "destination": "myUrlGroup"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'

```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

// Each message is the same as the one you would send with the publish endpoint
const res = await client.batchJSON([
  {
    urlGroup: "myUrlGroup",
  },
  {
    url: "https://example.com/destination2",
  },
]);

```

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.batch_json(
    [
        {"url_group": "my-url-group"},
        {"url": "https://example.com/destination2"},
    ]
)

```

--------------------------------

### Send Chat Completion Requests in Batches using QStash

Source: https://upstash.com/docs/qstash/integrations/llm

Sends multiple chat completion requests to LLM APIs in a single batch operation using QStash. This is efficient for processing large numbers of requests simultaneously. It requires QStash token, an array of request objects, and a callback URL for each request.

```javascript
import { Client, upstash } from "@upstash/qstash";

const client = new Client({
    token: "<QSTASH_TOKEN>",
});

const result = await client.batchJSON([
    {
        api: { name: "llm", provider: openai({ token: "_OPEN_AI_TOKEN_" }) },
        body: { ... },
        callback: "https://abc.requestcatcher.com",
    },
    ...
]);

console.log(result);
```

```python
from qstash import QStash
from qstash.chat import upstash

q = QStash("<QSTASH_TOKEN>")

result = q.message.batch_json(
    [
        {
            "api":{"name": "llm", "provider": openai("<OPENAI_API_KEY>")},
            "body": {...},
            "callback": "https://abc.requestcatcher.com",
        },
        ...
    ]
)

print(result)
```

```shell
curl "https://qstash.upstash.io/v2/batch" \
    -X POST \
    -H "Authorization: Bearer QSTASH_TOKEN" \
    -H "Content-Type: application/json" \
    -d '[
        {
            "destination": "api/llm",
            "body": {...},
            "callback": "https://abc.requestcatcher.com"
        },
        ...
    ]'
```

--------------------------------

### Batch Messages with Headers and Body (Python)

Source: https://upstash.com/docs/qstash/features/batch

Utilize the QStash Python client to send batched messages, including custom headers and bodies. The `batch_json` method accepts a list of dictionaries, where each dictionary represents a message with properties such as url_group, url, delay, body, and headers. The API supports various data types for the body.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.batch_json(
    [
        {
            "url_group": "my-url-group",
            "delay": "5s",
            "body": {"hello": "world"},
            "headers": {"random": "header"},
        },
        {
            "url": "https://example.com/destination1",
            "delay": "1m",
        },
        {
            "url": "https://example.com/destination2",
            "body": {"hello": "again"},
        },
    ]
)
```

--------------------------------

### Authentication using Bearer Token

Source: https://upstash.com/docs/qstash/api/flow-control/get

Authenticate your API requests by including your QSTASH_TOKEN in the Authorization header as a Bearer token. This is the recommended method for authentication.

```APIDOC
## Authenticate API Requests with Bearer Token

### Description
This method involves including your `QSTASH_TOKEN` in the `Authorization` header of your HTTP requests. This is the standard and recommended way to authenticate with the QStash API.

### Method
Any (e.g., GET, POST, PUT, DELETE)

### Endpoint
Any Qstash API endpoint

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format "Bearer <QSTASH_TOKEN>".

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/your-topic-or-endpoint \
  -H "Authorization: Bearer YOUR_QSTASH_TOKEN"
```

### Response
#### Success Response (200 OK)
Responses will vary depending on the specific endpoint, but a successful authentication will allow access to the requested resource.

#### Response Example
(Varies by endpoint)
```

--------------------------------

### Enqueue Chat Completion Request using QStash

Source: https://upstash.com/docs/qstash/integrations/llm

Enqueues a chat completion request into a specified QStash queue for later processing. This is useful for managing workloads and decoupling LLM processing from the main application flow. It requires queue name, QStash and LLM API tokens, message body, and a callback URL.

```javascript
import { Client, upstash } from "@upstash/qstash";

const client = new Client({
    token: "<QSTASH_TOKEN>",
});

const result = await client.queue({ queueName: "queue-name" }).enqueueJSON({
    api: { name: "llm", provider: openai({ token: "_OPEN_AI_TOKEN_"}) },
    body: {
        "model": "gpt-3.5-turbo",
        messages: [
            {
                role: "user",
                content: "Write a hello world program in Rust.",
            },
        ],
    },
    callback: "https://abc.requestcatcher.com",
});

console.log(result);
```

```python
from qstash import QStash
from qstash.chat import upstash

q = QStash("<QSTASH_TOKEN>")

result = q.message.enqueue_json(
    queue="queue-name",
    api={"name": "llm", "provider": openai("<OPENAI_API_KEY>")},
    body={
        "model": "gpt-3.5-turbo",
        "messages": [
            {
                "role": "user",
                "content": "Write a hello world program in Rust.",
            }
        ],
    },
    callback="https://abc.requestcatcher.com",
)

print(result)
```

--------------------------------

### Configure Message Retries with Custom Backoff

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publish a JSON message with custom retry configurations, including the maximum number of retries and a retry delay expression. The delay expression uses mathematical functions for exponential backoff. Requires a QStash token and the target URL.

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

--------------------------------

### Callbacks API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Add success and failure callback URLs to receive notifications about message processing status.

```APIDOC
## POST /v2/publish/{destination}

### Description
Publishes a message to a destination and optionally provides callback URLs for success and failure notifications.

### Method
POST

### Endpoint
`/v2/publish/{destination}`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL to send the message to.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - `application/json`
- **Upstash-Callback** (string) - Optional - The URL to send success notifications to.
- **Upstash-Failure-Callback** (string) - Optional - The URL to send failure notifications to.

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example
```bash
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api.example.com \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: https://my-app.example.com/callback' \
  -H 'Upstash-Failure-Callback: https://my-app.example.com/failure' \
  -d '{ "hello": "world" }'
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_xyz789"
}
```
```

--------------------------------

### Batch Messages with Headers and Body (cURL)

Source: https://upstash.com/docs/qstash/features/batch

Send batched messages to QStash using cURL. This method allows specifying a destination, custom headers (like Upstash-Delay and Upstash-Forward-*), and a message body for each item in the batch. Ensure your API token is correctly set in the Authorization header.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch   -H "Authorization: Bearer XXX" \
      -H "Content-Type: application/json" \
      -d \
      '\
      [\
        {\
            "destination": "myUrlGroup",\
            "headers":{\
              "Upstash-Delay":"5s",\
              "Upstash-Forward-Hello":"123456"\
            },\
            "body": "Hello World"\
        },\
        {\"destination": "https://example.com/destination1",\
            "headers":{\
              "Upstash-Delay":"7s",\
              "Upstash-Forward-Hello":"789"\
            }\
        },\
        {\"destination": "https://example.com/destination2",\
            "headers":{\
              "Upstash-Delay":"9s",\
              "Upstash-Forward-Hello":"again"\
            }\
        }\
      ]'
```

--------------------------------

### Importing Receiver for QStash Webhooks (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Imports the `Receiver` class from the `@upstash/qstash` library. This class is essential for handling incoming webhooks and verifying their authenticity.

```typescript
import { Receiver } from "@upstash/qstash";
```

--------------------------------

### Request Authorization

Source: https://upstash.com/docs/qstash/features/security

To interact with the QStash API, you must include an authorization token in the `Authorization` header of your requests.

```APIDOC
## Request Authorization

### Description
Include your QStash token in the `Authorization` header for all API requests.

### Method
All HTTP Methods

### Endpoint
All QStash Endpoints

### Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```
Authorization: Bearer <YOUR_QSTASH_TOKEN>
```
```

--------------------------------

### Batch messages to queues or destinations (cURL, TypeScript, Python)

Source: https://upstash.com/docs/qstash/features/batch

Send messages to specific queues or destinations in a batch. This allows you to manage messages intended for different processing queues or direct endpoints simultaneously. Each message can be configured with its own queue and destination.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
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
from upstash_qstash import QStash
from upstash_qstash.message import BatchRequest

qstash = QStash("<QSTASH_TOKEN>")

messages = [
    BatchRequest(
        queue="my-queue",
        url="https://httpstat.us/200",
        body=f"hi 1",
        retries=0
    ),
    BatchRequest(
        queue="my-second-queue",
        url="https://httpstat.us/200",
        body=f"hi 2",
        retries=0
    ),
]

qstash.message.batch(messages)

```

--------------------------------

### Verify QStash Signature in Next.js App Router

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This code snippet demonstrates how to secure a Next.js API route endpoint using `verifySignatureAppRouter` from `@upstash/qstash/nextjs`. It ensures that only requests originating from QStash can invoke the handler. The handler processes incoming JSON data and simulates a long-running task by making multiple fetch requests. It expects `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY` to be set in the environment variables.

```typescript
import { verifySignatureAppRouter } from "@upstash/qstash/nextjs"

async function handler(request: Request) {
  const data = await request.json()

  for (let i = 0; i < 10; i++) {
    await fetch("https://firstqstashmessage.requestcatcher.com/test", {
      method: "POST",
      body: JSON.stringify(data),
      headers: { "Content-Type": "application/json" },
    })
    await new Promise((resolve) => setTimeout(resolve, 500))
  }

  return Response.json({ success: true })
}

export const POST = verifySignatureAppRouter(handler)
```

--------------------------------

### URL Group Webhook Receiver

Source: https://upstash.com/docs/qstash/howto/webhook

Create URL Groups to define server-side templates for publishing messages. This allows for default headers and multiple endpoints within a group for fanning out webhook calls.

```APIDOC
## POST /v2/publish/{URL_GROUP_NAME}

### Description
Publish a message to a configured URL Group. All endpoints within the group will be triggered.

### Method
POST

### Endpoint
`/v2/publish/{URL_GROUP_NAME}`

### Parameters
#### Path Parameters
- **URL_GROUP_NAME** (string) - Required - The name of the URL Group.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.

#### Request Body
- **body** (object) - Optional - The payload to send to the webhook endpoints in the group.

### Request Example
```json
{
  "body": {
    "event": "user_created",
    "userId": "user123"
  }
}
```

## PATCH /v2/topics/{URL_GROUP_NAME}

### Description
Update the configuration for a URL Group, including default headers.

### Method
PATCH

### Endpoint
`/v2/topics/{URL_GROUP_NAME}`

### Parameters
#### Path Parameters
- **URL_GROUP_NAME** (string) - Required - The name of the URL Group.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.

#### Request Body
- **headers** (object) - Optional - A map of headers to set as defaults for the URL Group. Keys should be header names (e.g., `Upstash-Header-Forward`, `Upstash-Retries`), and values should be arrays of strings.

### Request Example
```json
{
  "headers": {
    "Upstash-Header-Forward": ["true"],
    "Upstash-Retries": ["3"]
  }
}
```

### Response
#### Success Response (200)
- **message** (string) - A success message indicating the URL Group was updated.

#### Response Example
```json
{
  "message": "URL Group updated successfully."
}
```
```

--------------------------------

### Publish JSON Message to QStash in Next.js

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This TypeScript code defines a server action in a Next.js application to publish a JSON message using the Upstash QStash client. It requires the QStash token to be set in the environment variables. The `publishJSON` method sends a message to a specified URL.

```ts
"use server"
import { Client } from "@upstash/qstash"

const qstashClient = new Client({
  // Add your token to a .env file
  token: process.env.QSTASH_TOKEN!,
})

export async function startBackgroundJob() {
  await qstashClient.publishJSON({
    url: "https://firstqstashmessage.requestcatcher.com/test",
    body: {
      hello: "world",
    },
  })
}
```

--------------------------------

### Publish Message with Custom Retries

Source: https://upstash.com/docs/qstash/features/retry

Demonstrates how to publish a JSON message with a specified number of retries using cURL, TypeScript, and Python. This controls how many times QStash will attempt to redeliver a message if the initial delivery fails.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 2" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    retries: 2,
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    retries=2,
)
```

--------------------------------

### Verify JWT Signature with QStash SDK (Golang)

Source: https://upstash.com/docs/qstash/howto/signature

Verifies the JWT signature of an incoming request using the QStash SDK for Golang. This method ensures the request's authenticity by checking the signature and claims. It requires the current and next signing keys, the raw request body, the 'Upstash-Signature' header value, and optionally, your site's URL.

```go
import "github.com/qstash/qstash-go"

receiver := qstash.NewReceiver("<CURRENT_SIGNING_KEY>", "NEXT_SIGNING_KEY")

// ... in your request handler

signature := req.Header.Get("Upstash-Signature")
body, err := io.ReadAll(req.Body)
// handle err

err := receiver.Verify(qstash.VerifyOptions{
    Signature: signature,
    Body:      string(body),
    Url:       "YOUR-SITE-URL", // optional
})
// handle err
```

--------------------------------

### Publish Anthropic LLM Request with QStash

Source: https://upstash.com/docs/qstash/integrations/anthropic

Publishes an LLM request to Anthropic via QStash. Requires QStash and Anthropic API tokens. The `api` parameter specifies `llm` with the `anthropic()` provider. A `callback` URL is used for asynchronous response handling, as streaming completions are not supported.

```typescript
import { anthropic, Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  api: { name: "llm", provider: anthropic({ token: "<ANTHROPIC_TOKEN>" }) },
  body: {
    model: "claude-3-5-sonnet-20241022",
    messages: [{ role: "user", content: "Summarize recent tech trends." }],
  },
  callback: "https://example.com/callback",
});
```

--------------------------------

### Batch Operations API

Source: https://upstash.com/docs/qstash/overall/llms-txt

This section covers batch operations for sending multiple messages efficiently. It includes publishing to multiple destinations and enqueuing messages to different queues in a single request, reducing overhead.

```APIDOC
## POST /v2/batch

### Description
Sends multiple messages in a single request to different URLs or URL groups, or enqueues messages to different queues.

### Method
POST

### Endpoint
/v2/batch

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
An array of message objects. Each object can specify a `destination` (URL) or a `queue` name, along with optional `headers`, `body`, `delay`, and `retries`.

### Request Example (Publish to Destinations)
```json
[
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
]
```

### Request Example (Enqueue to Queues)
```json
[
  {
    "queue": "my-queue",
    "destination": "https://example.com/destination1"
  },
  {
    "queue": "my-second-queue",
    "destination": "https://example.com/destination2"
  }
]
```

### Response
#### Success Response (200)
An array of objects, where each object contains the `messageId` for the successfully enqueued or published message.

#### Response Example
```json
[
  { "messageId": "msg_..." },
  { "messageId": "msg_..." }
]
```
```

--------------------------------

### Configure URL Group Headers via API

Source: https://upstash.com/docs/qstash/howto/webhook

Use the QStash API to configure headers for a URL Group, which will be applied to all publish requests made to that group. This allows for setting default headers like enabling header forwarding or specifying retry counts.

```curl
curl -X PATCH https://qstash.upstash.io/v2/topics/<URL_GROUP_NAME> \
    -H "Authorizarion: Bearer <QSTASH_TOKEN>" \
    -d '{
        "headers": {
            "Upstash-Header-Forward": ["true"],
            "Upstash-Retries": "3"
        }
    }'
```

--------------------------------

### Trigger Workflow (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Manually trigger a workflow execution using a cURL command. This method sends a POST request to the QStash publish endpoint, including authorization, content type, and custom headers for workflow run ID and retries, along with the JSON payload.

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

--------------------------------

### Publish Message to QStash (curl)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

This command-line script demonstrates how to publish a JSON message to Upstash QStash. It requires the destination URL of your Lambda function and your QStash bearer token for authorization. The Content-Type header is set to application/json.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://urzdbfn4et56vzeasu3fpcynym0zerme.lambda-url.eu-west-1.on.aws" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### Publish Message to Endpoint

Source: https://upstash.com/docs/qstash/overall/llms-txt

Send a JSON message to a specified URL. Ensures delivery with automatic retries. Requires a QStash token for authorization and the target URL. The body of the message is sent as JSON.

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

--------------------------------

### Enqueue Message to a Queue

Source: https://upstash.com/docs/qstash/features/queues

Enqueue a JSON message to a specified queue for ordered delivery. Messages are processed in a First-In, First-Out (FIFO) manner, ensuring sequential processing and retries.

```APIDOC
## POST /v2/enqueue/{queueName}/{url}

### Description
Enqueues a JSON message to a specified queue. Messages are delivered in FIFO order, with built-in retry mechanisms.

### Method
POST

### Endpoint
`/v2/enqueue/{queueName}/{url}`

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to send the message to.
- **url** (string) - Required - The URL to send the message to.

#### Request Body
- **message** (string) - Required - The message content (can be JSON stringified).

### Request Example
```json
{
  "message": "Hello, World!"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the enqueued message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Complete Cloudflare Worker Handler for QStash (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

A complete Cloudflare Worker `fetch` handler that imports the QStash Receiver, defines environment variables, initializes the receiver, verifies the incoming webhook signature, and returns an appropriate response. It returns 'Invalid signature' with a 401 status if verification fails.

```typescript
import { Receiver } from "@upstash/qstash";

export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string;
  QSTASH_NEXT_SIGNING_KEY: string;
}

export default {
  async fetch(request, env, ctx): Promise<Response> {
    const receiver = new Receiver({
      currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
      nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
    });

    const body = await request.text();

    const isValid = await receiver.verify({
      signature: request.headers.get("Upstash-Signature")!,
      body,
    });

    if (!isValid) {
      return new Response("Invalid signature", { status: 401 });
    }

    // signature is valid

    return new Response("Hello World!");
  },
} satisfies ExportedHandler<Env>;
```

--------------------------------

### Add Success and Failure Callbacks (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a JSON message with defined success and failure callback URLs using the Upstash QStash client for TypeScript. This enables asynchronous handling of endpoint responses. Requires QSTASH_TOKEN.

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

--------------------------------

### Schedule Cron Job with New York Timezone

Source: https://upstash.com/docs/qstash/features/schedules

This snippet demonstrates how to create a QStash schedule that runs at a specific time in New York. It requires a QStash client initialized with an API token and specifies the destination URL and the cron expression with the `CRON_TZ` prefix.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "CRON_TZ=America/New_York 0 4 * * *",
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

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: CRON_TZ=America/New_York 0 4 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

### View QStash Message Delivery Logs with Wrangler

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

This snippet demonstrates how to use the `wrangler tail` command to view logs from a Cloudflare Worker. This is used to confirm that a message published to QStash has been successfully received and processed by the worker.

```bash
npx wrangler tail
```

--------------------------------

### Sending LLM Requests in Batches

Source: https://upstash.com/docs/qstash/integrations/anthropic

Sends multiple LLM requests to Anthropic in a single batch using QStash's `batchJSON` method. Each request can have its own callback URL for handling responses.

```APIDOC
## POST /batch

### Description
Sends multiple LLM requests to Anthropic in a single batch operation.

### Method
POST

### Endpoint
/v2/batch

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- An array of request objects, where each object is structured like the 'Publishing a Request' endpoint:
  - **api** (object) - Required - Specifies the LLM API and provider.
    - **name** (string) - Required - Must be 'llm'.
    - **provider** (object) - Required - Anthropic provider configuration.
      - **token** (string) - Required - Your Anthropic API token.
  - **body** (object) - Required - The LLM request payload for Anthropic.
    - **model** (string) - Required - The Anthropic model to use.
    - **messages** (array) - Required - An array of message objects.
  - **callback** (string) - Optional - URL for the response.

### Request Example
```json
[
  {
    "api": {
      "name": "llm",
      "provider": {
        "name": "anthropic",
        "token": "<ANTHROPIC_TOKEN>"
      }
    },
    "body": {
      "model": "claude-3-5-sonnet-20241022",
      "messages": [{"role": "user", "content": "Describe the latest in AI research."}]
    },
    "callback": "https://example.com/callback1"
  },
  {
    "api": {
      "name": "llm",
      "provider": {
        "name": "anthropic",
        "token": "<ANTHROPIC_TOKEN>"
      }
    },
    "body": {
      "model": "claude-3-5-sonnet-20241022",
      "messages": [{"role": "user", "content": "Outline the future of remote work."}]
    },
    "callback": "https://example.com/callback2"
  }
]
```

### Response
#### Success Response (200)
- **batchId** (string) - The ID of the batch operation.

#### Response Example
```json
{
  "batchId": "batch_ghi789"
}
```
```

--------------------------------

### Receive and Verify QStash Messages in Next.js

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This code snippet demonstrates how to receive and verify an incoming QStash message in a Next.js route handler. It uses `verifySignatureAppRouter` from `@upstash/qstash/nextjs` to ensure the message originates from QStash. After verification, it parses the JSON body and performs the image processing logic.

```tsx
import { verifySignatureAppRouter } from "@upstash/qstash/nextjs"

// 👇 Verify that this messages comes from QStash
export const POST = verifySignatureAppRouter(async (req: Request) => {
  const body = await req.json()
  const { imageId } = body as { imageId: string }

  // Image processing logic, i.e. using sharp

  return new Response(`Image with id "${imageId}" processed successfully.`) 
})
```

--------------------------------

### Request Signing (Optional)

Source: https://upstash.com/docs/qstash/features/security

QStash provides optional request signing using JWTs in the `Upstash-Signature` header to verify the authenticity of incoming requests to your endpoints.

```APIDOC
## Request Signing (Optional)

### Description
Verify the authenticity of incoming requests by validating the JWT provided in the `Upstash-Signature` header. The JWT is signed using HMAC SHA256 with your signing key.

### Method
All HTTP Methods

### Endpoint
All QStash Endpoints

### Headers
- **Upstash-Signature** (string) - Required - A JWT containing request details.

### Request Body Hash
The `body` claim in the JWT is a URL-encoded, base64-encoded SHA256 hash of the request body.

### JWT Claims
- **iss** (string): Issuer, always `Upstash`.
- **sub** (string): The URL of your endpoint.
- **exp** (integer): Unix timestamp after which the token is invalid (default 5 minutes lifetime).
- **nbf** (integer): Unix timestamp before which the token should not be accepted.
- **iat** (integer): Unix timestamp when the JWT was created.
- **jti** (string): Unique token identifier.
- **body** (string): Base64-encoded SHA256 hash of the request body.

### Verifying the Signature
Refer to the QStash documentation for detailed instructions on how to verify the signature. [See how to verify the signature](/qstash/howto/signature)
```

--------------------------------

### Publish Message with Custom Retry Delay

Source: https://upstash.com/docs/qstash/features/retry

Shows how to publish a JSON message with a custom retry delay expression using cURL, TypeScript, and Python. This allows overriding the default exponential backoff with user-defined logic.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    retries: 3,
    retryDelay: "pow(2, retried) * 1000", // 2^retried * 1000ms
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    retries=3,
    retry_delay="pow(2, retried) * 1000",  # 2^retried * 1000ms
)
```

--------------------------------

### Publish to URL Group using Python

Source: https://upstash.com/docs/qstash/howto/publishing

This Python snippet illustrates publishing a JSON message to a URL Group with the QStash Python client. It involves creating a QStash client instance with an API token and then using the `publish_json` method, specifying the `url_group` and `body`. The function returns the API response.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url_group="my-url-group",
    body={
        "hello": "world",
    },
)
```

--------------------------------

### Set Rate Limit for Message Delivery (TypeScript, cURL)

Source: https://upstash.com/docs/qstash/features/flowcontrol

This snippet demonstrates how to set a rate limit for message delivery using QStash Flow Control. The `rate` parameter specifies the maximum number of calls allowed, and the `period` parameter defines the time window for this limit. The key `USER_GIVEN_KEY` is used to identify and apply this flow control setting.

```TypeScript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, period: "1m" },
});
```

```cURL
curl -XPOST -H 'Authorization: Bearer XXX' \
              -H "Content-type: application/json" \
              -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
              -H "Upstash-Flow-Control-Value:rate=10,period=1m" \
             'https://qstash.upstash.io/v2/publish/https://example.com' \
              -d '{"message":"Hello, World!"}'
```

--------------------------------

### Publish with Content-Based Deduplication

Source: https://upstash.com/docs/qstash/features/deduplication

Enable content-based deduplication by setting the `Upstash-Content-Based-Deduplication` header to `true`. QStash automatically generates a deduplication ID based on the destination, body, and forwarded headers.

```APIDOC
## POST /v2/publish

### Description
Publishes a message to a given URL, enabling content-based deduplication. QStash automatically generates a deduplication ID based on the message's destination, body, and specific headers.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type of the request body, e.g., `application/json`.
- **Upstash-Content-Based-Deduplication** (boolean) - Required - Set to `true` to enable content-based deduplication.

#### Request Body
- **body** (object) - Required - The JSON payload of the message to be published.

### Request Example
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Content-Based-Deduplication: true" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/...' 
```

### Response
#### Success Response (200 or 202)
- **messageId** (string) - The unique ID of the published message. If the message was a duplicate, this is the ID of the existing message.

#### Response Example
```json
{
  "messageId": "msg_67890"
}
```

### Note
The deduplication window for content-based deduplication is 10 minutes. After this period, messages with the same content can be sent again.
```

--------------------------------

### Trigger Background Job from Next.js Client

Source: https://upstash.com/docs/qstash/features/background-jobs

This client-side code in a Next.js application initiates a background job by sending a POST request to a server endpoint. It sends a list of users to be processed by the background task. Ensure proper error handling is implemented for production.

```tsx
"use client"

export default function Home() {
  async function handleClick() {
    // Send a request to our server to start the background job.
    // For proper error handling, refer to the quick start.
    // Note: This can also be a server action instead of a route handler
    await fetch("/api/start-email-job", {
      method: "POST",
      body: JSON.stringify({
        users: ["a@gmail.com", "b@gmail.com", "c.gmail.com"]
      }),
    })

  }

  return (
    <main>
      <button onClick={handleClick}>Run background job</button>
    </main>
  );
}

```

--------------------------------

### Import Libraries for QStash Webhook Handler (Python)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

Imports necessary Python libraries for handling JSON, environment variables, cryptographic operations (HMAC, SHA256, Base64), time, and JWT decoding. These are essential for processing QStash webhook requests and verifying signatures.

```python
import json
import os
import hmac
import hashlib
import base64
import time
import jwt
```

--------------------------------

### Enqueue Messages for Ordered Delivery (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Enqueues a JSON message to a specified queue for ordered delivery using the Upstash QStash client for Python. Requires a QSTASH_TOKEN, queue name, destination URL, and the message body.

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

--------------------------------

### Verify JWT Signature with QStash SDK (Python)

Source: https://upstash.com/docs/qstash/howto/signature

Verifies the JWT signature of an incoming request using the QStash SDK for Python. This function automates signature and claim validation, ensuring the request's integrity. It needs the current and next signing keys, the raw request body, the signature from the header, and your site's URL.

```python
from qstash import Receiver

receiver = Receiver(
    current_signing_key="YOUR_CURRENT_SIGNING_KEY",
    next_signing_key="YOUR_NEXT_SIGNING_KEY",
)

# ... in your request handler

signature, body = req.headers["Upstash-Signature"], req.body

receiver.verify(
    body=body,
    signature=signature,
    url="YOUR-SITE-URL",
)
```

--------------------------------

### Batch Enqueue Messages to Queues

Source: https://upstash.com/docs/qstash/overall/llms-txt

Enqueue multiple messages to different queues in a single batch request using QStash. This is useful for distributing tasks across various processing queues. Requires a QStash token for authentication.

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

--------------------------------

### Verify JWT Signature with QStash SDK (TypeScript)

Source: https://upstash.com/docs/qstash/howto/signature

Verifies the JWT signature of an incoming request using the QStash SDK for TypeScript. This method simplifies the process by handling the cryptographic operations. It requires the current and next signing keys, the request body, the signature from the header, and the URL of your site.

```typescript
import { Receiver } from "@upstash/qstash";

const receiver = new Receiver({
  currentSigningKey: "YOUR_CURRENT_SIGNING_KEY",
  nextSigningKey: "YOUR_NEXT_SIGNING_KEY",
});

// ... in your request handler

const signature = req.headers["Upstash-Signature"];
const body = req.body;

const isValid = await receiver.verify({
  body,
  signature,
  url: "YOUR-SITE-URL",
});
```

--------------------------------

### Create Recurring Schedule with Cron Expression

Source: https://upstash.com/docs/qstash/overall/llms-txt

Schedule messages to be sent periodically to a specified destination using a cron expression. Requires a QStash token and the destination URL. The cron expression defines the schedule's frequency.

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

--------------------------------

### AWS Lambda Handler for QStash Webhook Verification (Python)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

The main AWS Lambda handler function. It parses incoming event data, retrieves signing keys from environment variables, extracts the QStash signature and request URL. It then attempts to verify the signature using the current and next signing keys, returning an error if verification fails. Upon successful verification, it proceeds to the user's custom logic.

```python
def lambda_handler(event, context):

    # parse the inputs
    current_signing_key = os.environ['QSTASH_CURRENT_SIGNING_KEY']
    next_signing_key = os.environ['QSTASH_NEXT_SIGNING_KEY']

    headers = event['headers']
    signature = headers['upstash-signature']
    url = "https://{}{}".format(event["requestContext"]["domainName"], event["rawPath"])
    body = None
    if 'body' in event:
        body = event['body']


    # check verification now
    try:
        verify(signature, current_signing_key, body, url)
    except Exception as e:
        print("Failed to verify signature with current signing key:", e)
        try:
            verify(signature, next_signing_key, body, url)
        except Exception as e2:
            return {
                "statusCode": 400,
                "body": json.dumps({
                    "error": str(e2),
                }),
            }


    # Your logic here...

    return {
        "statusCode": 200,
        "body": json.dumps({
            "message": "ok",
        }),
    }
```

--------------------------------

### Configure AWS Lambda Environment Variables for QStash

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

Set the QSTASH_CURRENT_SIGNING_KEY and QSTASH_NEXT_SIGNING_KEY environment variables within your AWS Lambda configuration. These keys are crucial for QStash's security and message signing processes. Ensure these values are kept confidential.

```Shell
QSTASH_CURRENT_SIGNING_KEY=<your_current_signing_key>
QSTASH_NEXT_SIGNING_KEY=<your_next_signing_key>
```

--------------------------------

### Publish Message

Source: https://upstash.com/docs/qstash/howto/publishing

Publishing a message involves sending an HTTP POST request to the /publish endpoint with the destination URL and message content.

```APIDOC
## POST /publish

### Description
Publishes a message to a specified destination URL. The message content is provided in the request body.

### Method
POST

### Endpoint
`/publish`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **body** (any) - Required - The content of the message to be published.

### Request Example
```json
{
  "message": "Your message content here"
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the publish operation.

#### Response Example
```json
{
  "status": "published"
}
```

### Additional Information
- Destination URLs must include the protocol (e.g., `http://` or `https://`).
- Custom HTTP headers can be forwarded by prefixing them with `Upstash-Forward-`.
- The `Content-Type` header is recommended for the request body.
- Messages are retried automatically if the destination API is unavailable or returns an error status code.
```

--------------------------------

### Create URL Group Endpoints via REST API

Source: https://upstash.com/docs/qstash/howto/url-group-endpoint

This snippet demonstrates how to add multiple endpoints to a URL Group using the QStash REST API. It requires a bearer token for authentication and specifies the endpoint names and their corresponding URLs in JSON format. The API allows for batch creation of endpoints within a specified URL group.

```bash
curl -XPOST https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
    -H "Authorization: Bearer <token>" \
    -H "Content-Type: application/json" \
    -d '{
      "endpoints": [
        {
          "name": "endpoint1",
          "url": "https://example.com"
        },
        {
          "name": "endpoint2",
          "url": "https://somewhere-else.com"
        }
      ]
    }'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.addEndpoints({
  name: "urlGroupName",
  endpoints: [
    { name: "endpoint1", url: "https://example.com" },
    { name: "endpoint2", url: "https://somewhere-else.com" },
  ],
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.url_group.upsert_endpoints(
    url_group="url-group-name",
    endpoints=[
        {"name": "endpoint1", "url": "https://example.com"},
        {"name": "endpoint2", "url": "https://somewhere-else.com"},
    ],
)
```

--------------------------------

### Publish to URL Group using cURL

Source: https://upstash.com/docs/qstash/howto/publishing

This snippet demonstrates how to publish a JSON message to a URL Group using cURL. It requires basic authentication with a QStash token and specifies the message body and the target URL Group. The output is the response from the QStash API.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/my-url-group'
```

--------------------------------

### Publish to URL Group

Source: https://upstash.com/docs/qstash/howto/publishing

Publishing to a URL Group is similar to publishing to a single destination. Replace the `URL` in the `/publish` endpoint with the URL Group name.

```APIDOC
## POST /v2/publish/:urlGroup

### Description
Publishes a message to a specified URL Group.

### Method
POST

### Endpoint
`/v2/publish/:urlGroup`

### Parameters
#### Path Parameters
- **urlGroup** (string) - Required - The name of the URL Group to publish to.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message to be sent.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_xxxxxxxxxxxx"
}
```
```

--------------------------------

### Golang: JWT Signature Verification for QStash Webhooks

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Implements the JWT verification logic for incoming QStash webhooks. It parses the JWT token, validates the signing method, issuer, expiration, and not-before claims, and crucially, verifies that the body hash in the claims matches the SHA256 hash of the received request body.

```go
func verify(body []byte, tokenString, signingKey string) error {
	token, err := jwt.Parse(
		tokenString,
		func(token *jwt.Token) (interface{}, error) {
			if _, ok := token.Method.(*jwt.SigningMethodHMAC); !ok {
				return nil, fmt.Errorf("Unexpected signing method: %v", token.Header["alg"])
			}
			return []byte(signingKey), nil
		})

	if err != nil {
		return err
	}

	claims, ok := token.Claims.(jwt.MapClaims)
	if !ok || !token.Valid {
		return fmt.Errorf("Invalid token")
	}

	if !claims.VerifyIssuer("Upstash", true) {
		return fmt.Errorf("invalid issuer")
	}
	if !claims.VerifyExpiresAt(time.Now().Unix(), true) {
		return fmt.Errorf("token has expired")
	}
	if !claims.VerifyNotBefore(time.Now().Unix(), true) {
		return fmt.Errorf("token is not valid yet")
	}

	bodyHash := sha256.Sum256(body)
	if claims["body"] != base64.URLEncoding.EncodeToString(bodyHash[:]) {
		return fmt.Errorf("body hash does not match")
	}

	return nil
}
```

--------------------------------

### Enqueue Messages for Ordered Delivery (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Enqueues a JSON message to a specified queue for ordered delivery using the Upstash QStash client for TypeScript. Requires a QSTASH_TOKEN, queue name, destination URL, and the message body.

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

--------------------------------

### Publish JSON Message with cURL

Source: https://upstash.com/docs/qstash/overall/getstarted

This snippet demonstrates how to publish a JSON message to a specified URL using cURL. It requires an authorization token and sets the 'Content-type' header to 'application/json'. The message payload is provided as a JSON string in the request body.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://<your-api-url>'
```

--------------------------------

### Enqueue Anthropic LLM Chat Completion Request with QStash

Source: https://upstash.com/docs/qstash/integrations/anthropic

Enqueues a chat completion request for Anthropic via QStash using `enqueueJSON`. This allows for asynchronous processing of LLM requests. It requires QStash and Anthropic API tokens, and specifies a callback URL for handling the response.

```typescript
import { anthropic, Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const result = await client.queue({ queueName: "your-queue-name" }).enqueueJSON({
  api: { name: "llm", provider: anthropic({ token: "<ANTHROPIC_TOKEN>" }) },
  body: {
    model: "claude-3-5-sonnet-20241022",
    messages: [
      {
        role: "user",
        content: "Generate ideas for a marketing campaign.",
      },
    ],
  },
  callback: "https://example.com/callback",
});

console.log(result);
```

--------------------------------

### Python Redis Cleanup Logic

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Contains the core Python logic to connect to an Upstash Redis database and delete all entries. It uses the 'upstash_redis' package, requiring Redis URL and token for authentication. The function retrieves all keys and then deletes them.

```python
from upstash_redis import Redis

redis = Redis(url="https://YOUR_REDIS_URL", token="YOUR_TOKEN")

def delete_all_entries():
  keys = redis.keys("*") # Match all keys
  redis.delete(*keys)


delete_all_entries()
```

--------------------------------

### Publish with Relative Delay (cURL)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message with a relative delay of 1 minute using the `Upstash-Delay` header. This method is useful for delaying messages by a specific duration after publication.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 1m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

--------------------------------

### Publish with Absolute Delay (Python)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message with an absolute delay set via the `not_before` parameter, using a Unix timestamp. This demonstrates scheduling message delivery at a specific time in Python.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    headers={
        "test-header": "test-value",
    },
    not_before=1657104947,
)
```

--------------------------------

### Batch messages to destinations (cURL, TypeScript, Python)

Source: https://upstash.com/docs/qstash/features/batch

Send multiple messages to specific destinations in a single batch request. This method is useful when you need to send individual messages to different endpoints. The response will contain results for each message in the batch.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '
     [
      {
        "destination": "https://example.com/destination1"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'

```

```typescript
import { Client } from "@upstash/qstash";

// Each message is the same as the one you would send with the publish endpoint
const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.batchJSON([
  {
    url: "https://example.com/destination1",
  },
  {
    url: "https://example.com/destination2",
  },
]);

```

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.batch_json(
    [
        {"url": "https://example.com/destination1"},
        {"url": "https://example.com/destination2"},
    ]
)

```

--------------------------------

### Define Lambda and API Gateway with AWS CDK (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This snippet defines an AWS CDK stack in TypeScript, creating a Node.js Lambda function and an API Gateway REST API. The API Gateway is configured to integrate with the Lambda function for POST requests. Ensure the Lambda handler path and runtime are correctly specified. Dependencies include 'aws-cdk-lib' and 'constructs'.

```typescript
import * as cdk from "aws-cdk-lib";
import * as lambda from "aws-cdk-lib/aws-lambda";
import { NodejsFunction } from "aws-cdk-lib/aws-lambda-nodejs";
import { Construct } from "constructs";
import path from "path";
import * as apigateway from 'aws-cdk-lib/aws-apigateway';

export class VideoProcessingStack extends cdk.Stack {
  constructor(scope: Construct, id: string, props?: cdk.StackProps) {
    super(scope, id, props)

    // Create the Lambda function
    const videoProcessingLambda = new NodejsFunction(this, 'VideoProcessingLambda', {
      runtime: lambda.Runtime.NODEJS_20_X,
      handler: 'handler',
      entry: path.join(__dirname, '../lambda/index.ts'),
    });

    // Create the API Gateway
    const api = new apigateway.RestApi(this, 'VideoProcessingApi', {
      restApiName: 'Video Processing Service',
      description: 'This service handles video processing.',
      defaultMethodOptions: {
        authorizationType: apigateway.AuthorizationType.NONE,
      },
    });

    api.root.addMethod('POST', new apigateway.LambdaIntegration(videoProcessingLambda));
  }
}
```

--------------------------------

### Handle long-running background tasks in Next.js API route

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This TypeScript code defines a POST endpoint for a Next.js API route that handles a background job. It processes incoming JSON data, sends multiple requests with delays, and returns a success response. It's designed to be mindful of serverless function time limits.

```typescript
export async function POST(request: Request) {
  const data = await request.json()

  for (let i = 0; i < 10; i++) {
    await fetch("https://firstqstashmessage.requestcatcher.com/test", {
      method: "POST",
      body: JSON.stringify(data),
      headers: { "Content-Type": "application/json" },
    })
    await new Promise((resolve) => setTimeout(resolve, 500))
  }

  return Response.json({ success: true })
}
```

--------------------------------

### AWS Lambda Handler for QStash Verification (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

Implements the main handler function for an AWS Lambda that receives QStash requests. It extracts the 'upstash-signature' header and attempts to verify it using current and next signing keys to allow for seamless key rotation. If verification fails, it returns a 400 status code; otherwise, it proceeds to business logic. Dependencies include Node.js crypto module and AWS Lambda types.

```typescript
import type { APIGatewayEvent, APIGatewayProxyResult } from "aws-lambda"
import { createHash, createHmac } from "node:crypto"

export const handler = async (
  event: APIGatewayEvent,
): Promise<APIGatewayProxyResult> => {
  const signature = event.headers["upstash-signature"] ?? ""
  const currentSigningKey = process.env.QSTASH_CURRENT_SIGNING_KEY ?? ""
  const nextSigningKey = process.env.QSTASH_NEXT_SIGNING_KEY ?? ""

  const url = `https://${event.requestContext.domainName}`

  try {
    // Try to verify the signature with the current signing key and if that fails, try the next signing key
    // This allows you to roll your signing keys once without downtime
    await verify(signature, currentSigningKey, event.body, url).catch((err) => {
      console.error(
        `Failed to verify signature with current signing key: ${err}`
      )

      return verify(signature, nextSigningKey, event.body, url)
    })
  } catch (err) {
    const message = err instanceof Error ? err.toString() : err

    return {
      statusCode: 400,
      body: JSON.stringify({ error: message }),
    }
  }

  // Add your business logic here

  return {
    statusCode: 200,
    body: JSON.stringify({ message: "Request processed successfully" }),
  }
}
```

--------------------------------

### Publish with Relative Delay (Python)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message with a delay specified as '60s' using the `delay` parameter in the QStash client. This demonstrates how to implement relative message delays in Python applications.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    headers={
        "test-header": "test-value",
    },
    delay="60s",
)
```

--------------------------------

### Initialize Upstash QStash Receiver with Cloudflare Secrets Store

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

This TypeScript code snippet demonstrates how to initialize the Upstash QStash Receiver in a Cloudflare Worker. It retrieves signing keys from the Cloudflare Secrets Store via the `env` object, which must be configured with `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY` bindings.

```typescript
import { Receiver } from "@upstash/qstash";

export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: SecretsStoreSecret;
  QSTASH_NEXT_SIGNING_KEY: SecretsStoreSecret;
}

export default {
  async fetch(request, env, ctx): Promise<Response> {
    const c = new Receiver({
      currentSigningKey: await env.QSTASH_CURRENT_SIGNING_KEY.get(),
      nextSigningKey: await env.QSTASH_NEXT_SIGNING_KEY.get(),
    });

    // Rest of the code
  },
};
```

--------------------------------

### QStash API Request Authorization Header

Source: https://upstash.com/docs/qstash/features/security

This snippet shows how to include the authorization token in the Authorization header for requests to the QStash API. Ensure you replace '<QSTASH_TOKEN>' with your actual token obtained from the Upstash Console.

```http
"Authorization": "Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Publish with Absolute Delay (TypeScript)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message with an absolute delay specified by the `notBefore` Unix timestamp. This allows scheduling message delivery for a precise future moment in TypeScript.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    notBefore: 1657104947,
});
```

--------------------------------

### Publish Message with Content-Based Deduplication

Source: https://upstash.com/docs/qstash/features/deduplication

Enable automatic message deduplication based on message content by setting the 'Upstash-Content-Based-Deduplication' header to true. This ensures that messages with identical destinations, bodies, and forwarded headers within the deduplication window are only enqueued once. The client accepts a contentBasedDeduplication boolean parameter.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Content-Based-Deduplication: true" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/...'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    contentBasedDeduplication: true,
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    content_based_deduplication=True,
)
```

--------------------------------

### Defining Environment Variables for QStash (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Defines the `Env` interface for Cloudflare Workers, specifying the required environment variables: `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY`. These keys are used by the QStash Receiver to validate webhook signatures.

```typescript
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string;
  QSTASH_NEXT_SIGNING_KEY: string;
}
```

--------------------------------

### Publish with Relative Delay (TypeScript)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message with a relative delay of 60 seconds using the `delay` option in the QStash client. This provides a programmatic way to set message delays in TypeScript applications.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    delay: 60,
});
```

--------------------------------

### Enqueueing LLM Chat Completion Requests

Source: https://upstash.com/docs/qstash/integrations/anthropic

Enqueues a chat completion request to Anthropic for asynchronous processing using QStash's `enqueueJSON` method. This allows for managed execution of LLM tasks within a queue.

```APIDOC
## POST /queues/{queueName}/enqueue

### Description
Enqueues a chat completion request to Anthropic for processing in a specified QStash queue.

### Method
POST

### Endpoint
/v2/queues/{queueName}/enqueue

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to enqueue the request into.

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API and provider.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Anthropic provider configuration.
    - **token** (string) - Required - Your Anthropic API token.
- **body** (object) - Required - The LLM request payload for Anthropic.
  - **model** (string) - Required - The Anthropic model to use (e.g., "claude-3-5-sonnet-20241022").
  - **messages** (array) - Required - An array of message objects for the chat conversation.
- **callback** (string) - Optional - URL to send the LLM response to asynchronously.

### Request Example
```json
{
  "api": {
    "name": "llm",
    "provider": {
      "name": "anthropic",
      "token": "<ANTHROPIC_TOKEN>"
    }
  },
  "body": {
    "model": "claude-3-5-sonnet-20241022",
    "messages": [{"role": "user", "content": "Generate ideas for a marketing campaign."}]
  },
  "callback": "https://example.com/callback"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the enqueued message.

#### Response Example
```json
{
  "messageId": "msg_def456"
}
```
```

--------------------------------

### Enqueue Messages to a QStash Queue

Source: https://upstash.com/docs/qstash/features/queues

Enqueues a JSON message to a specified QStash queue. Ensures ordered delivery (FIFO) by default. Messages are queued without blocking the REST API and processed sequentially, waiting for previous messages to be delivered or fail before proceeding. Supports retries and callbacks.

```bash
curl -XPOST -H 'Authorization: Bearer XXX' \
              -H "Content-type: application/json" \
    'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' -d '{"message":"Hello, World!"}'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

  const queue = client.queue({
    queueName: "my-queue"
  })

  await queue.enqueueJSON({
    url: "https://example.com",
    body: {
      "Hello": "World"
    }
  })
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

--------------------------------

### Batch Publish Messages to Multiple Destinations

Source: https://upstash.com/docs/qstash/overall/llms-txt

Send multiple messages in a single request to different URLs or URL groups using QStash. This allows for efficient distribution of messages to various endpoints. Requires a QStash token for authentication.

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

--------------------------------

### Integrating Helicone Analytics

Source: https://upstash.com/docs/qstash/integrations/anthropic

Shows how to include Helicone analytics in your LLM requests by passing your Helicone API key within the `analytics` object of the request configuration.

```APIDOC
## POST /publish (with Helicone Analytics)

### Description
Publishes an LLM request to Anthropic through QStash, including Helicone analytics for usage monitoring.

### Method
POST

### Endpoint
/v2/publish

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API and provider.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Anthropic provider configuration.
    - **token** (string) - Required - Your Anthropic API token.
  - **analytics** (object) - Optional - Configuration for analytics integration.
    - **name** (string) - Required - Must be 'helicone'.
    - **token** (string) - Required - Your Helicone API key.
- **body** (object) - Required - The LLM request payload for Anthropic.
- **callback** (string) - Optional - URL for the response.

### Request Example
```json
{
  "api": {
    "name": "llm",
    "provider": {
      "name": "anthropic",
      "token": "<ANTHROPIC_TOKEN>"
    },
    "analytics": {
      "name": "helicone",
      "token": "<HELICONE_API_KEY>"
    }
  },
  "body": {
    "model": "claude-3-5-sonnet-20241022",
    "messages": [{"role": "user", "content": "Hello!"}]
  },
  "callback": "https://example.com/callback"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_jkl012"
}
```
```

--------------------------------

### List Schedules API

Source: https://upstash.com/docs/qstash/howto/delete-schedule

Retrieves a list of all existing schedules. This is useful if you need to find a schedule ID before deleting it.

```APIDOC
## GET /v2/schedules

### Description
Retrieves a list of all existing schedules. This is useful if you need to find a schedule ID before deleting it.

### Method
GET

### Endpoint
`/v2/schedules`

### Parameters
(No query parameters are specified for this endpoint)

### Request Example
```shell
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'
```

### Response
#### Success Response (200)
- **schedules** (array) - A list of schedule objects.
  - Each schedule object may contain details like `id`, `cron`, `createdAt`, etc. (Specific fields not detailed in the source text).

#### Response Example
```json
{
  "schedules": [
    {
      "id": "<schedule_id_1>",
      "cron": "* * * * *",
      "createdAt": 1678886400,
      "updatedAt": 1678886400
    },
    {
      "id": "<schedule_id_2>",
      "cron": "0 0 * * *",
      "createdAt": 1678886400,
      "updatedAt": 1678886400
    }
  ]
}
```
```

--------------------------------

### Verify QStash JWT Signature and Claims (Python)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

A helper function to verify the QStash signature, which is a JWT. It splits the token, generates a signature from the message (header + payload), and compares it with the provided signature. It also decodes JWT claims (issuer, subject, expiration, not-before) and verifies the request body hash if a body is present. This function ensures the integrity and authenticity of the incoming webhook.

```python
# @param jwt_token - The content of the `upstash-signature` header
# @param signing_key - The signing key to use to verify the signature (Get it from Upstash Console)
# @param body - The raw body of the request
# @param url - The public URL of the lambda function
def verify(jwt_token, signing_key, body, url):
    split = jwt_token.split(".")
    if len(split) != 3:
        raise Exception("Invalid JWT.")

    header, payload, signature = split

    message = header + '.' + payload
    generated_signature = base64.urlsafe_b64encode(hmac.new(bytes(signing_key, 'utf-8'), bytes(message, 'utf-8'), digestmod=hashlib.sha256).digest()).decode()

    if generated_signature != signature and signature + "=" != generated_signature :
        raise Exception("Invalid JWT signature.")

    decoded = jwt.decode(jwt_token, options={"verify_signature": False})
    sub = decoded['sub']
    iss = decoded['iss']
    exp = decoded['exp']
    nbf = decoded['nbf']
    decoded_body = decoded['body']

    if iss != "Upstash":
        raise Exception("Invalid issuer: {}".format(iss))

    if sub.rstrip("/") != url.rstrip("/"):
        raise Exception("Invalid subject: {}".format(sub))

    now = time.time()
    if now > exp:
        raise Exception("Token has expired.")

    if now < nbf:
        raise Exception("Token is not yet valid.")


    if body != None:
        while decoded_body[-1] == "=":
            decoded_body = decoded_body[:-1]

        m = hashlib.sha256()
        m.update(bytes(body, 'utf-8'))
        m = m.digest()
        generated_hash = base64.urlsafe_b64encode(m).decode()

        if generated_hash != decoded_body and generated_hash != decoded_body + "=" :
                raise Exception("Body hash doesn't match.")
```

--------------------------------

### Publish Message to RequestCatcher with cURL

Source: https://upstash.com/docs/qstash/overall/getstarted

This cURL command publishes a JSON message to a RequestCatcher URL, useful for debugging and verifying message delivery. It includes the necessary authorization header and content type, sending a simple JSON payload.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://firstqstashmessage.requestcatcher.com/test'
```

--------------------------------

### Publish with Absolute Delay (cURL)

Source: https://upstash.com/docs/qstash/features/delay

Publishes a JSON message to be delivered at a specific future time, indicated by a Unix timestamp (1657104947) in the `Upstash-Not-Before` header. This is for absolute time-based message delivery.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Not-Before: 1657104947" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

--------------------------------

### Failure Callback Payload Structure

Source: https://upstash.com/docs/qstash/features/callbacks

Illustrates the JSON structure of the callback body sent to the failure callback URL. This payload contains details about the failed message delivery, including status, headers, body, retry information, and message metadata.

```json
{
  "status": 400,
  "header": { "key": ["value"] },         // Response header
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==", // base64 encoded response body
  "retried": 3,                           // How many times we retried to deliver the original message
  "maxRetries": 3,                        // Number of retries before the message assumed to be failed to delivered.
  "dlqId": "1725323658779-0",             // Dead Letter Queue id. This can be used to retrieve/remove the related message from DLQ.
  "sourceMessageId": "msg_xxx",           // The ID of the message that triggered the callback
  "topicName": "myTopic",                 // The name of the URL Group (topic) if the request was part of a topic
  "endpointName": "myEndpoint",           // The endpoint name if the endpoint is given a name within a topic
  "url": "http://myurl.com",              // The destination url of the message that triggered the callback
  "method": "GET",                        // The http method of the message that triggered the callback
  "sourceHeader": { "key": "value" },     // The http header of the message that triggered the callback
  "sourceBody": "YmFzZTY0kZWQgcm9keQ==",  // The base64 encoded body of the message that triggered the callback
  "notBefore": "1701198458025",           // The unix timestamp of the message that triggered the callback is/will be delivered in milliseconds
  "createdAt": "1701198447054",           // The unix timestamp of the message that triggered the callback is created in milliseconds
  "scheduleId": "scd_xxx",                // The scheduleId of the message if the message is triggered by a schedule
  "callerIP": "178.247.74.179"
}
```

--------------------------------

### Publish Message to QStash via cURL

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

This snippet shows how to publish a JSON message to QStash using the cURL command-line tool. It requires the QStash token and the destination worker URL. The output is logged by the receiving Cloudflare Worker.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://<your-worker-name>.<account-name>.workers.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### AWS Lambda Webhook Verification with Upstash QStash SDK

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs

This TypeScript code defines an AWS Lambda handler function that verifies incoming webhook requests using the Upstash QStash SDK. It requires signing keys to be provided as environment variables and checks for a valid signature in the request headers.

```typescript
import { Receiver } from "@upstash/qstash"
import type { APIGatewayProxyEvent, APIGatewayProxyResult } from "aws-lambda"

const receiver = new Receiver({
  currentSigningKey: process.env.QSTASH_CURRENT_SIGNING_KEY ?? "",
  nextSigningKey: process.env.QSTASH_NEXT_SIGNING_KEY ?? "",
})

export const handler = async (
  event: APIGatewayProxyEvent
): Promise<APIGatewayProxyResult> => {
  const signature = event.headers["upstash-signature"]
  const lambdaFunctionUrl = `https://${event.requestContext.domainName}`

  if (!signature) {
    return {
      statusCode: 401,
      body: JSON.stringify({ message: "Missing signature" }),
    }
  }

  try {
    await receiver.verify({
      signature: signature,
      body: event.body ?? "",
      url: lambdaFunctionUrl,
    })
  } catch (err) {
    return {
      statusCode: 401,
      body: JSON.stringify({ message: "Invalid signature" }),
    }
  }

  // Request is valid, perform business logic

  return {
    statusCode: 200,
    body: JSON.stringify({ message: "Request processed successfully" }),
  }
}
```

--------------------------------

### Set Parallelism Limit for Message Delivery (TypeScript, cURL)

Source: https://upstash.com/docs/qstash/features/flowcontrol

This snippet shows how to set a parallelism limit for message delivery with QStash Flow Control. The `parallelism` parameter restricts the number of concurrent active calls to your endpoint. The `USER_GIVEN_KEY` is used to associate this limit with a specific flow control configuration.

```TypeScript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", parallelism: 10 },
});
```

```cURL
curl -XPOST -H 'Authorization: Bearer XXX' \
              -H "Content-type: application/json" \
              -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
              -H "Upstash-Flow-Control-Value:parallelism=10" \
             'https://qstash.upstash.io/v2/publish/https://example.com' \
              -d '{"message":"Hello, World!"}'
```

--------------------------------

### Publish Message with Relative Delay

Source: https://upstash.com/docs/qstash/features/delay

Publish a message with a delay relative to the publish time. The delay can be specified using the `Upstash-Delay` header or the `delay` option in client libraries. The format for the duration is `<number><unit>`, e.g., `10s`, `1m`, `2h`, `7d`.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a given URL with a specified relative delay.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Set to `application/json`.
- **Upstash-Delay** (string) - Optional - The duration to delay the message delivery. Format: `<number><unit>` (e.g., `1m`, `2h`, `7d`).

### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 1m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

### Request Example (TypeScript)
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    delay: 60, // delay in seconds
});
```

### Request Example (Python)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    delay="60s", # delay in string format
)
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Retry-After Headers

Source: https://upstash.com/docs/qstash/features/retry

Control when QStash should retry a message by including specific headers in your response. You can specify delays in seconds, RFC1123 date format, or duration format. The maximum delay is one day.

```APIDOC
## Retry-After Headers

Instead of using the default backoff algorithm, you can specify when QStash should retry your message. To do this, include one of the following headers in your response to QStash request:

*   `Retry-After`
*   `X-RateLimit-Reset`
*   `X-RateLimit-Reset-Requests`
*   `X-RateLimit-Reset-Tokens`

These headers can be set to a value in seconds, the RFC1123 date format, or a duration format (e.g., `6m5s`). For the duration format, valid time units are `ns`, `us` (or `µs`), `ms`, `s`, `m`, `h`.

Note that you can only delay retries up to the maximum value of the default backoff algorithm, which is one day. If you specify a value beyond this limit, the backoff algorithm will be applied.

This feature is particularly useful if your application has rate limits, ensuring retries are scheduled appropriately without wasting attempts during restricted periods.

### Request Headers

#### Retry-After (seconds, RFC1123 date, or duration format)

**Examples:**

```
Retry-After: 0
Retry-After: 10
Retry-After: 6m5s
Retry-After: Sun, 27 Jun 2024 12:16:24 GMT
```

### Response

#### Success Response (200/2XX)

QStash will process the `Retry-After` or related headers to schedule the next retry.

#### Response Example (Header Usage)

```json
{
  "message": "Processing instructions received."
}
```

*(The actual response would likely be a successful HTTP status code with the specified header)*
```

--------------------------------

### Configure QStash Queue Parallelism

Source: https://upstash.com/docs/qstash/features/queues

Sets the maximum number of messages that can be processed concurrently from a QStash queue. By default, parallelism is 1 (sequential processing). This feature helps control the load on your endpoints. Note: This functionality is being deprecated in favor of the 'publish' API for flow control.

```bash
curl -XPOST https://qstash.upstash.io/v2/queues/ \
    -H "Authorization: Bearer <token>" \
    -H "Content-Type: application/json" \
    -d '{
      "queueName": "my-queue", 
      "parallelism": 5,
    }'
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

  const queue = client.queue({
    queueName: "my-queue"
  })

  await queue.upsert({
    parallelism: 1,
  })
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.upsert("my-queue", parallelism=5)
```

--------------------------------

### Publish with Deduplication ID

Source: https://upstash.com/docs/qstash/features/deduplication

Publish a message with a specific `Upstash-Deduplication-Id` header to ensure it's processed only once. If a duplicate is detected, QStash returns an `202 Accepted` status code and the message ID of the existing message.

```APIDOC
## POST /v2/publish

### Description
Publishes a message to a given URL with deduplication enabled using a custom `Upstash-Deduplication-Id` header.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type of the request body, e.g., `application/json`.
- **Upstash-Deduplication-Id** (string) - Required - A unique identifier to deduplicate the message.

#### Request Body
- **body** (object) - Required - The JSON payload of the message to be published.

### Request Example
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Deduplication-Id: abcdef" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

### Response
#### Success Response (200 or 202)
- **messageId** (string) - The unique ID of the published message. If the message was a duplicate, this is the ID of the existing message.

#### Response Example
```json
{
  "messageId": "msg_12345"
}
```
```

--------------------------------

### Specify Retry Timing with Retry-After Header

Source: https://upstash.com/docs/qstash/features/retry

Control when QStash should retry a message by including the Retry-After header in your response. This header can accept values in seconds, RFC1123 date format, or a duration format (e.g., 6m5s). Retries are capped at a maximum of one day.

```http
Retry-After: 0
Retry-After: 10
Retry-After: 6m5s
Retry-After: Sun, 27 Jun 2024 12:16:24 GMT
```

--------------------------------

### Verifying QStash Webhook Signature (TypeScript)

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Verifies the signature of an incoming webhook request. It retrieves the signature from the `Upstash-Signature` header and the request body, then uses the `receiver.verify` method to validate them. Returns `true` if the signature is valid, `false` otherwise.

```typescript
const body = await request.text();

const isValid = await receiver.verify({
  signature: request.headers.get("Upstash-Signature")!,
  body,
});
```

--------------------------------

### Add Helicone Analytics to Anthropic LLM Request with QStash

Source: https://upstash.com/docs/qstash/integrations/anthropic

Includes Helicone analytics for monitoring LLM usage when sending requests to Anthropic via QStash. This is done by passing the Helicone API key within the `analytics` object in the request configuration.

```typescript
await client.publishJSON({
  api: {
    name: "llm",
    provider: anthropic({ token: "<ANTHROPIC_TOKEN>" }),
    analytics: { name: "helicone", token: process.env.HELICONE_API_KEY! },
  },
  body: { model: "claude-3-5-sonnet-20241022", messages: [{ role: "user", content: "Hello!" }] },
  callback: "https://example.com/callback",
});
```

--------------------------------

### List Schedules - cURL, TypeScript, Python

Source: https://upstash.com/docs/qstash/howto/delete-schedule

Retrieves a list of all schedules associated with your Upstash QStash account. This is useful for finding the schedule ID required for deletion. Requires an authorization token.

```shell
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const allSchedules = await client.schedules.list();
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.list()
```

--------------------------------

### Dead Letter Queue (DLQ) Operations

Source: https://upstash.com/docs/qstash/howto/handling-failures

QStash automatically moves failed messages to the Dead Letter Queue (DLQ). You can then retrieve messages from the DLQ for inspection or retry them.

```APIDOC
## Dead Letter Queue (DLQ)

### Description
The Dead Letter Queue stores messages that failed to be published. You can retrieve messages from the DLQ to investigate failures or retry publishing.

### Related Endpoints
- **Get Message from DLQ**: `/qstash/api/dlq/getMessage`
- **Delete Message from DLQ**: `/qstash/api/dlq/deleteMessage`
- **Publish Message**: `/qstash/api/publish` (to retry a message from DLQ)
```

--------------------------------

### Publish Message with Absolute Delay

Source: https://upstash.com/docs/qstash/features/delay

Publish a message to be delivered at a specific future time. The delivery time is specified using the `Upstash-Not-Before` header as a Unix timestamp in seconds (UTC).

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a given URL to be delivered at a specific future time.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Set to `application/json`.
- **Upstash-Not-Before** (integer) - Optional - The Unix timestamp (seconds, UTC) at which the message should be delivered. Overrides `Upstash-Delay` if both are present.

### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Not-Before: 1657104947" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

### Request Example (TypeScript)
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
    url: "https://my-api...",
    body: { hello: "world" },
    notBefore: 1657104947, // Unix timestamp in seconds
});
```

### Request Example (Python)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    not_before=1657104947, # Unix timestamp in seconds
)
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```
```

--------------------------------

### Failure Callback Request Body Structure

Source: https://upstash.com/docs/qstash/features/callbacks

Details the structure of the JSON object received by the failure callback URL when a message delivery fails.

```APIDOC
## Failure Callback Request Body

### Description
When a message delivery fails after all retries, a callback is sent to the configured `Upstash-Failure-Callback` URL. The body of this callback is a JSON object containing details about the failure.

### Structure
```json
{
  "status": 400,
  "header": { "key": ["value"] },         // Response header
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==", // base64 encoded response body
  "retried": 3,                           // How many times we retried to deliver the original message
  "maxRetries": 3,                        // Number of retries before the message assumed to be failed to delivered.
  "dlqId": "1725323658779-0",             // Dead Letter Queue id. This can be used to retrieve/remove the related message from DLQ.
  "sourceMessageId": "msg_xxx",           // The ID of the message that triggered the callback
  "topicName": "myTopic",                 // The name of the URL Group (topic) if the request was part of a topic
  "endpointName": "myEndpoint",           // The endpoint name if the endpoint is given a name within a topic
  "url": "http://myurl.com",              // The destination url of the message that triggered the callback
  "method": "GET",                        // The http method of the message that triggered the callback
  "sourceHeader": { "key": "value" },     // The http header of the message that triggered the callback
  "sourceBody": "YmFzZTY0kZWQgcm9keQ==",  // The base64 encoded body of the message that triggered the callback
  "notBefore": "1701198458025",           // The unix timestamp of the message that triggered the callback is/will be delivered in milliseconds
  "createdAt": "1701198447054",           // The unix timestamp of the message that triggered the callback is created in milliseconds
  "scheduleId": "scd_xxx",                // The scheduleId of the message if the message is triggered by a schedule
  "callerIP": "178.247.74.179"            // The IP address where the message that triggered the callback is published from
}
```
```

--------------------------------

### Delay in Schedules

Source: https://upstash.com/docs/qstash/features/delay

When using schedules, delays can only be applied using the `Upstash-Delay` header. This delay affects the delivery of messages generated by the schedule, not the schedule's trigger time.

```APIDOC
## Schedules with Delay

### Description
Schedules can incorporate a delay for the messages they generate. This delay is applied using the `Upstash-Delay` header during schedule creation or message publication, ensuring messages are delivered after the specified duration from their creation time.

### Method
POST (for creating schedules or publishing messages)

### Endpoint
(Relevant schedule or publish endpoints)

### Headers (for applying delay to messages generated by schedules)
- **Upstash-Delay** (string) - Optional - The duration to delay the message delivery for messages created by the schedule. Format: `<number><unit>` (e.g., `30s`).

### Example
If a schedule is set to trigger every hour and is configured with an `Upstash-Delay` of `30s`, the messages generated by this schedule will be created at the scheduled time but will only be delivered 30 seconds later.

### Note
This delay mechanism applies specifically to the message delivery time and does not alter the schedule's execution frequency.
```
```

