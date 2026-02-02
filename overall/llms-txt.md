```
### Install QStash Python SDK

Source: https://upstash.com/docs/qstash/sdks/py/gettingstarted

Installs the QStash Python SDK using pip. This is the first step to integrate QStash into your Python application.

```bash
pip install qstash
```

--------------------------------

### Install @upstash/qstash via NPM

Source: https://upstash.com/docs/qstash/sdks/ts/gettingstarted

This command installs the Upstash QStash SDK using npm. Ensure you have Node.js and npm installed on your system.

```bash
npm install @upstash/qstash
```

--------------------------------

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

### Project Setup with C3 CLI (npm)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initiates a new Cloudflare worker project using the create-cloudflare-cli (C3) with npm. Guides through project configuration and installs Wrangler.

```shell
npm create cloudflare@latest
```

--------------------------------

### Project Setup with C3 CLI (yarn)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initiates a new Cloudflare worker project using the create-cloudflare-cli (C3) with yarn. Guides through project configuration and installs Wrangler.

```shell
yarn create cloudflare@latest
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

### QStash Python SDK Synchronous Client Usage

Source: https://upstash.com/docs/qstash/sdks/py/gettingstarted

Demonstrates how to initialize and use the synchronous QStash client in Python. This client is suitable for straightforward API calls where immediate responses are expected.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(...)
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

### QStash Python SDK Client with Custom Retry Configuration

Source: https://upstash.com/docs/qstash/sdks/py/gettingstarted

Illustrates how to configure custom retry policies when initializing the QStash Python client. This allows fine-tuning the behavior for handling transient network issues for outgoing requests.

```python
from qstash import QStash

client = QStash(
    "<QSTASH_TOKEN>",
    retry={
        "retries": 3,
        "backoff": lambda retry_count: (2**retry_count) * 20,
    },
)
```

--------------------------------

### Initialize Upstash QStash Client (TypeScript)

Source: https://upstash.com/docs/qstash/sdks/ts/gettingstarted

Initializes the Upstash QStash client with your QStash token. This is the basic setup required to interact with the QStash API.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
});
```

--------------------------------

### Install Vercel CLI for deployment

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This bash command installs the Vercel Command Line Interface (CLI) globally on your system. The Vercel CLI is used for deploying projects to Vercel, a platform for frontend developers.

```bash
npm install -g vercel
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

### QStash Retry Delay Examples

Source: https://upstash.com/docs/qstash/api-refence/messages/publish-a-message

Examples demonstrating how to customize retry delay using mathematical expressions. The 'retried' variable represents the number of previous retry attempts (0 for the first retry).

```text
- 1000: Fixed 1 second delay
- 1000 * (1 + retried): Linear backoff
- pow(2, retried) * 1000: Exponential backoff
- max(1000, pow(2, retried) * 100): Exponential with minimum 1s delay
```

--------------------------------

### QStash Python SDK Asynchronous Client Usage

Source: https://upstash.com/docs/qstash/sdks/py/gettingstarted

Shows how to set up and use the asynchronous QStash client for non-blocking operations in Python. This is ideal for applications that need to handle many operations concurrently without waiting for each to complete.

```python
import asyncio

from qstash import AsyncQStash


async def main():
    client = AsyncQStash("<QSTASH_TOKEN>")
    await client.message.publish_json(...)


asyncio.run(main())
```

--------------------------------

### Create and Get a Queue with Parallelism (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/queues

This snippet demonstrates how to create or update a queue with a specified parallelism level using the QStash Python client. It then retrieves and prints the queue's configuration. Ensure you have the QStash client installed and a valid QSTASH_TOKEN.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=2)

print(client.queue.get(queue_name))
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

### Install Vercel CLI

Source: https://upstash.com/docs/qstash/overall/llms-txt

Installs the Vercel Command Line Interface (CLI) globally, which is used for deploying projects to Vercel.

```bash
npm install -g vercel
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

### Deploy Python App to Vercel CLI

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Commands to install the Vercel CLI globally and then initiate the deployment process for the Python application. This assumes the application is set up for deployment in the current directory.

```bash
npm install -g vercel
vercel
```

--------------------------------

### Deploy project using Vercel CLI

Source: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs

This bash command initiates the deployment process for your project using the Vercel CLI. It guides you through the deployment steps, such as selecting a scope and project settings, and ultimately deploys your application to Vercel.

```bash
vercel
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

### Deploy Application with Flyctl

Source: https://upstash.com/docs/qstash/quickstarts/fly-io/go

Deploys the application to the Fly.io platform. This command assumes the Fly.io CLI is installed and configured.

```bash
flyctl deploy
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

### Install Upstash Redis Package

Source: https://upstash.com/docs/qstash/quickstarts/python-vercel

Installs the necessary Python package 'upstash-redis' to interact with Upstash Redis databases. This package provides the client for database operations.

```bash
pip install upstash-redis
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

### Run QStash CLI Dev Server with Docker

Source: https://upstash.com/docs/qstash/overall/llms-txt

Instructions for running the QStash CLI development server using Docker, including pulling the image and starting the container.

```APIDOC
## Local Development with Docker

### Description
This section provides instructions on how to run the QStash CLI development server locally using Docker. This is useful for testing and development purposes.

### Steps

1.  **Pull the QStash Docker Image**
    *   **Command**: `docker pull public.ecr.aws/upstash/qstash:latest`
    *   **Description**: Fetches the latest QStash Docker image from the public ECR repository.

2.  **Run the Docker Container**
    *   **Command**: `docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev`
    *   **Description**: Starts a QStash development server container. The `-p 8080:8080` flag maps port 8080 on your host machine to port 8080 inside the container, making the development server accessible.

### Usage
After running the command, the QStash CLI development server will be available at `http://localhost:8080`.
```

--------------------------------

### Get QStash Queue Configuration

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves the configuration details for a specified QStash queue, including its parallelism settings. This allows users to inspect the current settings of an existing queue. Examples are provided for cURL, TypeScript, and Python.

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

### Initialize Upstash QStash Client with Custom Retry (TypeScript)

Source: https://upstash.com/docs/qstash/sdks/ts/gettingstarted

Initializes the Upstash QStash client with custom retry settings. You can configure the number of retries and the backoff strategy. Note that this applies to requests to QStash, not QStash's internal retries.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
  retry: {
    retries: 3,
    backoff: retry_count => 2 ** retry_count * 20,
  },
});
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

### Create Schedule Example (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Example using curl to create a new schedule for sending messages. It requires an Authorization header with a Bearer token, a Content-Type, an Upstash-Cron expression for scheduling, and the destination URL. An optional JSON payload can be included in the request body.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json" \
    -H "Upstash-Cron: 0 0 * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
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

### Get Signing Keys

Source: https://upstash.com/docs/qstash/api-refence/signing-keys/get-signing-keys

Retrieves your current and next signing keys for QStash. This is useful for verifying message signatures.

```APIDOC
## GET /v2/keys

### Description
Retrieve your current and next signing keys.

### Method
GET

### Endpoint
/v2/keys

### Parameters

#### Query Parameters
- **qstash_token** (string) - Required - QStash authentication token passed as a query parameter.

### Request Example
```http
GET /v2/keys?qstash_token=YOUR_QSTASH_TOKEN
```

### Response
#### Success Response (200)
- **current** (string) - The current signing key.
- **next** (string) - The next signing key.

#### Response Example
```json
{
  "current": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyLCJjdXJyZW50Ijp0cnVlfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c",
  "next": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyLCJuZXh0Ijp0cnVlfQ.g6z_W7tNlQyUf7Y9r2wV0mQ6dJ8sX3zP5w7uY9v1Z0k"
}
```
```

--------------------------------

### Publish JSON with Callback and GET Method (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes a JSON message to a URL using the GET method and specifies callback and failure callback URLs. This is useful for long-running functions where QStash needs to return the response to a callback URL. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    callback="https://my-callback...",
    failure_callback="https://my-failure-callback...",
    method="GET",
)
```

--------------------------------

### Initialize Upstash QStash Client with Telemetry Disabled (TypeScript)

Source: https://upstash.com/docs/qstash/sdks/ts/gettingstarted

Initializes the Upstash QStash client with telemetry explicitly disabled. This prevents the SDK from sending anonymous telemetry data.

```typescript
const client = new Client({
  token: "<QSTASH_TOKEN>",
  enableTelemetry: false,
});
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

### Deploy Python App to Vercel CLI

Source: https://upstash.com/docs/qstash/overall/llms-txt

Commands to install the Vercel CLI globally and then initiate the deployment process for the Python application. This assumes the application is set up for deployment in the current directory.

```bash
npm install -g vercel
vercel
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

### QStash Batch Request Example

Source: https://upstash.com/docs/qstash/overall/llms-txt

Example of a JSON payload for making a batch request to QStash. This payload consists of an array of objects, where each object specifies a destination URL.

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

--------------------------------

### QStash Publish Message Request Example (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Example of publishing a JSON message to a specified URL using the Upstash QStash TypeScript SDK. This shows how to configure the client and call the publishJSON method with message details and callback URLs.

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

--------------------------------

### Get QStash Message Logs

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve logs for published messages, with optional filtering capabilities. This allows monitoring message delivery and processing. The examples demonstrate how to fetch logs using curl, a TypeScript client, and a Python client.

```shell
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

```typescript
import { Client } from "@upstash/qstash";

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

### QStash Request Example

Source: https://upstash.com/docs/qstash/overall/llms-txt

An example JSON payload demonstrating how to structure a batch request to the QStash API for LLM (Large Language Model) tasks. Each object in the array specifies the API to call, the provider (e.g., Anthropic) with its token, the message body for the LLM, and a callback URL for receiving the results.

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

--------------------------------

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/url-groups/add-endpoint

Shows how to authenticate QStash API requests using the `qstash_token` query parameter when headers are not feasible.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
If you cannot set the `Authorization` header, you can authenticate your QStash API requests by appending the `qstash_token` query parameter to your request URL.

### Method
All HTTP Methods (e.g., POST, GET, DELETE)

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
(Responses vary based on the specific endpoint being called. Authentication is a prerequisite.)

#### Success Response (200)
(Details depend on the specific API call)

#### Response Example
(Details depend on the specific API call)
```

--------------------------------

### QStash Library Installation

Source: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers

Installs the official Upstash QStash library for Node.js. This library provides the necessary tools to interact with QStash services, including receiving and verifying webhooks.

```bash
npm install @upstash/qstash
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

### Run QStash CLI Dev Server with NPX

Source: https://upstash.com/docs/qstash/howto/local-development

Use NPX to run the QStash CLI development server. This command starts the server locally, allowing you to test QStash features. You can specify a different port using the -port flag. This method is convenient for quick local testing.

```bash
npx @upstash/qstash-cli dev

# Start on a different port
npx @upstash/qstash-cli dev -port=8081
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

### Run QStash CLI Dev Server with Binary

Source: https://upstash.com/docs/qstash/howto/local-development

Instructions for running the QStash CLI development server after downloading the binary directly. Extract the archive file and then execute the 'qstash dev' command from your terminal. This method bypasses package managers.

```bash
$ ./qstash dev
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

### QStash JWT Payload Example

Source: https://upstash.com/docs/qstash/overall/llms-txt

An example of the JWT payload found in the 'Upstash-Signature' header, including issuer, subject, expiration, and other relevant details.

```APIDOC
## JWT Payload Example

### Description
An example of the JWT payload used for signature verification in QStash requests.

### Response Example
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

### Fields
- **iss** (string) - Issuer of the JWT.
- **sub** (string) - Subject of the JWT (e.g., the endpoint URL).
- **exp** (integer) - Expiration time of the JWT.
- **nbf** (integer) - Not before time of the JWT.
- **iat** (integer) - Issued at time of the JWT.
- **jti** (string) - JWT ID.
- **body** (string) - Base64 encoded hash of the request body.
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

### Get Message Details using QStash API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves details for a specific message using its ID. This functionality is available only while the message is being processed by QStash. Requires authentication and the message ID as a path parameter. An example using cURL is provided.

```shell
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### QStash API Authentication using Query Parameter (Messages Get)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Explains how to use the `qstash_token` query parameter for authentication when header authentication is not feasible, specifically for the messages get endpoint.

```APIDOC
## QStash API Authentication using Query Parameter (Messages Get)

### Description
When setting the `Authorization` header is not feasible, you can authenticate your QStash API requests by including your `QSTASH_TOKEN` as the `qstash_token` query parameter. This example focuses on the messages get endpoint but applies generally.

### Method
This example uses cURL, but the principle applies to any HTTP client.

### Endpoint
`https://qstash.upstash.io/v2/messages/...?qstash_token=<QSTASH_TOKEN>` (Example endpoint for getting messages)

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/messages/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
(Response details depend on the specific endpoint being called)

#### Response Example
(Response example depends on the specific endpoint being called)
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

### Publish with Callback, Failure Callback, and GET Method

Source: https://upstash.com/docs/qstash/sdks/ts/examples/publish

This snippet illustrates publishing a message with specified callback and failure callback URLs. It also demonstrates changing the HTTP method from the default POST to GET. This is useful for long-running functions where QStash needs to return the response to a callback URL.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  callback: "https://my-callback...",
  failureCallback: "https://my-failure-callback...",
  method: "GET",
});
```

--------------------------------

### QStash API Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/url-groups/add-endpoint

Demonstrates how to authenticate QStash API requests using the Authorization header with a Bearer token.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
Authenticate your requests to the QStash API by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer token.

### Method
All HTTP Methods (e.g., POST, GET, DELETE)

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
(Responses vary based on the specific endpoint being called. Authentication is a prerequisite.)

#### Success Response (200)
(Details depend on the specific API call)

#### Response Example
(Details depend on the specific API call)
```

--------------------------------

### GET /v2/logs - Get Message Logs

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve logs for all published messages. Filtering options may be available. Requires authentication.

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

### GET /v2/flowControl/{flowControlKey}

Source: https://upstash.com/docs/qstash/api-refence/flow-control/get-flow-control-key

Fetches the details of a specified Flow Control key, including its current waitlist size.

```APIDOC
## GET /v2/flowControl/{flowControlKey}

### Description
Get details of a specific Flow Control key.

### Method
GET

### Endpoint
`/v2/flowControl/{flowControlKey}`

### Parameters
#### Path Parameters
- **flowControlKey** (string) - Required - The Flow Control key to retrieve

### Request Example
```json
{
  "example": "No request body needed for this GET request."
}
```

### Response
#### Success Response (200)
- **flowControlKey** (string) - The flow control key name
- **waitlistSize** (integer) - The number of messages waiting due to flow control configuration.

#### Response Example
```json
{
  "flowControlKey": "my_key",
  "waitlistSize": 5
}
```

#### Error Response (404)
- **error** (string) - Error message

#### Error Response Example
```json
{
  "error": "Flow Control key not found"
}
```
```

--------------------------------

### GET /v2/queues/{queueName}

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves the details of a specific queue. This endpoint allows you to get information about a particular queue, including its name and current parallelism settings.

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

### Get Flow Control Key Details - OpenAPI Spec

Source: https://upstash.com/docs/qstash/api-refence/flow-control/get-flow-control-key

This OpenAPI specification defines the GET endpoint for retrieving details of a specific Flow Control key. It includes path parameters, response schemas for success (200 OK) and errors (404 Not Found), and authentication methods.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/flowControl/{flowControlKey}:
    get:
      tags:
        - Flow Control
      summary: Get Flow Control Key
      description: Get details of a specific Flow Control key
      parameters:
        - name: flowControlKey
          in: path
          required: true
          schema:
            type: string
          description: The Flow Control key to retrieve
      responses:
        '200':
          description: Flow control key details
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/FlowControlKey'
        '404':
          description: Flow Control key not found
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
components:
  schemas:
    FlowControlKey:
      type: object
      properties:
        flowControlKey:
          type: string
          description: The flow control key name
        waitlistSize:
          type: integer
          description: The number of messages waiting due to flow control configuration.
    Error:
      type: object
      required:
        - error
      properties:
        error:
          type: string
          description: Error message
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

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

### Get all logs with pagination

Source: https://upstash.com/docs/qstash/sdks/ts/examples/logs

Retrieves all logs, implementing pagination using a cursor to handle large result sets.

```APIDOC
## GET /v2/logs

### Description
Retrieves logs with pagination support using a cursor. This is useful for handling large numbers of logs efficiently.

### Method
GET

### Endpoint
/v2/logs

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - The cursor to fetch the next set of logs.

### Request Example
(No request body for GET)

### Response
#### Success Response (200)
- **logs** (array) - An array of log objects.
- **cursor** (string) - The cursor for the next page of results, or null if there are no more logs.

#### Response Example
{
  "logs": [
    {
      "messageId": "msg_abc123",
      "status": "DELIVERED",
      "tag": "email-campaign",
      "createdAt": 1678886400,
      "deduplicationId": "dedup_xyz789"
    }
  ],
  "cursor": "next_cursor_value"
}
```

--------------------------------

### QStash API Authentication

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessages

This section details the methods for authenticating requests to the QStash API. You will need your QSTASH_TOKEN, which can be found in the QStash console.

```APIDOC
## QStash API Authentication

### Description
This section details the methods for authenticating requests to the QStash API. You will need your QSTASH_TOKEN, which can be found in the QStash console.

### Method 1: Bearer Token

Use the `Authorization` header with a `Bearer` token.

### Endpoint
Any QStash API endpoint.

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\ldots \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Method 2: Query Parameter

Alternatively, you can use the `qstash_token` query parameter if setting headers is not possible.

### Endpoint
Any QStash API endpoint.

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QSTASH_TOKEN

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/\ldots?qstash_token=<QSTASH_TOKEN>
```

### Security Note
Always keep your token safe and reset it if you suspect it has been compromised.
```

--------------------------------

### Get a Schedule

Source: https://upstash.com/docs/qstash/api-refence/schedules/get-a-schedule

Retrieves the details of a specific schedule by its ID.

```APIDOC
## GET /v2/schedules/{scheduleId}

### Description
Get details of a specific schedule.

### Method
GET

### Endpoint
/v2/schedules/{scheduleId}

### Parameters
#### Path Parameters
- **scheduleId** (string) - Required - The ID of the schedule to retrieve.

### Request Example
(No request body for GET request)

### Response
#### Success Response (200)
- **scheduleId** (string) - Unique identifier for the schedule
- **cron** (string) - The cron expression used to schedule the message
- **destination** (string) - The destination URL or URL Group name
- **createdAt** (integer) - The creation timestamp of the schedule in unix milliseconds
- **method** (string) - The HTTP method used for the scheduled message
- **header** (object) - Map of header names to arrays of header values
- **body** (string) - The body of the scheduled message
- **retries** (integer) - The number of retries for the scheduled message
- **delay** (integer) - The delay in seconds before the scheduled message is sent
- **callback** (string) - The callback URL for the scheduled message
- **failureCallback** (string) - The failure callback URL for the scheduled message
- **callerIp** (string) - The IP address of the client that created the schedule
- **isPaused** (boolean) - Whether the schedule is paused
- **flowControlKey** (string) - The flow control key used for rate limiting
- **parallelism** (integer) - The parallelism value used for flow control
- **rate** (integer) - The rate value used for flow control
- **period** (integer) - The period value used for flow control
- **retryDelayExpression** (string) - The retry delay expression used for calculating retry delays
- **label** (string) - The label assigned to the scheduled message
- **lastScheduleTime** (integer) - The last time the schedule was triggered in unix milliseconds
- **nextScheduleTime** (integer) - The next scheduled trigger time in unix milliseconds
- **lastScheduleStates** (object) - The states of the last scheduled messages

#### Error Response (404)
- **error** (string) - Error message

#### Response Example
```json
{
  "scheduleId": "sched_123",
  "cron": "* * * * *",
  "destination": "https://example.com/webhook",
  "createdAt": 1678886400000,
  "method": "POST",
  "header": {
    "Content-Type": ["application/json"]
  },
  "body": "{\"message\": \"Hello World\"}",
  "retries": 3,
  "delay": 0,
  "callback": "https://example.com/callback",
  "failureCallback": "https://example.com/failure",
  "callerIp": "192.168.1.1",
  "isPaused": false,
  "flowControlKey": "flow_abc",
  "parallelism": 10,
  "rate": 100,
  "period": 60,
  "retryDelayExpression": "$random(1,5)",
  "label": "my-schedule",
  "lastScheduleTime": 1678886400000,
  "nextScheduleTime": 1678886460000,
  "lastScheduleStates": {
    "status": "success"
  }
}
```
```json
{
  "error": "Schedule not found"
}
```
```

--------------------------------

### Get a Queue

Source: https://upstash.com/docs/qstash/api-refence/queues/get-a-queue

Fetches details for a specified queue by its name. This includes information like creation date, last update, parallelism settings, pause status, and message lag.

```APIDOC
## GET /v2/queues/{queueName}

### Description
Get details of a specific queue.

### Method
GET

### Endpoint
/v2/queues/{queueName}

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to retrieve.

### Request Example
```json
{
  "example": "No request body for GET request."
}
```

### Response
#### Success Response (200)
- **name** (string) - The name of the queue.
- **createdAt** (integer) - The creation timestamp of the queue in Unix milliseconds.
- **updatedAt** (integer) - The last update timestamp of the queue in Unix milliseconds.
- **parallelism** (integer) - The number of parallel consumers consuming from the queue.
- **paused** (boolean) - Whether the queue is paused.
- **lag** (integer) - The number of unprocessed messages that exist in the queue.

#### Response Example
```json
{
  "name": "my-queue",
  "createdAt": 1678886400000,
  "updatedAt": 1678886400000,
  "parallelism": 10,
  "paused": false,
  "lag": 0
}
```

#### Error Response (400)
- **error** (string) - Queue name is invalid. Queue names can only contain alphanumeric characters, hyphens, periods, and underscores.

#### Error Response (404)
- **error** (string) - Queue not found
```

--------------------------------

### Set Up ngrok Tunnel and Publish Message

Source: https://upstash.com/docs/qstash/overall/llms-txt

ngrok is a powerful tool for creating secure tunnels to your local server. This snippet shows how to set up ngrok with your authentication token, start a tunnel to your application's port, and then use curl to publish a message to your tunneled endpoint via QStash.

```APIDOC
## Set Up ngrok Tunnel and Publish Message

### Description
ngrok is a powerful tool for creating secure tunnels to your local server. This snippet shows how to set up ngrok with your authentication token, start a tunnel to your application's port, and then use curl to publish a message to your tunneled endpoint via QStash.

### Setup ngrok

```bash
ngrok config add-authtoken XXX
```

### Start ngrok Tunnel

```bash
$ ngrok http 3000
```

### Publish Message to Tunneled Endpoint

```bash
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://e02f-2a02-810d-af40-5284-b139-58cc-89df-b740.eu.ngrok.io/api/webhooks'
```
```

--------------------------------

### Publish Message with Custom Headers

Source: https://upstash.com/docs/qstash/overall/llms-txt

This example demonstrates how to publish a JSON message with a custom forwardable header using cURL.

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

### Get Message Details

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message using its ID with the Upstash QStash SDK for Python. The client is initialized with a QStash token, and the get method fetches message information.

```APIDOC
## GET /v2/message/{messageId}

### Description
Retrieve details for a specific message using its ID.

### Method
GET

### Endpoint
`/v2/message/{messageId}`

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The unique identifier of the message.

### Request Example (Python)
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

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier of the message.
- **url** (string) - The target URL the message was sent to.
- **body** (object) - The content of the message.
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

### Upstash Workflow - Trigger Workflow API Request Example

Source: https://upstash.com/docs/qstash/overall/llms-txt

This example shows how to trigger an Upstash Workflow execution using a POST request to the QStash API. It requires specifying the workflow URL, authentication token, content type, and optionally a run ID and retry count. The request body contains user-specific details required for the workflow.

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

### Get URL Group

Source: https://upstash.com/docs/qstash/api-refence/url-groups/get-a-url-group

Retrieves details of a specific URL Group by its name.

```APIDOC
## GET /v2/topics/{urlGroupName}

### Description
Retrieves details of a specific URL Group.

### Method
GET

### Endpoint
/v2/topics/{urlGroupName}

### Parameters
#### Path Parameters
- **urlGroupName** (string) - Required - The name of the URL Group to retrieve.

### Request Example
```json
{
  "example": ""
}
```

### Response
#### Success Response (200)
- **name** (string) - URL Group name
- **createdAt** (integer) - Creation timestamp of URL Group in Unix milliseconds
- **updatedAt** (integer) - Last update timestamp of URL Group in Unix milliseconds
- **endpoints** (array) - Array of endpoint objects
  - **name** (string) - The name of the endpoint
  - **url** (string) - The URL of the endpoint

#### Response Example
```json
{
  "name": "example-url-group",
  "createdAt": 1678886400000,
  "updatedAt": 1678886400000,
  "endpoints": [
    {
      "name": "endpoint1",
      "url": "https://example.com/hook1"
    }
  ]
}
```

#### Error Response (404)
- **error** (string) - Error message

#### Response Example
```json
{
  "error": "URL Group not found"
}
```
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

### Create Python Project Directory

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes a new directory for a Python application and navigates into it. This is a foundational step for setting up the project structure for a Python-based application, likely for deployment on platforms like Vercel.

```bash
mkdir clean-db-cron
cd clean-db-cron
```

--------------------------------

### Events API - Get all events with pagination

Source: https://upstash.com/docs/qstash/sdks/py/examples/events

Demonstrates how to fetch all events from QStash, utilizing a cursor for pagination to manage potentially large result sets. The loop continues until no more cursors are available, ensuring all events are retrieved.

```APIDOC
## GET /v1/events

### Description
Fetches a paginated list of events. Use the `cursor` parameter to paginate through results.

### Method
GET

### Endpoint
/v1/events

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - The cursor to retrieve the next page of events.

### Request Example
```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

all_events = []
cursor = None
while True:
    res = client.event.list(cursor=cursor)
    all_events.extend(res.events)
    cursor = res.cursor
    if cursor is None:
        break
```

### Response
#### Success Response (200)
- **events** (array) - A list of event objects.
- **cursor** (string) - The cursor for the next page of results. Null if this is the last page.

#### Response Example
```json
{
  "events": [
    {
      "messageId": "msg_abc123",
      "deduplicationId": "dedup_xyz789",
      "providerSenderId": "snd_123",
      "topic": "my-topic",
      "insertedAt": 1678886400,
      "attempts": 1,
      "nextAttemptAt": 1678886400,
      "url": "https://example.com/webhook",
      "body": {
        "key": "value"
      },
      "headers": {
        "Content-Type": "application/json"
      },
      "tags": ["tag1", "tag2"]
    }
  ],
  "cursor": "next_cursor_value"
}
```
```

--------------------------------

### Handling Callbacks in Next.js

Source: https://upstash.com/docs/qstash/overall/llms-txt

Example of a Next.js API route for handling incoming callbacks from Upstash QStash, including signature verification.

```APIDOC
## Handling Callbacks in Next.js

### Description
This example demonstrates how to set up a Next.js API route to handle incoming callbacks from Upstash QStash. It includes decoding the base64-encoded message body and verifying the request's authenticity using `verifySignature`.

### Method
POST (typically for callbacks)

### Endpoint
`/pages/api/callback.js` (within your Next.js project)

### Parameters
(No explicit parameters; handles incoming request body)

### Request Example (Conceptual)
(Incoming request body from Qstash)

### Response
#### Success Response (200)
- **Status** (integer) - 200 - Indicates successful handling of the callback.

### Code Example
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

### Initialize AWS Lambda Project Structure (Bash)

Source: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python

Creates a new directory for the AWS Lambda project and initializes an empty Python file for the Lambda function handler. This sets up the basic file structure required for the project.

```bash
mkdir aws-lambda
cd aws-lambda
touch lambda_function.py
```

--------------------------------

### Schedule Daily Task with QStash

Source: https://upstash.com/docs/qstash/overall/llms-txt

Examples for scheduling a daily task using QStash via cURL, TypeScript SDK, and Python SDK.

```APIDOC
## Schedule Daily Task with QStash

### Description
This section provides examples for scheduling a task to run once a day using QStash. The cron syntax `0 0 * * *` ensures the task executes at midnight every day. Replace placeholders with your actual token and target URL.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/schedules/<destination_url>`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`
- **Upstash-Cron** (string) - Required - Cron syntax for scheduling (e.g., `0 0 * * *` for daily at midnight)
- **Content-type** (string) - Required - `application/json`

#### Request Body
- **(JSON Object)** - Required - The payload for your task.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Cron: 0 0 * * *" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

### Request Example (TypeScript SDK)
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "0 0 * * *",
});
```

### Request Example (Python SDK)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="0 0 * * *",
)
# Async version is also available
```

### Response
(Response details depend on the specific operation)
```

--------------------------------

### Create Python Project Directory

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes a new directory for a Python application and navigates into it. This is a foundational step for setting up project structures.

```APIDOC
## Project Setup

### Description
Initializes a new directory for the Python application and navigates into it.

### Method
Shell Commands

### Endpoint
N/A

### Parameters
None

### Request Example
```bash
mkdir clean-db-cron
cd clean-db-cron
```

### Response
N/A
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

### GET /v2/messages/{messageId}

Source: https://upstash.com/docs/qstash/api-refence/messages/get-a-message

Retrieve details of a specific message by its unique identifier.

```APIDOC
## GET /v2/messages/{messageId}

### Description
Retrieve details of a specific message.

### Method
GET

### Endpoint
/v2/messages/{messageId}

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The identifier of the message to retrieve.

### Response
#### Success Response (200)
- **messageId** (string) - Unique identifier for the message
- **url** (string) - The URL to which the message should be delivered.
- **topicName** (string) - The URL Group (a.k.a. topic) name if this message was sent to a URL Group.
- **endpointName** (string) - The endpoint name of the message if the endpoint is given a name within the URL group.
- **method** (string) - The HTTP method to use for the message.
- **header** (object) - The HTTP headers sent to your API.
- **body** (string) - The body of the message if it is composed of utf8 chars only, empty otherwise.
- **bodyBase64** (string) - The base64 encoded body if the body contains a non-utf8 char only, empty otherwise.
- **maxRetries** (integer) - The number of retries that should be attempted in case of delivery failure.
- **notBefore** (integer) - The unix timestamp in milliseconds before which the message should not be delivered.
- **createdAt** (integer) - The unix timestamp in milliseconds when the message was created.
- **callback** (string) - The url where we send a callback each time the message is attempted to be delivered.
- **failureCallback** (string) - The url where we send a callback to after the message is failed
- **queueName** (string) - The name of the queue if the message is enqueued to a queue.
- **scheduleId** (string) - The scheduleId of the message if the message is triggered by a schedule
- **callerIP** (string) - IP address of the publisher of this message.
- **label** (string) - The label of the message assigned by the user.
- **flowControlKey** (string) - The flow control key used for rate limiting.
- **rate** (integer) - The rate value used for flow control.
- **period** (integer) - The period value used for flow control.
- **parallelism** (integer) - The parallelism value used for flow control.

#### Error Response (404)
- **error** (string) - Error message

### Response Example
#### Success Response (200)
```json
{
  "messageId": "msg_xxxxxx",
  "url": "https://example.com/webhook",
  "topicName": "my-topic",
  "endpointName": "default",
  "method": "POST",
  "header": {
    "Content-Type": ["application/json"]
  },
  "body": "{\"key\": \"value\"}",
  "bodyBase64": "",
  "maxRetries": 3,
  "notBefore": 1678886400000,
  "createdAt": 1678886000000,
  "callback": "https://example.com/callback",
  "failureCallback": "https://example.com/failure-callback",
  "queueName": "my-queue",
  "scheduleId": "sch_yyyyyy",
  "callerIP": "192.168.1.1",
  "label": "my-message-label",
  "flowControlKey": "fc_key_zzzzzz",
  "rate": 10,
  "period": 60,
  "parallelism": 5
}
```
#### Error Response (404)
```json
{
  "error": "Message not found"
}
```
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

### Handling Callbacks in Next.js

Source: https://upstash.com/docs/qstash/overall/llms-txt

Provides an example of how to handle QStash callbacks within a Next.js API route, including necessary steps for decoding the payload and verifying the signature.

```APIDOC
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

### Get Schedule

Source: https://upstash.com/docs/qstash/sdks/ts/examples/schedules

Retrieves details of a specific schedule by its ID.

```APIDOC
## GET /v1/schedules/{scheduleId}

### Description
Retrieves details of a specific schedule by its ID.

### Method
GET

### Endpoint
/v1/schedules/{scheduleId}

### Parameters
#### Path Parameters
- **scheduleId** (string) - Required - The ID of the schedule to retrieve.

### Response
#### Success Response (200)
- **scheduleId** (string) - The ID of the schedule.
- **cron** (string) - The cron expression.
- **destination** (string) - The destination URL or URL Group ID.
- **callback** (string) - The callback URL.
- **failureCallback** (string) - The failure callback URL.
- **isPaused** (boolean) - Indicates if the schedule is paused.

#### Response Example
```json
{
  "scheduleId": "schedule-abc-123",
  "cron": "*/5 * * * *",
  "destination": "https://my-api...",
  "callback": "https://my-callback...",
  "failureCallback": "https://my-failure-callback...",
  "isPaused": false
}
```
```

--------------------------------

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/flow-control/list

This section explains how to authenticate your API requests using the `qstash_token` query parameter. This method is useful in environments where setting request headers is not feasible.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
Authenticate your API requests by including your `QSTASH_TOKEN` as a query parameter named `qstash_token`. This method is an alternative for environments where modifying request headers is not possible.

### Method
All HTTP Methods (GET, POST, PUT, DELETE, etc.)

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
Responses will vary based on the specific endpoint called.

#### Response Example
(Example varies by endpoint)
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

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/api/schedules/list

This section explains how to authenticate API requests using the `qstash_token` query parameter. This method is useful in environments where setting request headers is not feasible.

```APIDOC
## QStash API Authentication - Query Parameter

### Description
When setting request headers is not possible, you can authenticate your QStash API requests by appending the `qstash_token` query parameter to your URL. Ensure your token is kept secure.

### Method
Any (e.g., POST, GET, DELETE)

### Endpoint
`https://qstash.upstash.io/v2/*?qstash_token=<QSTASH_TOKEN>`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash authentication token.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/some/endpoint?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200 OK)
- **(Specific response details depend on the endpoint called)**

#### Response Example
```json
{
  "message": "Request processed successfully"
}
```
```

--------------------------------

### Create Workflow with Steps (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Define and execute workflows using the Upstash Workflow SDK for Python, integrated with FastAPI. This example showcases sequential steps including sending emails and managing workflow context.

```APIDOC
## POST /workflow

### Description
Create and execute a workflow with defined steps using the Upstash Workflow SDK for Python.

### Method
POST

### Endpoint
`/workflow`

### Parameters
#### Request Body
- **userId** (string) - Required - The ID of the user for the workflow.
- **email** (string) - Required - The email address for the user.
- **name** (string) - Required - The name of the user.

### Request Example
```json
{
  "userId": "user123",
  "email": "user@example.com",
  "name": "John Doe"
}
```

### Response
#### Success Response (200)
- **workflowId** (string) - The ID of the executed workflow.
- **status** (string) - The status of the workflow execution.
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

### GET /v2/schedules - List All Schedules

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve a list of all scheduled messages. This endpoint requires authentication.

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

### Authenticate with Bearer Token Header

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessage

This method demonstrates how to include your QStash token in the 'Authorization' header for API requests. It's the recommended approach when possible.

```cURL
curl https://qstash.upstash.io/v2/publish/ \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Publish Messages to FIFO Queue

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publish messages to a queue for First-In, First-Out (FIFO) processing. This example demonstrates how to enqueue a JSON message using cURL, the TypeScript SDK, or the Python SDK.

```APIDOC
## Publish Messages to FIFO Queue

### Description
Publish messages to a queue for First-In, First-Out (FIFO) processing.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/enqueue/<queueName>/<url>`

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the FIFO queue.
- **url** (string) - Required - The URL to enqueue the message for.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example (cURL)
```shell
curl -XPOST -H 'Authorization: Bearer XXX' \
                -H "Content-type: application/json" \
                'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' \
                -d '{"message":"Hello, World!"}'
```

### Request Example (TypeScript)
```typescript
import { Client } from "@upstash/qstash";

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

### Request Example (Python)
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

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the enqueued message.
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

### Authenticate with Query Parameter using cURL

Source: https://upstash.com/docs/qstash/api/dlq/deleteMessages

This snippet shows how to use the `qstash_token` query parameter for authentication with cURL. This method is useful in environments where modifying request headers is not feasible.

```Bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

### Publish Message

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a message to a specified URL using a cURL example. Requires authentication and sets the content type.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a specified URL. This endpoint is used for sending one-time messages.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Path Parameters
- **url** (string) - Required - The destination URL where the message will be published.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication (e.g., `Bearer <QSTASH_TOKEN>`)
- **Content-Type** (string) - Required - Specifies the format of the request body (e.g., `application/json`)

#### Request Body
- **body** (object) - Required - The content of the message to be published. The structure depends on the `Content-Type`.

### Request Example
```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://winter-cherry-9545.fly.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{\"hello\": \"world\"}"
```

### Response
#### Success Response (200 OK)
Indicates the message was successfully published.

#### Response Example
```json
{
  "messageId": "msg_xxxxxx"
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

### Verify QStash Message Signature with TypeScript SDK

Source: https://upstash.com/docs/qstash/sdks/ts/examples/receiver

This snippet demonstrates how to initialize the `Receiver` and verify an incoming message signature using the QStash TypeScript SDK. It requires your current and next signing keys, the request body, the signature from the headers, and your site URL. Ensure you have the `@upstash/qstash` package installed.

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

### Publish JSON Message to QStash

Source: https://upstash.com/docs/qstash/overall/llms-txt

This example demonstrates how to publish a JSON message to a specified URL using the Upstash QStash client in a Next.js application.

```APIDOC
## POST /v2/publish/json

### Description
Publishes a JSON message to a given URL.

### Method
POST

### Endpoint
/v2/publish/json

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **url** (string) - Required - The URL to send the message to.
- **body** (object) - Required - The JSON payload of the message.
- **retries** (integer) - Optional - The number of times to retry delivery if it fails.
- **delay** (string) - Optional - The delay before sending the message (e.g., "5s", "1m").

### Request Example
```json
{
  "url": "https://your-api-endpoint.com",
  "body": {
    "key": "value"
  },
  "retries": 3,
  "delay": "10s"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_xxxxxxxxxxxxxxxxx"
}
```
```

--------------------------------

### QStash API Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/schedules/list

This section details how to authenticate API requests using a Bearer Token in the Authorization header. This is the recommended method for security.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
Authenticate your requests to the QStash API by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer token. This is the standard and recommended method for securing your API interactions.

### Method
Any (e.g., POST, GET, DELETE)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/some/endpoint \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200 OK)
- **(Specific response details depend on the endpoint called)**

#### Response Example
```json
{
  "message": "Request processed successfully"
}
```
```

--------------------------------

### Get a message from the DLQ

Source: https://upstash.com/docs/qstash/sdks/py/examples/dlq

Retrieves a specific message from the Dead Letter Queue (DLQ) by its ID.

```APIDOC
## GET /v2/dlq/{messageId}

### Description
Retrieves a specific message from the Dead Letter Queue (DLQ) by its ID.

### Method
GET

### Endpoint
/v2/dlq/{messageId}

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The ID of the message to retrieve.

### Request Example
```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
msg = client.dlq.get("<dlq-id>")
```

### Response
#### Success Response (200)
- **message** (object) - The message object details.
```

--------------------------------

### Get All Events with Pagination (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/events

Retrieves all events from QStash using a cursor for pagination. This is useful for handling large numbers of events by fetching them in batches. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

all_events = []
cursor = None
while True:
    res = client.event.list(cursor=cursor)
    all_events.extend(res.events)
    cursor = res.cursor
    if cursor is None:
        break
```

--------------------------------

### QStash Signature Verification via SDKs

Source: https://upstash.com/docs/qstash/overall/llms-txt

This section details how to use the QStash SDKs to verify incoming request signatures. It provides code examples for TypeScript, Python, and Go, utilizing the Receiver type for simplified verification. Ensure correct signing keys and URL are provided.

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

```go
import "github.com/qstash/qstash-go"
import "io"

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

### Get Message Details

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message by its ID. This endpoint is only available while the message is being processed.

```APIDOC
## GET /v2/messages/{messageId}

### Description
Retrieve details for a specific message by its ID. This is only available while the message is being processed.

### Method
GET

### Endpoint
`/v2/messages/{messageId}`

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

### Publish JSON to URL Group with Delay and Headers

Source: https://upstash.com/docs/qstash/sdks/ts/examples/publish

This example shows how to publish a JSON message to a URL group, allowing messages to be sent to multiple endpoints simultaneously. It includes a delay and custom headers. The response is an array of message IDs, one for each URL in the group.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  urlGroup: "my-url-group",
  body: { hello: "world" },
  headers: { "test-header": "test-value" },
  delay: "3s",
});

// When publishing to a URL Group, the response is an array of messages for each URL in the URL Group
console.log(res[0].messageId);
```

--------------------------------

### Get URL Group by Name

Source: https://upstash.com/docs/qstash/sdks/py/examples/url-groups

Retrieves a specific URL group by its name, including all the endpoints associated with it.

```APIDOC
## GET /v2/urlgroups/{url_group_name}

### Description
Retrieves a URL group by its name.

### Method
GET

### Endpoint
/v2/urlgroups/{url_group_name}

### Parameters
#### Path Parameters
- **url_group_name** (string) - Required - The name of the URL group to retrieve.

### Response
#### Success Response (200)
- **name** (string) - The name of the URL group.
- **endpoints** (array[object]) - A list of endpoint objects in the URL group.
  - **url** (string) - The URL of the endpoint.

#### Response Example
```json
{
  "name": "my-url-group",
  "endpoints": [
    {"url": "https://my-endpoint-1"},
    {"url": "https://my-endpoint-2"}
  ]
}
```
```

--------------------------------

### QStash API Authentication - Bearer Token

Source: https://upstash.com/docs/qstash/api/flow-control/list

This section details how to authenticate your API requests using a Bearer Token in the Authorization header. This is the recommended method for securing your requests.

```APIDOC
## QStash API Authentication - Bearer Token

### Description
Authenticate your API requests by including your `QSTASH_TOKEN` in the `Authorization` header as a Bearer Token. This is the standard and recommended method for authenticating with the QStash API.

### Method
All HTTP Methods (GET, POST, PUT, DELETE, etc.)

### Endpoint
`https://qstash.upstash.io/v2/*`

### Parameters
#### Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/ \ 
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Response
#### Success Response (200)
Responses will vary based on the specific endpoint called.

#### Response Example
(Example varies by endpoint)
```

--------------------------------

### Publish Message with Custom Headers (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

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

### GET /v2/logs - List Logs

Source: https://upstash.com/docs/qstash/api-refence/logs/list-logs

Retrieves a paginated list of logs for published messages. Supports filtering by various parameters like message ID, state, URL, and time range.

```APIDOC
## GET /v2/logs

### Description
Paginate through logs of published messages. Supports filtering by various parameters.

### Method
GET

### Endpoint
/v2/logs

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - By providing a cursor you can paginate through all of the logs
- **messageId** (string) - Optional - Filter logs by message ID
- **state** (string) - Optional - Filter logs by message state. Possible values: CREATED, ACTIVE, RETRY, ERROR, IN_PROGRESS, DELIVERED, FAILED, CANCEL_REQUESTED, CANCELLED.
- **url** (string) - Optional - Filter logs by destination URL
- **topicName** (string) - Optional - Filter logs by URL Group name
- **scheduleId** (string) - Optional - Filter logs by schedule ID
- **queueName** (string) - Optional - Filter logs by queue name
- **fromDate** (integer) - Optional - Filter logs by starting date, in milliseconds (Unix timestamp). This is inclusive.
- **toDate** (integer) - Optional - Filter logs by ending date, in milliseconds (Unix timestamp). This is inclusive.
- **count** (integer) - Optional - The number of log entries to return. Defaults to 100. Maximum is 100.
- **order** (string) - Optional - The sorting order of logs by timestamp. Possible values: latestFirst, earliestFirst. Defaults to latestFirst.
- **label** (string) - Optional - Filter logs by the label of the message assigned by the user

### Response
#### Success Response (200)
- **cursor** (string) - A cursor which you can use in subsequent requests to paginate through all logs. If no cursor is returned, you have reached the end of the logs.
- **logs** (array) - An array of LogEntry objects.

##### LogEntry Object
- **time** (integer) - The timestamp of the log entry in Unix milliseconds
- **messageId** (string) - The ID of the message

#### Response Example
```json
{
  "cursor": "some_cursor_string",
  "logs": [
    {
      "time": 1678886400000,
      "messageId": "msg_123"
    }
  ]
}
```
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

### Bundle and Zip Lambda Function (Makefile)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Automates the process of installing Python dependencies (like pyjwt), copying Lambda function code, and creating a zip archive for AWS deployment. This ensures all necessary components are bundled correctly for the Lambda function.

```yaml
zip:
    rm -rf dist
	pip3 install --target ./dist pyjwt
	cp lambda_function.py ./dist/lambda_function.py
	cd dist && zip -r lambda.zip .
	mv ./dist/lambda.zip ./

```

--------------------------------

### Next.js Workflow API

Source: https://upstash.com/docs/qstash/overall/llms-txt

An example of how to use Upstash QStash Workflow in a Next.js application to send emails, sleep, call external APIs, and process responses.

```APIDOC
## POST /api/workflow

### Description
This endpoint is part of a Next.js application utilizing Upstash QStash Workflow. It orchestrates a series of steps including sending welcome emails, pausing execution, generating personalized messages using an AI, and sending follow-up emails.

### Method
POST

### Endpoint
/api/workflow

### Parameters
#### Request Body
- **userId** (string) - Required - The ID of the user.
- **email** (string) - Required - The email address of the user.
- **name** (string) - Required - The name of the user.

### Request Example
```json
{
  "userId": "user123",
  "email": "test@example.com",
  "name": "John Doe"
}
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

### Verify JWT Signature

Source: https://upstash.com/docs/qstash/overall/llms-txt

This example shows how to verify the JWT signature of an incoming request using the QStash SDK for Golang. This ensures the authenticity and integrity of requests received from QStash.

```APIDOC
## POST /verify (Implicit in SDK)

### Description
Verifies the JWT signature of an incoming request to ensure authenticity.

### Method
POST (Implicitly handled by the SDK when receiving a webhook)

### Endpoint
Not directly called, but part of the webhook receiving process.

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None (SDK handles verification internally)

#### SDK Initialization Parameters
- **CURRENT_SIGNING_KEY** (string) - Required - The current signing key provided by QStash.
- **NEXT_SIGNING_KEY** (string) - Optional - The next signing key, used for seamless key rotation.

#### Verification Options
- **Signature** (string) - Required - The value of the 'Upstash-Signature' header from the incoming request.
- **Body** (string) - Required - The raw request body.
- **Url** (string) - Optional - Your site's URL, used to verify the origin of the request.

### Request Example (Golang SDK)
```go
import "github.com/qstash/qstash-go"

// Initialize receiver with signing keys
receiver := qstash.NewReceiver("<CURRENT_SIGNING_KEY>", "<NEXT_SIGNING_KEY>")

// Inside your request handler:
// Assuming 'req' is your http.Request object
signature := req.Header.Get("Upstash-Signature")
bodyBytes, err := io.ReadAll(req.Body)
// Handle err
bodyString := string(bodyBytes)

// Verify the signature
err := receiver.Verify(qstash.VerifyOptions{
    Signature: signature,
    Body:      bodyString,
    Url:       "YOUR-SITE-URL", // Optional: specify your site URL
})
// Handle err: If err is not nil, the signature is invalid.
```

### Response
#### Success Response
No explicit response for verification itself; an error indicates failure.

#### Error Response
- **error** (string) - Indicates a verification failure (e.g., invalid signature).

#### Response Example (Error)
```json
{
  "error": "invalid signature"
}
```
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

### Publish JSON Message using Upstash QStash SDK (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Provides a TypeScript example using the Upstash QStash client to publish a JSON message. It shows how to initialize the client with a token, specify the destination URL, the message body as a JavaScript object, and custom headers.

```APIDOC
## Publish JSON Message using Upstash QStash SDK (TypeScript)

### Description
Provides a TypeScript example using the Upstash QStash client to publish a JSON message. It shows how to initialize the client with a token, specify the destination URL, the message body as a JavaScript object, and custom headers. The SDK abstracts the HTTP request details.

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

### fly.io App Launch Command

Source: https://upstash.com/docs/qstash/overall/llms-txt

Command to launch a new application on fly.io for a Go project. This command scans the source code, detects the Go environment, and prompts the user for necessary configuration details like app name and region.

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

### Get a schedule by ID in TypeScript

Source: https://upstash.com/docs/qstash/sdks/ts/examples/schedules

Retrieves details of a specific schedule using its unique identifier. This is useful for inspecting the configuration or status of an existing schedule.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const res = await client.schedules.get("scheduleId");
console.log(res.cron);
```

--------------------------------

### Get QStash Schedule by ID (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Retrieves details of a specific QStash schedule using its unique schedule ID. This function allows inspecting the configuration of an existing schedule.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule = client.schedule.get("<schedule-id>")

print(schedule.cron)
```

--------------------------------

### Publish with Content-Based Deduplication

Source: https://upstash.com/docs/qstash/sdks/ts/examples/publish

This example shows how to enable content-based deduplication for published messages. When enabled, QStash will prevent duplicate messages with the same body content from being processed within a certain timeframe.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  contentBasedDeduplication: true,
});
```

--------------------------------

### Get all messages with pagination using cursor

Source: https://upstash.com/docs/qstash/sdks/py/examples/dlq

Retrieves all messages from the Dead Letter Queue (DLQ) with pagination support using a cursor. This is useful for handling large DLQs.

```APIDOC
## GET /v2/dlq

### Description
Retrieves all messages from the Dead Letter Queue (DLQ) with pagination support using a cursor. This is useful for handling large DLQs.

### Method
GET

### Endpoint
/v2/dlq

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - The cursor to use for pagination. If not provided, the first page of results is returned.

### Request Example
```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

all_messages = []
cursor = None
while True:
    res = client.dlq.list(cursor=cursor)
    all_messages.extend(res.messages)
    cursor = res.cursor
    if cursor is None:
        break
```

### Response
#### Success Response (200)
- **messages** (array) - A list of messages in the DLQ.
- **cursor** (string) - The cursor for the next page of results. Will be null if there are no more pages.
```

--------------------------------

### Get Message Logs (QStash API)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves logs for all published messages using the QStash API. Requires authentication with a Bearer token.

```curl
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = await client.logs()
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

### Get QStash Queue Configuration

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves the current configuration, including parallelism settings, for a specified QStash queue. This allows you to inspect the settings of an existing queue.

```APIDOC
## GET /v2/queues/{queueName}

### Description
Retrieves the configuration for a specified QStash queue.

### Method
GET

### Endpoint
/v2/queues/{queueName}

### Path Parameters
- **queueName** (string) - Required - The name of the queue to retrieve configuration for.

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.

### Response
#### Success Response (200)
- **queueName** (string) - The name of the queue.
- **currentParallelism** (integer) - The current parallelism setting.
- **maxParallelism** (integer) - The maximum allowed parallelism.

### Client Library Examples
#### TypeScript
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const queue = client.queue({
  queueName: "my-queue"
});
const res = await queue.get();
```
#### Python
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.get("my-queue")
```
```

--------------------------------

### List Queues OpenAPI Specification

Source: https://upstash.com/docs/qstash/api-refence/queues/list-queues

This OpenAPI 3.1.0 specification defines the GET /v2/queues endpoint for listing all queues in QStash. It outlines the request, responses, and the schema for a Queue object, including its properties like name, creation/update timestamps, parallelism, paused status, and lag.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/queues:
    get:
      tags:
        - Queues
      summary: List Queues
      description: List all your queues
      responses:
        '200':
          description: List of queues
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Queue'
components:
  schemas:
    Queue:
      type: object
      properties:
        name:
          type: string
          description: The name of the queue.
        createdAt:
          type: integer
          format: int64
          description: The creation timestamp of the queue in Unix milliseconds
        updatedAt:
          type: integer
          format: int64
          description: The last update timestamp of the queue in Unix milliseconds
        parallelism:
          type: integer
          description: The number of parallel consumers consuming from the queue
        paused:
          type: boolean
          description: Whether the queue is paused
        lag:
          type: integer
          description: The number of unprocessed messages that exist in the queue
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

```

--------------------------------

### Publish Anthropic LLM Request

Source: https://upstash.com/docs/qstash/overall/llms-txt

This example shows how to publish a request to an Anthropic LLM model via QStash. It requires both QStash and Anthropic API tokens and specifies a callback URL for handling the asynchronous response.

```APIDOC
## POST /v2/publish/json (LLM API)

### Description
Publishes a request to an LLM API (e.g., Anthropic) through QStash.

### Method
POST

### Endpoint
/v2/publish/json

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Configuration for the LLM API.
  - **name** (string) - Required - Must be "llm".
  - **provider** (object) - Required - The LLM provider configuration.
    - **anthropic** (object) - Configuration for Anthropic.
      - **token** (string) - Required - Your Anthropic API token.
- **body** (object) - Required - The payload for the LLM request (e.g., model, messages).
- **callback** (string) - Required - The URL to which the LLM response should be sent.

### Request Example (TypeScript)
```json
{
  "api": {
    "name": "llm",
    "provider": {
      "anthropic": {
        "token": "<ANTHROPIC_TOKEN>"
      }
    }
  },
  "body": {
    "model": "claude-3-5-sonnet-20241022",
    "messages": [
      { "role": "user", "content": "Summarize recent tech trends."} 
    ]
  },
  "callback": "https://example.com/callback"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_xxxxxxxxxxxxxxxxx"
}
```
```

--------------------------------

### Get DLQ Message

Source: https://upstash.com/docs/qstash/api-refence/dlq/get-a-dlq-message

Retrieves a specific message from the Dead Letter Queue (DLQ). This is useful for inspecting messages that failed processing and may require manual intervention or re-queuing.

```APIDOC
## GET /websites/upstash-qstash/dlq/{messageId}

### Description
Get a specific message from the DLQ.

### Method
GET

### Endpoint
/websites/upstash-qstash/dlq/{messageId}

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The unique identifier of the message to retrieve from the DLQ.

### Response
#### Success Response (200)
- **message** (object) - Details of the DLQ message.
  - **id** (string) - The unique ID of the message.
  - **body** (string) - The message payload.
  - **headers** (object) - The message headers.
  - **url** (string) - The URL the message was intended for.
  - **deduplicationId** (string) - The deduplication ID used for the message.
  - **retries** (integer) - The number of times the message was retried.
  - **next_enqueue_time** (string) - The next scheduled time for the message to be enqueued (if applicable).
  - **created_at** (string) - The timestamp when the message was created.
  - **dlq_at** (string) - The timestamp when the message was moved to the DLQ.

#### Response Example
```json
{
  "message": {
    "id": "msg_abc123",
    "body": "{\"key\": \"value\"}",
    "headers": {
      "Content-Type": "application/json"
    },
    "url": "https://example.com/webhook",
    "deduplicationId": "dedup_xyz789",
    "retries": 3,
    "next_enqueue_time": "2023-10-27T10:00:00Z",
    "created_at": "2023-10-27T09:00:00Z",
    "dlq_at": "2023-10-27T09:30:00Z"
  }
}
```
```

--------------------------------

### Publish JSON Message using Upstash QStash SDK

Source: https://upstash.com/docs/qstash/overall/llms-txt

This TypeScript example utilizes the Upstash QStash client to publish a JSON message. It requires initializing the client with a token and specifying the destination URL and message body.

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

### Create Workflow with Steps using TypeScript in Next.js

Source: https://upstash.com/docs/qstash/overall/llms-txt

Build durable workflows with step-based execution using the Upstash Workflow SDK for TypeScript within a Next.js environment. This example demonstrates sending emails, sleeping, calling an external API, and running sequential steps with error recovery.

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

### Configure Number of Retries for Published Messages

Source: https://upstash.com/docs/qstash/sdks/ts/examples/publish

This example shows how to configure the number of retries for a published message. The maximum number of retries depends on the QStash plan. The snippet sets the `retries` parameter to 1.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  retries: 1,
});
```

--------------------------------

### Get Schedule Details (OpenAPI)

Source: https://upstash.com/docs/qstash/api-refence/schedules/get-a-schedule

This snippet defines the OpenAPI specification for retrieving details of a specific schedule using its ID. It includes the request parameters, response schemas for success (200 OK) and not found (404) scenarios, and details about the Schedule and Error components.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/schedules/{scheduleId}:
    get:
      tags:
        - Schedules
      summary: Get a Schedule
      description: Get details of a specific schedule
      parameters:
        - name: scheduleId
          in: path
          required: true
          schema:
            type: string
          description: The ID of the schedule to retrieve.
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Schedule'
        '404':
          description: Schedule not found
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
components:
  schemas:
    Schedule:
      type: object
      required:
        - scheduleId
        - cron
        - destination
        - createdAt
        - method
        - isPaused
      properties:
        scheduleId:
          type: string
          description: Unique identifier for the schedule
        cron:
          type: string
          description: The cron expression used to schedule the message
        destination:
          type: string
          description: The destination URL or URL Group name
        createdAt:
          type: integer
          format: int64
          description: The creation timestamp of the schedule in unix milliseconds
        method:
          type: string
          description: The HTTP method used for the scheduled message
        header:
          type: object
          additionalProperties:
            type: array
            items:
              type: string
          description: Map of header names to arrays of header values
        body:
          type: string
          description: The body of the scheduled message
        retries:
          type: integer
          description: The number of retries for the scheduled message
        delay:
          type: integer
          description: The delay in seconds before the scheduled message is sent
        callback:
          type: string
          description: The callback URL for the scheduled message
        failureCallback:
          type: string
          description: The failure callback URL for the scheduled message
        callerIp:
          type: string
          description: The IP address of the client that created the schedule
        isPaused:
          type: boolean
          description: Whether the schedule is paused
        flowControlKey:
          type: string
          description: The flow control key used for rate limiting
        parallelism:
          type: integer
          description: The parallelism value used for flow control
        rate:
          type: integer
          description: The rate value used for flow control
        period:
          type: integer
          description: The period value used for flow control
        retryDelayExpression:
          type: string
          description: The retry delay expression used for calculating retry delays
        label:
          type: string
          description: The label assigned to the scheduled message
        lastScheduleTime:
          type: integer
          format: int64
          description: The last time the schedule was triggered in unix milliseconds
        nextScheduleTime:
          type: integer
          format: int64
          description: The next scheduled trigger time in unix milliseconds
        lastScheduleStates:
          type: object
          description: The states of the last scheduled messages
          additionalProperties:
            type: string
    Error:
      type: object
      required:
        - error
      properties:
        error:
          type: string
          description: Error message
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

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

### Create a Schedule to a URL Group

Source: https://upstash.com/docs/qstash/overall/llms-txt

This API endpoint allows you to schedule messages to be published to a URL Group using its name or ID. Examples are provided for TypeScript, Python, and cURL.

```APIDOC
## Create a Schedule to a URL Group

### Description
This code illustrates how to schedule messages to be published to a URL Group using its name or ID. The examples are provided for TypeScript, Python, and cURL, enabling flexible integration into different projects. Remember to substitute placeholders like '<QSTASH_TOKEN>' and '<URL_GROUP_ID_OR_NAME>' with your specific values.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/schedules/<URL_GROUP_ID_OR_NAME>`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - `Bearer <QSTASH_TOKEN>`
- **Upstash-Cron** (string) - Required - The cron schedule (e.g., `* * * * *`)
- **Content-type** (string) - Required - `application/json`

#### Request Body
- **(object)** - Required - The JSON message payload to be sent.

### Request Example
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

### Response
#### Success Response (200)
Responses vary based on the specific endpoint and operation.

#### Response Example
(Example depends on the specific endpoint)
```

--------------------------------

### Authentication Methods

Source: https://upstash.com/docs/qstash/api-refence/messages/enqueue-a-message

Details the available security schemes for authenticating with the QStash API.

```APIDOC
## Authentication Methods

### Description
QStash supports authentication using JWT tokens, which can be provided either as a Bearer token in the Authorization header or as a query parameter.

### Method
N/A (This describes authentication methods, not specific endpoints)

### Endpoint
N/A

### Parameters
#### Path Parameters
None

#### Query Parameters
- **stash_token** (string) - Required - QStash authentication token passed as a query parameter.

#### Request Body
None

### Request Example
#### Bearer Token Authentication
```
Authorization: Bearer <your_jwt_token>
```

#### Query Parameter Authentication
```
?stash_token=<your_jwt_token>
```

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Publish Message with Custom Headers using cURL

Source: https://upstash.com/docs/qstash/overall/llms-txt

Demonstrates publishing a JSON message with custom forwardable headers using cURL. It specifies the HTTP method, endpoint, and includes examples of request and response payloads.

```bash
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

--------------------------------

### Publish HTML Content to URL (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes raw HTML content to a specified URL. The 'content_type' must be set to 'text/html'. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish(
    url="https://my-api...",
    body="<html><body><h1>Hello World</h1></body></html>",
    content_type="text/html",
)
```

--------------------------------

### Create QStash Schedule (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Creates a new QStash schedule that runs a task at a specified cron interval. Requires a QStash client initialized with a token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule_id = client.schedule.create(
    destination="https://my-api...",
    cron="*/5 * * * *",
)

print(schedule_id)
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

### QStash Success Response Example

Source: https://upstash.com/docs/qstash/overall/llms-txt

A JSON object representing a successful response from a QStash batch operation. It contains a single field, `batchId`, which is a string identifier for the completed batch.

```json
{
  "batchId": "batch_ghi789"
}
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

### Configure URL Group Headers with QStash

Source: https://upstash.com/docs/qstash/howto/webhook

URL Groups allow defining server-side templates for publishing messages, including default headers. This example shows how to configure a URL Group to forward all incoming request headers and set a default retry count. This simplifies webhook processing by ensuring consistent header forwarding and retry policies across multiple requests to the same group.

```Shell
curl -X PATCH https://qstash.upstash.io/v2/topics/<URL_GROUP_NAME> \
    -H "Authorization: Bearer <QSTASH_TOKEN>" \
    -d '{ 
        "headers": { 
            "Upstash-Header-Forward": ["true"], 
            "Upstash-Retries": "3" 
        } 
    }'
```

--------------------------------

### List Schedules OpenAPI Specification

Source: https://upstash.com/docs/qstash/api-refence/schedules/list-schedules

This OpenAPI 3.1.0 specification describes the endpoint for listing all schedules in the QStash API. It details the request method (GET), path (/v2/schedules), and the structure of the successful response (200 OK) which returns an array of Schedule objects. It also defines the properties of a Schedule object, including its ID, cron expression, destination, and status.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/schedules:
    get:
      tags:
        - Schedules
      summary: List schedules
      description: List all schedules
      responses:
        '200':
          description: List of schedules
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Schedule'
components:
  schemas:
    Schedule:
      type: object
      required:
        - scheduleId
        - cron
        - destination
        - createdAt
        - method
        - isPaused
      properties:
        scheduleId:
          type: string
          description: Unique identifier for the schedule
        cron:
          type: string
          description: The cron expression used to schedule the message
        destination:
          type: string
          description: The destination URL or URL Group name
        createdAt:
          type: integer
          format: int64
          description: The creation timestamp of the schedule in unix milliseconds
        method:
          type: string
          description: The HTTP method used for the scheduled message
        header:
          type: object
          additionalProperties:
            type: array
            items:
              type: string
          description: Map of header names to arrays of header values
        body:
          type: string
          description: The body of the scheduled message
        retries:
          type: integer
          description: The number of retries for the scheduled message
        delay:
          type: integer
          description: The delay in seconds before the scheduled message is sent
        callback:
          type: string
          description: The callback URL for the scheduled message
        failureCallback:
          type: string
          description: The failure callback URL for the scheduled message
        callerIp:
          type: string
          description: The IP address of the client that created the schedule
        isPaused:
          type: boolean
          description: Whether the schedule is paused
        flowControlKey:
          type: string
          description: The flow control key used for rate limiting
        parallelism:
          type: integer
          description: The parallelism value used for flow control
        rate:
          type: integer
          description: The rate value used for flow control
        period:
          type: integer
          description: The period value used for flow control
        retryDelayExpression:
          type: string
          description: The retry delay expression used for calculating retry delays
        label:
          type: string
          description: The label assigned to the scheduled message
        lastScheduleTime:
          type: integer
          format: int64
          description: The last time the schedule was triggered in unix milliseconds
        nextScheduleTime:
          type: integer
          format: int64
          description: The next scheduled trigger time in unix milliseconds
        lastScheduleStates:
          type: object
          description: The states of the last scheduled messages
          additionalProperties:
            type: string
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

```

--------------------------------

### List All QStash Schedules (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Fetches a list of all QStash schedules associated with the authenticated client. This is useful for auditing or managing multiple schedules.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
all_schedules = client.schedule.list()

print(all_schedules)
```

--------------------------------

### QStash API Authentication Methods

Source: https://upstash.com/docs/qstash/overall/llms-txt

Details two methods for authenticating requests to the QStash API: using a Bearer Token in the `Authorization` header (recommended) or as a `qstash_token` query parameter. Examples are provided for both cURL.

```bash
curl https://qstash.upstash.io/v2/publish/ -H "Authorization: Bearer <QSTASH_TOKEN>"
```

```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
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

### Authenticate with Bearer Token Header (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Example of authenticating QStash API requests using a Bearer token in the Authorization header. This method is applicable for various HTTP methods.

```bash
curl https://qstash.upstash.io/v2/publish/\ldots \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

### Next.js UI to Start Background Job

Source: https://upstash.com/docs/qstash/overall/llms-txt

A React component for triggering a background job in a Next.js application. It manages loading and message states using the `useState` hook. Button clicks invoke the `startBackgroundJob` function and update the UI to display loading indicators or operation results, including message IDs.

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

### Publish JSON with Helicone Analytics in TypeScript

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publish a JSON message with Helicone analytics enabled for LLM usage monitoring. This example uses the QStash client in TypeScript and requires setting up a custom provider and passing the Helicone API key via environment variables.

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

### Expose Local Server with localtunnel.me

Source: https://upstash.com/docs/qstash/howto/local-tunnel

Use localtunnel.me to create a public URL for your local development server. This tool is simple to use and requires only the port your application is running on. It's useful for quickly testing QStash integrations.

```bash
npx localtunnel --port 3000
```

--------------------------------

### Publish JSON to URL with Delay, Headers, and Body (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes a JSON message to a specified URL with a 3-second delay, custom headers, and a JSON body. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
res = client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    headers={
        "test-header": "test-value",
    },
    delay="3s",
)

print(res.message_id)
```

--------------------------------

### Create QStash Schedule with Callbacks (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Creates a QStash schedule with specified cron interval, destination, and optional callback URLs for success and failure notifications. This allows for asynchronous handling of schedule execution outcomes.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.schedule.create(
    destination="https://my-api...",
    cron="0 * * * *",
    callback="https://my-callback...",
    failure_callback="https://my-failure-callback...",
)
```

--------------------------------

### Enqueue Chat Completion Request (JavaScript, Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Illustrates how to enqueue a chat completion request for later processing using QStash. This integrates with LLM providers and requires queue name, QStash and LLM API tokens, message body, and a callback URL. Examples are provided for both JavaScript and Python.

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

### Key Rotation Logic in Pseudocode

Source: https://upstash.com/docs/qstash/howto/roll-signing-keys

Illustrates the core logic for rotating signing keys. It shows how the 'current' key is updated to the 'next' key, and a new 'next' key is generated. This pseudocode is language-agnostic and represents the fundamental steps involved in key rolling.

```pseudocode
currentKey = nextKey
nextKey = generateNewKey()
```

--------------------------------

### Get URL Group by Name - Python

Source: https://upstash.com/docs/qstash/sdks/py/examples/url-groups

Retrieves a specific URL group by its name. Initializes a QStash client with your token. Returns a URL group object containing its name and a list of its endpoints.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
url_group = client.url_group.get("my-url-group")

print(url_group.name, url_group.endpoints)
```

--------------------------------

### GET /v2/dlq/{dlqId}

Source: https://upstash.com/docs/qstash/api-refence/dlq/get-a-dlq-message

Retrieves a specific message from the Dead Letter Queue (DLQ) using its unique DLQ ID. This is useful for inspecting messages that failed delivery and may require manual intervention or re-processing.

```APIDOC
## GET /v2/dlq/{dlqId}

### Description
Get a specific message from the DLQ.

### Method
GET

### Endpoint
/v2/dlq/{dlqId}

### Parameters
#### Path Parameters
- **dlqId** (string) - Required - The DLQ ID of the message you want to retrieve.

### Response
#### Success Response (200)
- **messageId** (string) - Unique identifier for the message
- **url** (string) - The URL to which the message should be delivered.
- **topicName** (string) - The URL Group (a.k.a. topic) name if this message was sent to a URL Group.
- **endpointName** (string) - The endpoint name of the message if the endpoint is given a name within the URL group.
- **method** (string) - The HTTP method to use for the message.
- **header** (object) - The HTTP headers sent to your API.
- **body** (string) - The body of the message if it is composed of utf8 chars only, empty otherwise.
- **bodyBase64** (string) - The base64 encoded body if the body contains a non-utf8 char only, empty otherwise.
- **maxRetries** (integer) - The number of retries that should be attempted in case of delivery failure.
- **notBefore** (integer) - The unix timestamp in milliseconds before which the message should not be delivered.
- **createdAt** (integer) - The unix timestamp in milliseconds when the message was created.
- **callback** (string) - The url where we send a callback each time the message is attempted to be delivered.
- **failureCallback** (string) - The url where we send a callback to after the message is failed
- **queueName** (string) - The name of the queue if the message is enqueued to a queue.
- **scheduleId** (string) - The scheduleId of the message if the message is triggered by a schedule
- **callerIP** (string) - IP address of the publisher of this message.
- **label** (string) - The label of the message assigned by the user.
- **flowControlKey** (string) - The flow control key used for rate limiting.
- **rate** (integer) - The rate value used for flow control.
- **period** (integer) - The period value used for flow control.
- **parallelism** (integer) - The parallelism value used for flow control.
- **responseStatus** (integer) - The HTTP status code received from the destination API.
- **responseHeader** (object) - 

#### Response Example
```json
{
  "messageId": "msg_abc123",
  "url": "https://example.com/webhook",
  "topicName": "my-topic",
  "endpointName": "default",
  "method": "POST",
  "header": {
    "Content-Type": ["application/json"]
  },
  "body": "{\"key\": \"value\"}",
  "bodyBase64": "",
  "maxRetries": 3,
  "notBefore": 1678886400000,
  "createdAt": 1678886300000,
  "callback": "https://my-callback.com/success",
  "failureCallback": "https://my-callback.com/failure",
  "queueName": "my-queue",
  "scheduleId": "sch_xyz789",
  "callerIP": "192.168.1.100",
  "label": "important-message",
  "flowControlKey": "fc_key_123",
  "rate": 100,
  "period": 60,
  "parallelism": 5,
  "responseStatus": 500,
  "responseHeader": {
    "X-Custom-Header": ["some-value"]
  }
}
```

#### Error Response (404)
- **code** (string) - Error code
- **message** (string) - Error message

#### Response Example
```json
{
  "code": "NOT_FOUND",
  "message": "Message not found in DLQ"
}
```
```

--------------------------------

### Overwrite an Existing QStash Schedule (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Updates an existing QStash schedule using its `scheduleId`. This example demonstrates how to modify a schedule's configuration or destination using the `@upstash/qstash` client library in TypeScript.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  scheduleId: "existingScheduleId",
  cron: "* * * * *",
});

```

--------------------------------

### Callback Configuration

Source: https://upstash.com/docs/qstash/api-refence/messages/enqueue-a-message

Configure callback URLs and custom headers for receiving post-delivery notifications.

```APIDOC
## Callback Configuration

### Description
This section details headers used to configure callback URLs and forward custom headers to the callback destination.

### Method
Not applicable (describes headers for various endpoints)

### Endpoint
Not applicable (describes headers for various endpoints)

### Headers
#### `Upstash-Callback` (header)
- **Type**: string
- **Description**: Specifies a callback URL to be invoked after message delivery (success or failure). The content delivered to the callback is detailed [here](/qstash/features/callbacks#how-do-i-use-callbacks). The callback URL must start with `http://` or `https://`. Callbacks are charged as regular messages and use the original request's retry settings.

#### `Upstash-Callback-Forward-*` (header)
- **Type**: string
- **Description**: Allows sending custom headers to the callback URL. Prefix the header name with `Upstash-Callback-Forward-`. The prefix will be stripped, and the header will be sent to the callback destination. Example: `Upstash-Callback-Forward-My-Header: my-value` forwards `My-Header: my-value`.

#### `Upstash-Callback-*` (header)
- **Type**: string
- **Description**: Customizes the callback message configuration. See [Configuring Callbacks](/qstash/features/callbacks#configuring-callbacks) for details. Example: `Upstash-Callback-Method` can set the HTTP method for the callback.

### Request Example
(No specific request body example as this describes headers applicable to various POST/PUT/etc. requests)

### Response
(No specific response example as this describes headers applicable to various endpoints)

```

--------------------------------

### Get DLQ Messages with Pagination (TypeScript)

Source: https://upstash.com/docs/qstash/sdks/ts/examples/dlq

Retrieves all messages from the Dead Letter Queue (DLQ) using cursor-based pagination. This is useful for handling large numbers of messages efficiently. It requires a QStash client with a valid token.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client("<QSTASH_TOKEN>");
const dlq = client.dlq;
const all_messages = [];
let cursor = null;
while (true) {
  const res = await dlq.listMessages({ cursor });
  all_messages.push(...res.messages);
  cursor = res.cursor;
  if (!cursor) {
    break;
  }
}
```

--------------------------------

### Run QStash CLI Dev Server (Bash)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Instructions for running the QStash CLI development server directly after downloading the binary. This bypasses package managers and involves executing the 'qstash dev' command from the terminal.

```bash
$ ./qstash dev
```

--------------------------------

### Configure Message Retries with Custom Backoff (Bash, TypeScript, Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Demonstrates publishing a JSON message with custom retry configurations, including the maximum number of retries and a delay expression for exponential backoff. This example showcases the usage in Bash, TypeScript, and Python, requiring a QStash token and target URL.

```bash
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>'
    -H "Content-type: application/json"
    -H "Upstash-Retries: 3"
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000"
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

### Publish Message to Endpoint (curl, TypeScript, Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Sends a JSON message to a specified URL with automatic retries. Examples are provided in cURL for command-line execution, TypeScript using the Upstash client library, and Python also using the QStash client library.

```curl
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

### Get All DLQ Messages with Pagination (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/dlq

Retrieves all messages from the Dead Letter Queue (DLQ) using cursor-based pagination. This is useful for handling large numbers of messages. It requires the 'qstash' library and a QStash token. The function iterates through pages until no cursor is returned.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

all_messages = []
cursor = None
while True:
    res = client.dlq.list(cursor=cursor)
    all_messages.extend(res.messages)
    cursor = res.cursor
    if cursor is None:
        break
```

--------------------------------

### Message Sending with Advanced Configurations

Source: https://upstash.com/docs/qstash/api-refence/schedules/create-a-schedule

This section details how to send messages using the QStash API, including advanced configurations for retry delays, message delivery delays, custom headers, and callback URLs for delivery and failure notifications.

```APIDOC
## POST /websites/upstash-qstash

### Description
Send a message to a specific endpoint with advanced delivery and callback configurations.

### Method
POST

### Endpoint
/websites/upstash-qstash

### Parameters
#### Header Parameters
- **Upstash-Retry-Delay** (string) - Optional - Customize the delay between retry attempts when message delivery fails. Supports mathematical expressions using the `retried` variable.
- **Upstash-Delay** (string) - Optional - Delay the message delivery. Format is `<value><unit>`, where unit can be `s`, `m`, `h`, or `d`.
- **Upstash-Forward-`{HeaderName}`** (string) - Optional - Send custom headers to your endpoint. Prefix the header name with `Upstash-Forward-`.
- **Upstash-Callback** (string) - Optional - Define a callback URL to be called after each attempt. The URL must be prefixed with `http://` or `https://`.
- **Upstash-Callback-Forward-`{HeaderName}`** (string) - Optional - Send custom headers along with your callback message. Prefix the header name with `Upstash-Callback-Forward-`.
- **Upstash-Callback-`{ConfigName}`** (string) - Optional - Customize callback message configuration. Supported values for `{ConfigName}` include `Method`, `Timeout`, `Retries`, and `Retry-Delay`.
- **Upstash-Failure-Callback** (string) - Optional - Define a failure callback URL to be called when a delivery fails after all retries.

### Request Example
```json
{
  "to": "https://example.com/webhook",
  "body": "This is a test message."
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the sent message.

#### Response Example
```json
{
  "messageId": "msg_abc123xyz"
}
```
```

--------------------------------

### Publish JSON Message with Custom Retries (cURL, TypeScript, Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Shows how to publish a JSON message with custom retry configurations. This allows control over how many times QStash will attempt to redeliver a message upon failure. Examples are provided for cURL, TypeScript, and Python using the respective QStash SDKs or command-line interface.

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

### Start Background Job API

Source: https://upstash.com/docs/qstash/overall/llms-txt

This Next.js API route handler receives user data and uses the Upstash QStash client to publish a JSON message, invoking a separate API endpoint for background job logic. It dynamically constructs the URL for the background job endpoint.

```APIDOC
## POST /api/start-background-job

### Description
Starts a background job by publishing a JSON message to a QStash endpoint.

### Method
POST

### Endpoint
/api/start-background-job

### Parameters
#### Request Body
- **users** (string[]) - Required - A list of user identifiers.

### Request Example
```json
{
  "users": ["user1", "user2"]
}
```

### Response
#### Success Response (200)
- **message** (string) - Indicates that the job has been started.

#### Response Example
```json
"Job started"
```
```

--------------------------------

### POST /v2/queues/

Source: https://upstash.com/docs/qstash/overall/llms-txt

Creates or updates a queue with specified configuration, including parallelism.

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

### Run QStash CLI Dev Server with Docker

Source: https://upstash.com/docs/qstash/overall/llms-txt

Sets up a local development environment for the QStash CLI using Docker. It involves pulling the latest QStash Docker image and running a container that maps port 8080 to expose the development server.

```bash
# Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

# Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev

```

--------------------------------

### GET /v2/logs API Endpoint

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves event logs for published messages, enabling tracking of delivery status, errors, and retry attempts. This API endpoint supports optional filtering parameters such as `from`, `to`, `messageId`, `limit`, and `cursor` for paginated results.

```bash
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer <QSTASH_TOKEN>"

```

--------------------------------

### Publish Message to AWS Lambda URL (curl)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a JSON message to an AWS Lambda URL using cURL. This example demonstrates sending a simple JSON payload with authorization via a bearer token and specifying the Content-Type as application/json.

```curl
curl --request POST "https://qstash.upstash.io/v2/publish/https://urzdbfn4et56vzeasu3fpcynym0zerme.lambda-url.eu-west-1.on.aws" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### Get Message Logs with Filtering in QStash

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve event logs for published messages to monitor their delivery status. This allows tracking message lifecycles and identifying potential issues. Requires a QStash token for authentication.

```APIDOC
## Get Message Logs

### Description
Retrieves event logs for published messages to monitor their delivery status. This allows tracking message lifecycles and identifying potential issues. Requires a QStash token for authentication.

### Method
GET

### Endpoint
`/v2/logs`

### Parameters
#### Request Headers
- **Authorization** (string) - Required - The authentication token in the format `Bearer <QSTASH_TOKEN>`.

### Request Example (curl)
```bash
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer <QSTASH_TOKEN>"
```

### Request Example (TypeScript)
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

### Request Example (Python)
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
logs = client.event.list()

for event in logs:
    print(f"{event['time']}: {event['state']} - Message {event['messageId']}")
    print(f"  URL: {event['url']}")
```

### Response
#### Success Response (200)
- **events** (array) - An array of log events.
  - **time** (string) - The timestamp of the event.
  - **state** (string) - The state of the message (e.g., `published`, `delivered`, `failed`).
  - **messageId** (string) - The ID of the message.
  - **url** (string) - The URL the message was sent to.
  - **responseStatus** (integer) - The HTTP status code of the response from the webhook.
```

--------------------------------

### Publish Message with Custom Retry Delay using cURL, TypeScript, and Python

Source: https://upstash.com/docs/qstash/overall/llms-txt

Illustrates how to publish a JSON message to QStash with a custom retry delay. This example shows the equivalent implementation across cURL, TypeScript, and Python, allowing users to override the default exponential backoff with specific retry logic defined by a mathematical expression.

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

### Initialize Upstash QStash Receiver with Cloudflare Secrets Store (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

This TypeScript code snippet shows how to initialize the Upstash QStash Receiver within a Cloudflare Worker. It securely retrieves signing keys from the Cloudflare Secrets Store using the `env` object, which must be configured with `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY` bindings. This setup is crucial for verifying incoming QStash messages.

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

### Pause and Resume QStash Schedule (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Demonstrates how to temporarily pause a QStash schedule from running and subsequently resume it. This allows for controlled deactivation and reactivation of scheduled tasks.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule_id = "scd_1234"

client.schedule.pause(schedule_id)

schedule = client.schedule.get(schedule_id)
print(schedule.paused) # prints True

client.schedule.resume(schedule_id)
```

--------------------------------

### POST /v2/enqueue/{queueName}/{destination}

Source: https://upstash.com/docs/qstash/api-refence/messages/enqueue-a-message

Enqueue a message to the specified queue. The queue will be created automatically if it doesn't exist.

```APIDOC
## POST /v2/enqueue/{queueName}/{destination}

### Description
Enqueue a message to the specified queue.

### Method
POST

### Endpoint
/v2/enqueue/{queueName}/{destination}

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to enqueue the message to.
- **destination** (string) - Required - The destination URL or URL Group name for the message.

#### Header Parameters
- **Content-Type** (string) - Optional - The MIME type of the message (e.g., `application/json`).
- **Upstash-Forward-*** (string) - Optional - Custom headers to forward to the destination, prefixed with `Upstash-Forward-`.
- **Upstash-Method** (string) - Optional - The HTTP method to use for the request to your API (e.g., `GET`, `POST`). Defaults to `POST`.
- **Upstash-Timeout** (string) - Optional - Maximum duration for the request before timing out (e.g., `5s`, `2m`).
- **Upstash-Retries** (integer) - Optional - Number of retries for the message.

### Request Example
```json
{
  "queueName": "my-queue",
  "destination": "https://example.com/webhook",
  "body": {
    "message": "Hello QStash!"
  }
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the enqueued message.

#### Response Example
```json
{
  "messageId": "msg_abc123xyz"
}
```
```

--------------------------------

### Overwrite an Existing QStash Schedule (cURL)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Updates an existing QStash schedule using its `scheduleId`. This example demonstrates how to modify a schedule's configuration or destination using cURL, including setting headers for authorization, content type, cron schedule, and schedule ID.

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

### Get URL Group by Name (TypeScript)

Source: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups

Retrieves a specific URL group by its name. This function requires the QSTASH_TOKEN for authentication and the name of the URL group to fetch. It returns the group's name and its associated endpoints.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
const urlGroup = await urlGroups.get("urlGroupName");
console.log(urlGroup.name, urlGroup.endpoints);
```

--------------------------------

### Start Background Job with QStash API (TypeScript)

Source: https://upstash.com/docs/qstash/overall/llms-txt

This Next.js API route handler in TypeScript uses the Upstash QStash client to publish a JSON message. This message triggers a separate API endpoint to execute background job logic. It dynamically constructs the background job endpoint URL and requires a QStash token for authentication. The input is expected to be a JSON object containing a 'users' array.

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

### Publish Message with Delay using QStash API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Schedules a message publication with a delay using QStash. The message is held by QStash for the specified duration before being sent. Requires authentication, a target URL, and a delay parameter. Examples provided for cURL, TypeScript, and Python.

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

### Set Max Retry Count for Message Publishing

Source: https://upstash.com/docs/qstash/overall/llms-txt

Configure the maximum number of retries for sending a message before it's sent to the dead-letter queue. This example shows how to set retries to 3 using cURL, TypeScript SDK, or Python SDK.

```APIDOC
## POST /v2/publish/{url}

### Description
Publish a message to a specified URL with a custom maximum retry count.

### Method
POST

### Endpoint
`/v2/publish/{url}`

### Parameters
#### Path Parameters
- **url** (string) - Required - The target URL to publish the message to.

#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Retries** (integer) - Optional - The maximum number of retries for the message.
- **Content-type** (string) - Required - Specifies the content type of the request body, usually `application/json`.

#### Request Body
- **body** (object) - Required - The JSON payload of the message.

### Request Example (cURL)
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Request Example (TypeScript)
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

### Request Example (Python)
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
```

### Response
#### Success Response (200)
- **message** (string) - Indicates the success of the operation.
```

--------------------------------

### Verify QStash Message Signature with Python SDK

Source: https://upstash.com/docs/qstash/sdks/py/examples/receiver

This snippet demonstrates how to initialize the QStash Receiver and verify the signature of an incoming message. It requires your current and next signing keys, and the request URL. The function takes the message body and signature from the request headers as input.

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

### Publish Message with Custom Header using QStash API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Demonstrates adding a custom header to a published message, allowing for the transmission of additional metadata to the target endpoint. Requires authentication, a target URL, and the specification of the custom header. Examples are provided for cURL, TypeScript, and Python.

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

### QStash Authentication

Source: https://upstash.com/docs/qstash/api-refence/dlq/get-a-dlq-message

Details on how to authenticate with the QStash API using JWT Bearer tokens or query parameters.

```APIDOC
## QStash API Authentication

### Description
QStash supports two primary authentication methods: JWT Bearer tokens and a query parameter.

### Security Schemes

#### `bearerAuth` (HTTP Bearer Token)
- **Type**: `http`
- **Scheme**: `bearer`
- **Format**: `JWT`
- **Description**: Use this scheme to pass your QStash authentication token in the `Authorization` header as a Bearer token.

#### `bearerAuthQuery` (API Key in Query Parameter)
- **Type**: `apiKey`
- **In**: `query`
- **Name**: `qstash_token`
- **Description**: Alternatively, you can pass your QStash authentication token as a query parameter named `qstash_token` in your requests.

```

--------------------------------

### Get Message Details

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieve details for a specific message using its ID with the Upstash QStash SDK for TypeScript. This function requires a QStash client initialized with a token and returns message details or logs an error if the message is not found or already delivered.

```APIDOC
## Get Message Details

### Description
Retrieve details for a specific message using its ID with the Upstash QStash SDK for TypeScript. This function requires a QStash client initialized with a token and returns message details or logs an error if the message is not found or already delivered.

### Method
GET (via SDK)

### Endpoint
Not directly exposed as a REST endpoint, accessed via SDK method `client.messages.get(messageId)`

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The unique identifier of the message to retrieve.

#### Request Body
None

### Request Example
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

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier of the message.
- **url** (string) - The destination URL of the message.
- **createdAt** (number) - Timestamp when the message was created.
- **body** (string) - The body of the message.

#### Response Example
```json
{
  "messageId": "msg_123",
  "url": "http://example.com/webhook",
  "createdAt": 1701198447054,
  "body": "{\"key\": \"value\"}"
}
```

#### Error Response
- **Error**: Logs "Message already delivered or not found" if the message does not exist or has already been delivered.
```

--------------------------------

### Create QStash Schedule to URL Group (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Creates a QStash schedule that targets a URL group instead of a specific URL. This is useful for load balancing or routing tasks to a set of defined endpoints.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.schedule.create(
    destination="my-url-group",
    cron="0 * * * *",
)
```

--------------------------------

### Retrieve Signing Keys with Python

Source: https://upstash.com/docs/qstash/sdks/py/examples/keys

This code snippet demonstrates how to retrieve your current and next signing keys using the `qstash` Python library. It requires your QStash API token for authentication. The output will display the current and the upcoming signing keys.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
signing_key = client.signing_key.get()

print(signing_key.current, signing_key.next)
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

### Build and Zip Script for AWS Lambda Deployment (Node.js)

Source: https://upstash.com/docs/qstash/overall/llms-txt

This npm script automates the build process for AWS Lambda deployments using esbuild. It bundles and minifies TypeScript code into a single JavaScript file and then creates a zip archive for deployment.

```json
{
  "scripts": {
    "build": "rm -rf ./dist; esbuild index.ts --bundle --minify --sourcemap --platform=node --target=es2020 --outfile=dist/index.js && cd dist && zip -r index.zip index.js*"
  }
}
```

--------------------------------

### Schedule Message to QStash Queue

Source: https://upstash.com/docs/qstash/overall/llms-txt

Schedules a message to be added to a specific QStash queue at a defined time using cron syntax. The target queue can be specified either via the `queueName` option in the client or by using the `Upstash-Queue-Name` header in cURL requests. Examples are provided in TypeScript and cURL.

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

### Initialize QStash Client (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes the QStash client using the Python SDK. This SDK handles retries internally. Both synchronous and asynchronous client versions are available for use.

```python
from qstash import QStash

# Python SDK handles retries internally
client = QStash("<QSTASH_TOKEN>")

# Both sync and async versions available
from qstash import AsyncQStash

async_client = AsyncQStash("<QSTASH_TOKEN>")
```

--------------------------------

### List DLQ Messages - OpenAPI Spec

Source: https://upstash.com/docs/qstash/api-refence/dlq/list-dlq-messages

Defines the GET /v2/dlq endpoint for listing messages from the Dead Letter Queue. It includes parameters for pagination, filtering by various criteria like message ID, URL, topic, schedule ID, queue name, date range, response status, caller IP, and labels. It also supports sorting and limiting the number of results.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/dlq:
    get:
      tags:
        - DLQ
      summary: List DLQ messages
      description: List and paginate through all messages currently in the DLQ
      parameters:
        - name: cursor
          in: query
          schema:
            type: string
          description: >-
            By providing a cursor you can paginate through all of the messages
            in the DLQ
        - name: messageId
          in: query
          schema:
            type: string
          description: Filter DLQ messages by message ID
        - name: url
          in: query
          schema:
            type: string
          description: Filter DLQ messages by destination URL
        - name: topicName
          in: query
          schema:
            type: string
          description: Filter DLQ messages by URL Group name
        - name: scheduleId
          in: query
          schema:
            type: string
          description: Filter DLQ messages by schedule ID
        - name: queueName
          in: query
          schema:
            type: string
          description: Filter DLQ messages by queue name
        - name: fromDate
          in: query
          schema:
            type: integer
            format: int64
          description: >-
            Filter DLQ messages by starting date, in milliseconds (Unix
            timestamp). This is inclusive.
        - name: toDate
          in: query
          schema:
            type: integer
            format: int64
          description: >-
            Filter DLQ messages by ending date, in milliseconds (Unix
            timestamp). This is inclusive.
        - name: responseStatus
          in: query
          schema:
            type: integer
          description: >-
            Filter DLQ messages by HTTP response status code of the last
            delivery attempt
        - name: callerIp
          in: query
          schema:
            type: string
          description: Filter DLQ messages by IP address of the publisher
        - name: label
          in: query
          schema:
            type: string
          description: Filter DLQ messages by the label of the message assigned by the user
        - name: count
          in: query
          schema:
            type: integer
            default: 100
            maximum: 100
          description: The number of messages to return.
        - name: order
          in: query
          schema:
            type: string
            enum:
              - latestFirst
              - earliestFirst
            default: latestFirst
          description: The sorting order of DLQ messages by timestamp.
      responses:
        '200': 
          description: List of DLQ messages
          content:
            application/json:
              schema:
                type: object
                properties:
                  cursor:
                    type: string
                    description: >
                      A cursor which you can use in subsequent requests to
                      paginate through all messages. 

                      If no cursor is returned, you have reached the end of the
                      messages.
                  messages:
                    type: array
                    items:
                      $ref: '#/components/schemas/DLQMessage'
components:
  schemas:
    DLQMessage:
      type: object
      properties:
        messageId:
          type: string
          description: Unique identifier for the message
        url:
          type: string
          description: The URL to which the message should be delivered.
        topicName:
          type: string
          description: >-
            The URL Group (a.k.a. topic) name if this message was sent to a URL
            Group.
        endpointName:
          type: string
          description: >-
            The endpoint name of the message if the endpoint is given a name
            within the URL group.
        method:
          type: string
          description: The HTTP method to use for the message.
        header:
          type: object

```

--------------------------------

### List URL Groups OpenAPI Specification

Source: https://upstash.com/docs/qstash/api-refence/url-groups/list-url-groups

This OpenAPI 3.1.0 specification defines the GET /v2/topics endpoint for listing URL Groups. It outlines the request method, tags, summary, and detailed response schema, including URLGroup and Endpoint object structures. Authentication is handled via bearer token.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/topics:
    get:
      tags:
        - URL Groups
      summary: List URL Groups
      description: List all your URL Groups
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/URLGroup'
components:
  schemas:
    URLGroup:
      type: object
      properties:
        name:
          type: string
          description: URL Group name
        createdAt:
          type: integer
          description: Creation timestamp of URL Group in Unix milliseconds
        updatedAt:
          type: integer
          description: Last update timestamp of URL Group in Unix milliseconds
        endpoints:
          type: array
          items:
            $ref: '#/components/schemas/Endpoint'
    Endpoint:
      type: object
      properties:
        name:
          type: string
          description: The name of the endpoint
        url:
          type: string
          description: The URL of the endpoint
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

```

--------------------------------

### Publish Message with Relative Delay (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

This Python code snippet demonstrates how to publish a JSON message to QStash with a relative delay specified as '60s' using the `delay` parameter in the QStash client. It requires the 'qstash' Python library and a valid QStash token. The example shows publishing a simple JSON body with custom headers.

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

### Create QStash Schedule with Timeout (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/schedules

Creates a QStash schedule with a specified timeout duration for the destination URL. This helps prevent tasks from running indefinitely if the destination is unresponsive.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule_id = client.schedule.create(
    destination="https://my-api...",
    cron="*/5 * * * *",
    timeout="30s",
)

print(schedule_id)
```

--------------------------------

### Dead Letter Queue (DLQ) Operations

Source: https://upstash.com/docs/qstash/overall/llms-txt

The Dead Letter Queue (DLQ) stores messages that failed to be published. You can retrieve messages from the DLQ to investigate failures or retry publishing. Related endpoints include getting, deleting messages from the DLQ, and publishing messages to retry them.

```APIDOC
## Dead Letter Queue (DLQ)

### Description
The Dead Letter Queue stores messages that failed to be published. You can retrieve messages from the DLQ to investigate failures or retry publishing.

### Related Endpoints
- **Get Message from DLQ**: /qstash/api/dlq/getMessage
- **Delete Message from DLQ**: /qstash/api/dlq/deleteMessage
- **Publish Message**: /qstash/api/publish (to retry a message from DLQ)
```

--------------------------------

### List Flow Control Keys (OpenAPI)

Source: https://upstash.com/docs/qstash/api-refence/flow-control/list-flow-control-keys

This OpenAPI specification defines the GET /v2/flowControl endpoint for the QStash REST API. It allows users to retrieve a list of all Flow Control keys, including their waitlist sizes. The endpoint requires authentication via JWT bearer token or a query parameter.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/flowControl:
    get:
      tags:
        - Flow Control
      summary: List Flow Control Keys
      description: List all Flow Control keys
      responses:
        '200':
          description: Flow control keys retrieved successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/FlowControlKey'
components:
  schemas:
    FlowControlKey:
      type: object
      properties:
        flowControlKey:
          type: string
          description: The flow control key name
        waitlistSize:
          type: integer
          description: The number of messages waiting due to flow control configuration.
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

```

--------------------------------

### Get Message Details with Upstash QStash (TypeScript)

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

### Get Specific DLQ Message (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/dlq

Fetches a single message from the Dead Letter Queue (DLQ) using its unique DLQ ID. This operation requires the 'qstash' library and a valid QStash token. The function takes the DLQ ID as input and returns the corresponding message object.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
msg = client.dlq.get("<dlq-id>")
```

--------------------------------

### Publish Message to URL Group using QStash API

Source: https://upstash.com/docs/qstash/overall/llms-txt

Publishes a JSON message to a URL group for fan-out distribution. The message is sent to all registered endpoints within the specified group. Requires authentication and the URL group name. Examples are provided for cURL, TypeScript, and Python.

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

### Initialize QStash Client (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initializes the QStash client using the Python SDK, which handles retries internally. Both synchronous and asynchronous client versions are available.

```APIDOC
## Initialize QStash Client (Python)

### Description
Initializes the QStash client using the Python SDK. The Python SDK handles retries internally, abstracting this complexity from the developer. Both synchronous and asynchronous client versions are available.

### Code
```python
from qstash import QStash

# Python SDK handles retries internally
client = QStash("<QSTASH_TOKEN>")

# Both sync and async versions available
from qstash import AsyncQStash

async_client = AsyncQStash("<QSTASH_TOKEN>")
```
```

--------------------------------

### Create or Update Queue

Source: https://upstash.com/docs/qstash/sdks/ts/examples/queues

Allows you to create a new queue or update an existing one. You can specify the desired parallelism for the queue.

```APIDOC
## Create or Update Queue

### Description
Creates a new queue or updates an existing one with specified parallelism.

### Method
POST (implicitly via client method)

### Endpoint
`/queue/{queueName}/upsert` (conceptual endpoint)

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to create or update.

#### Query Parameters
None

#### Request Body
- **parallelism** (integer) - Required - The desired parallelism level for the queue.

### Request Example
```typescript
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName }).upsert({ parallelism: 2 });
```

### Response
#### Success Response (200)
- **queueDetails** (object) - Details of the created or updated queue.

#### Response Example
```json
{
  "queueName": "upstash-queue",
  "parallelism": 2,
  "createdAt": "2023-01-01T12:00:00Z",
  "updatedAt": "2023-01-01T12:05:00Z"
}
```
```

--------------------------------

### Get Message Logs with Filtering in QStash (Bash, TypeScript, Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Retrieves event logs for published messages to monitor delivery status and identify potential issues. Requires a QStash token for authentication. Supports filtering and provides details like time, state, message ID, URL, and response status.

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

### Trigger Workflow Execution with Upstash Workflow Client (Python)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Initiates a workflow execution using the Upstash Workflow client in Python. This function requires the workflow URL, a request body, and can optionally accept a custom workflow run ID and retry count. It returns the ID of the newly started workflow run.

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

### Pause/Resume Queue - TypeScript

Source: https://upstash.com/docs/qstash/sdks/ts/examples/queues

Demonstrates how to pause and resume a queue using the Upstash QStash client. It involves creating a queue with a specific parallelism, pausing it, checking its status, and then resuming it. Requires QSTASH_TOKEN.

```typescript
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const name = "upstash-pause-resume-queue";
const queue = client.queue({ queueName: name });
await queue.upsert({ parallelism: 1 });

// pause queue
await queue.pause();

const queueInfo = await queue.get();
console.log(queueInfo.paused); // prints true

// resume queue
await queue.resume();
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

### Configure QStash Retry Delay

Source: https://upstash.com/docs/qstash/overall/llms-txt

Customize the delay between message delivery retries using mathematical expressions with QStash. This supports advanced strategies like exponential backoff. The examples show how to set the number of retries and the retry delay expression using cURL, TypeScript, and Python. The default retry strategy is exponential backoff.

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

### QStash Batch Operations API (JSON)

Source: https://upstash.com/docs/qstash/overall/llms-txt

Defines the structure for using the QStash Batch Operations API to send multiple messages efficiently. This allows publishing to various destinations or enqueuing messages to different queues within a single API request, reducing network overhead. Examples show publishing to distinct URLs and to named queues.

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

--------------------------------

### Pause and Resume a Queue (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/queues

This snippet demonstrates how to pause and resume a queue using the QStash Python client. It first sets parallelism to 1, then pauses the queue, verifies its paused state, and finally resumes it. Be aware that these operations can take up to a minute.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=1)

client.queue.pause(queue_name)

queue = client.queue.get(queue_name)
print(queue.paused) # prints True

client.queue.resume(queue_name)
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

### Create a basic schedule in TypeScript

Source: https://upstash.com/docs/qstash/sdks/ts/examples/schedules

Creates a new schedule that runs a specified destination URL at a defined cron interval. Requires a QStash token and a valid cron expression.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://my-api...",
  cron: "*/5 * * * *",
});
```

--------------------------------

### Expose Local Server with localtunnel.me

Source: https://upstash.com/docs/qstash/overall/llms-txt

A command-line utility to create a public URL for a local development server. This is useful for testing integrations like QStash without deploying publicly.

```bash
npx localtunnel --port 3000
```

--------------------------------

### Golang QStash Webhook Handler and Verification

Source: https://upstash.com/docs/qstash/overall/llms-txt

Sets up an HTTP server in Golang to listen for QStash webhooks. It verifies the request signature using provided signing keys and handles potential errors. Dependencies include standard Go libraries for HTTP and I/O. The function takes the request body, signature, and signing keys as input.

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

### Create a schedule with callbacks in TypeScript

Source: https://upstash.com/docs/qstash/sdks/ts/examples/schedules

Creates a schedule that includes optional callback URLs for success and failure notifications. This allows for tracking the execution status of scheduled tasks.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://my-api...",
  cron: "0 * * * *",
  callback: "https://my-callback...",
  failureCallback: "https://my-failure-callback...",
});
```

--------------------------------

### Publish JSON to URL Group with Delay, Headers, and Body (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes a JSON message to a URL group with a 3-second delay, custom headers, and a JSON body. The response is an array of message IDs, one for each URL in the group. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
res = client.message.publish_json(
    url_group="my-url-group",
    body={
        "hello": "world",
    },
    headers={
        "test-header": "test-value",
    },
    delay="3s",
)

# When publishing to a URL group, the response is an array of messages for each URL in the group
print(res[0].message_id)
```

--------------------------------

### Resume Schedule OpenAPI Definition

Source: https://upstash.com/docs/qstash/api-refence/schedules/resume-a-schedule

Defines the OpenAPI 3.1.0 specification for resuming a QStash schedule. It details the POST request to the /v2/schedules/{scheduleId}/resume endpoint, including parameters, responses, and security schemes.

```yaml
openapi: 3.1.0
info:
  title: QStash REST API
  description: |
    QStash is a message queue and scheduler built on top of Upstash Redis.
  version: 2.0.0
  contact:
    name: Upstash
    url: https://upstash.com
servers:
  - url: https://qstash.upstash.io
security:
  - bearerAuth: []
  - bearerAuthQuery: []
tags:
  - name: Messages
    description: Publish and manage messages
  - name: Queues
    description: Manage message queues
  - name: Schedules
    description: Create and manage scheduled messages
  - name: URL Groups
    description: Manage URL groups and endpoints
  - name: DLQ
    description: Dead Letter Queue operations
  - name: Logs
    description: Log operations
  - name: Signing Keys
    description: Manage signing keys
  - name: Flow Control
    description: Monitor flow control keys
paths:
  /v2/schedules/{scheduleId}/resume:
    post:
      tags:
        - Schedules
      summary: Resume a Schedule
      description: Resume a paused Schedule
      parameters:
        - name: scheduleId
          in: path
          required: true
          schema:
            type: string
          description: The ID of the schedule to resume.
      responses:
        '200':
          description: Schedule resumed successfully
components:
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: QStash authentication token
    bearerAuthQuery:
      type: apiKey
      in: query
      name: qstash_token
      description: QStash authentication token passed as a query parameter

```

--------------------------------

### Publish JSON with Configured Retries (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes a JSON message to a URL and configures the number of retries. The maximum number of retries is dependent on the QStash plan. Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    retries=1,
)
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

### Next.js Client-Side Button to Trigger Server Action

Source: https://upstash.com/docs/qstash/overall/llms-txt

This client-side TypeScript code integrates with Next.js server actions. It defines a React component with a button that, when clicked, triggers the `startBackgroundJob` server action. Dependencies include React and Next.js server actions. The `handleClick` function is asynchronous and awaits the server action.

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

### POST /websites/upstash-qstash

Source: https://upstash.com/docs/qstash/api-refence/schedules/create-a-schedule

This endpoint allows you to create a new message schedule. You can specify a failure callback URL and custom headers for the callback. The request body can be plain text, JSON, or binary data.

```APIDOC
## POST /websites/upstash-qstash

### Description
Creates a new message schedule with optional failure callback configurations and custom headers.

### Method
POST

### Endpoint
/websites/upstash-qstash

### Parameters
#### Header Parameters
- **Upstash-Failure-Callback-Url** (string) - Required - The URL to send failure notifications to. Must be prefixed with http:// or https://.
- **Upstash-Failure-Callback-Forward-*** (string) - Optional - Custom headers to forward with the failure callback. Prefix with `Upstash-Failure-Callback-Forward-`.
- **Upstash-Failure-Callback-Method** (string) - Optional - HTTP method for the callback request. Defaults to POST.
- **Upstash-Failure-Callback-Timeout** (string) - Optional - Timeout for the callback request.
- **Upstash-Failure-Callback-Retries** (integer) - Optional - Number of retries for the callback request. Defaults to original message retries.
- **Upstash-Failure-Callback-Retry-Delay** (string) - Optional - Retry delay for the callback request.

#### Request Body
- **(string, object, binary)** - Required - The message content. Can be `text/plain`, `application/json`, or `application/octet-stream`.

### Request Example
```json
{
  "message": "This is a scheduled message.",
  "callback": "https://your-callback-url.com/failure"
}
```

### Response
#### Success Response (200)
- **scheduleId** (string) - Unique identifier for the schedule.

#### Response Example
```json
{
  "scheduleId": "your-generated-schedule-id"
}
```

#### Error Responses
- **400** - Invalid Schedule ID format.
- **412** - Maximum number of schedules exceeded.
```

--------------------------------

### Publish JSON with Timeout (Python)

Source: https://upstash.com/docs/qstash/sdks/py/examples/publish

Publishes a JSON message to a URL and sets a timeout value for the request. The timeout value is specified as a string (e.g., '30s'). Requires the 'qstash' library and a QStash token.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    timeout="30s",
)
```
```

