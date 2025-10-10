```
================
CODE SNIPPETS
================
### QStash Local Development Setup

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This section provides instructions on how to pull and run the QStash CLI Docker image for local development. It includes commands to download the latest image and start a container, mapping the development server port.

```APIDOC
## Docker Commands for QStash Local Development

### Description
Commands to pull the QStash CLI Docker image from AWS ECR and run it, exposing the development server on a local port.

### Method
N/A (Shell Commands)

### Endpoint
N/A

### Parameters
None

### Request Example
```shell
# Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

# Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev
```

### Response
N/A
```

--------------------------------

### Start Next.js Development Server

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Runs the Next.js development server, allowing you to view and test your QStash integration locally.

```bash
npm run dev
```

--------------------------------

### Launch Fly.io Application

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Uses the `flyctl launch` command to initialize a new Fly.io application. This command interactively prompts for application details like name and region, and generates a `fly.toml` configuration file. It also offers options for database setup and immediate deployment.

```bash
flyctl launch
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

### List QStash Queues via API

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to make authenticated GET requests to the QStash API to retrieve a list of all queues. Examples include cURL, JavaScript, Python, and Go, illustrating the common pattern of using an Authorization header.

```sh
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"
```

```js
const response = await fetch("https://qstash.upstash.io/v2/queues", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/queues',
  headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/queues", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
deffer resp.Body.Close()
```

--------------------------------

### Install Vercel CLI (Bash)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Installs the Vercel Command Line Interface globally using npm. This tool is used for deploying applications to Vercel.

```bash
npm install -g vercel
```

--------------------------------

### Install QStash Package for Next.js

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Installs the `@upstash/qstash` npm package into the Next.js project, enabling QStash integration.

```bash
npm install @upstash/qstash
```

--------------------------------

### Retrieve All URL Groups Request Examples

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to make a GET request to the /v2/topics endpoint to retrieve all URL Groups. Requires a Bearer token for authorization. Examples are provided for cURL, Node.js, Python, and Go.

```sh
curl https://qstash.upstash.io/v2/topics \
  -H "Authorization: Bearer <token>"
```

```Node.js
const response = await fetch("https://qstash.upstash.io/v2/topics", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

```Python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/topics',
  headers=headers
)
```

```Go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/topics", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defersp.Body.Close()
```

--------------------------------

### Example QStash Development Environment Variables

Source: https://upstash.com/docs/qstash/qstash/howto/local-development

Provides example environment variables required to connect to the local QStash development server. These include the URL, token, and signing keys.

```dotenv
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7kYjw48mhY7kAjqNGcy6cr29RJ6r
QSTASH_NEXT_SIGNING_KEY=sig_5ZB6DVzB1wjE8S6rZ7eenA8Pdnhs
```

--------------------------------

### Create Directory and Install Dependency (Bash)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

Commands to create a new directory for the Python application and install the necessary Upstash Redis client library.

```bash
mkdir clean-db-cron
```

```bash
cd clean-db-cron
```

```bash
pip install upstash-redis
```

--------------------------------

### Basic UI for Starting Background Job (Next.js Page)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

A simple Next.js page component with a button that triggers a background job when clicked. It uses client-side JavaScript for the click handler.

```typescript
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

### Deploy Application using Vercel CLI (Bash)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Initiates the deployment process for an application using the Vercel CLI. This command guides the user through the deployment steps.

```bash
vercel
```

--------------------------------

### Example JSON Response for Get Schedule

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Provides an example of the JSON structure returned by the QStash API upon successfully retrieving schedule details. It includes fields like schedule ID, creation timestamp, cron expression, destination URL, HTTP method, headers, body, and retry count.

```json
{
  "scheduleId": "scd_1234",
  "createdAt": 1623345678001,
  "cron": "0 0 1 * *",
  "destination": "https://example.com",
  "method": "POST",
  "header": {
    "Content-Type": ["application/json"]
  },
  "body": "{\"message\":\"hello\"}",
  "retries": 3
}
```

--------------------------------

### TypeScript/Python: List All QStash Schedules

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Lists all QStash schedules using dedicated SDKs. The TypeScript example uses the @upstash/qstash client, while the Python example uses the qstash library. Both require an authentication token and demonstrate a simple API call to retrieve schedule information.

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

### Next.js Client Component to Start Background Job with QStash

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

This Next.js client component uses the 'use client' directive and interacts with a server action to start a background job via QStash. It manages loading states and displays messages to the user indicating the job's status. Dependencies include React and the startBackgroundJob function from '@/app/actions'.

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

### Retrieve All URL Groups

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Examples demonstrating how to make a GET request to the /v2/topics endpoint to retrieve all URL Groups. Requires a Bearer token for authorization.

```APIDOC
## GET /v2/topics

### Description
Retrieves all URL Groups configured in QStash.

### Method
GET

### Endpoint
/v2/topics

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example
```bash
curl https://qstash.upstash.io/v2/topics \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch("https://qstash.upstash.io/v2/topics", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/topics',
  headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/topics", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```
```

--------------------------------

### Retrieve QStash Signing Keys Request Examples

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Illustrates how to make a request to the QStash API to retrieve signing keys. Examples are provided for cURL, Node.js (JavaScript), Python, and Go, all requiring a Bearer token for authorization.

```curl
curl https://qstash.upstash.io/v2/keys \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch('https://qstash.upstash.io/v2/keys', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/keys',
   headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/keys", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defersp.Body.Close()
```

--------------------------------

### Deploy Python Application (Bash)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

Commands to install the Vercel CLI globally and then initiate the deployment process for the Python application.

```bash
npm install -g vercel
```

```bash
vercel
```

--------------------------------

### Start localtunnel.me Tunnel

Source: https://upstash.com/docs/qstash/qstash/howto/local-tunnel

Starts a localtunnel.me tunnel to expose your local development server running on a specified port to the public internet. Replace '3000' with your application's port.

```bash
npx localtunnel --port 3000
```

--------------------------------

### GET /v2/queues

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This endpoint retrieves a list of all queues. It requires an authorization token in the header.

```APIDOC
## GET /v2/queues

### Description
Retrieves a list of all QStash queues.

### Method
GET

### Endpoint
https://qstash.upstash.io/v2/queues

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```sh
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch("https://qstash.upstash.io/v2/queues", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/queues',
  headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/queues", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

### Response
#### Success Response (200)
Details of the response are not provided in the source text.

#### Response Example
None provided.
```

--------------------------------

### Upstash Workflow Trigger Example

Source: https://upstash.com/docs/qstash/qstash/workflow

Demonstrates how to trigger an Upstash Workflow using the Upstash Workflow SDK. It shows the client initialization and the `trigger` method with optional parameters like body, headers, workflow run ID, and retries.

```typescript
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

--------------------------------

### Install Upstash Dependencies

Source: https://upstash.com/docs/qstash/qstash/recipes/periodic-data-updates

Installs the necessary Upstash client libraries for QStash and Redis. These libraries enable communication with Upstash services.

```bash
npm install @upstash/qstash @upstash/redis
```

--------------------------------

### Create Next.js App for QStash Background Jobs

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Initializes a new Next.js project using `create-next-app` to demonstrate QStash background job capabilities.

```bash
npx create-next-app@latest qstash-bg-job
```

--------------------------------

### Publish JSON Message with Custom Headers via QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Shows how to publish a JSON message to a specified URL using QStash, including forwarding custom HTTP headers. The example demonstrates setting 'Upstash-Forward-My-Header' to pass custom data to the destination API. Examples provided for shell, TypeScript, and Python.

```shell
curl -XPOST \ 
    -H 'Authorization: Bearer XXX' \ 
    -H 'Upstash-Forward-My-Header: my-value' \ 
    -H "Content-type: application/json" \ 
    -d '{ "hello": "world" }' \ 
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://example.com",
  body: { "hello": "world" },
  headers: { "my-header": "my-value" }
});
```

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world"
    },
    headers={
        "my-header": "my-value"
    }
)
```

--------------------------------

### Start ngrok HTTP Tunnel

Source: https://upstash.com/docs/qstash/qstash/howto/local-tunnel

Starts an ngrok tunnel to forward HTTP traffic from a public URL to your local development server running on the specified port. Replace '3000' with your application's port.

```bash
$ ngrok http 3000
```

--------------------------------

### Server Action to Start Background Job with QStash

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Defines a Next.js server action that uses the QStash client to publish a JSON message. This action is intended to be called from the client-side to initiate a background task.

```typescript
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

### Create Cloudflare Application with C3

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Uses the `create-cloudflare-cli` (C3) tool to scaffold a new Cloudflare Worker project. It guides the user through project creation, including directory, application type (Hello World Worker), TypeScript usage, compatibility date, and Git integration. Wrangler is installed by default for testing and deployment.

```shell
npm create cloudflare@latest

```

```shell
➜  npm create cloudflare@latest
Need to install the following packages:
  create-cloudflare@2.1.0
Ok to proceed? (y) y

using create-cloudflare version 2.1.0

╭ Create an application with Cloudflare Step 1 of 3
│
├ In which directory do you want to create your application?
│ dir ./cloudflare_starter
│
├ What type of application do you want to create?
│ type "Hello World" Worker
│
├ Do you want to use TypeScript?
│ yes typescript
│
├ Copying files from "hello-world" template
│
├ Do you want to use TypeScript?
│ yes typescript
│
├ Retrieving current workerd compatibility date
│ compatibility date 2023-08-07
│
├ Do you want to use git for version control?
│ yes git
│
╰ Application created

```

--------------------------------

### Start Background Job with Error Handling (TypeScript/Next.js)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Enhances the `startBackgroundJob` function with a try-catch block for robust error handling. It logs any errors during the QStash publish operation and returns the message ID or null.

```typescript
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
    return response.messageId;
  } catch (error) {
    console.error(error);
    return null;
  }
}
```

--------------------------------

### Integrate Anthropic with QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This example demonstrates how to send messages to Anthropic's models via QStash, specifying the model, messages, and a callback URL.

```APIDOC
## POST /queue/enqueueJSON

### Description
Enqueues a JSON message to a QStash queue, with specific API integration details.

### Method
POST

### Endpoint
/queue/enqueueJSON

### Parameters
#### Request Body
- **api** (object) - Required - API details for the integration.
  - **name** (string) - Required - The name of the API (e.g., "llm").
  - **provider** (object) - Required - The provider specific configuration (e.g., Anthropic).
    - **token** (string) - Required - The API token for the provider.
- **body** (object) - Required - The payload for the API call.
- **callback** (string) - Optional - The URL to send the callback notification to.
```

--------------------------------

### Deploy Go Application to Fly.io

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

A simple bash command to deploy a Go application to Fly.io. This command is typically used after configuring the application and setting up necessary secrets.

```bash
flyctl deploy
```

--------------------------------

### Fly.io: Launching a new application

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

Demonstrates the use of the `flyctl` CLI to launch a new application on fly.io. This command initializes the application, detects the Go build configuration, prompts for app name and region, and generates a `fly.toml` configuration file. It also includes options to skip database setup and immediate deployment.

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

### Start QStash CLI Development Server with NPX

Source: https://upstash.com/docs/qstash/qstash/howto/local-development

Initiates the QStash development server locally using the NPX package manager. You can also specify a custom port.

```bash
npx @upstash/qstash-cli dev

# Start on a different port
npx @upstash/qstash-cli dev -port=8081
```

--------------------------------

### Publish Message to QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Example cURL command to send a JSON payload to a QStash endpoint, including necessary authentication and content type headers for publishing a message.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a specified QStash endpoint.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - Set to `application/json`.

#### Request Body
- **body** (object) - Required - The JSON payload to send in the message.

### Request Example
```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://cloudflare-workers.upstash.workers.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```
```

--------------------------------

### Start Background Job with QStash (TypeScript/Next.js)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

An asynchronous server action that publishes a JSON message to QStash. It uses the Upstash QStash client to send data to a specified public URL, initiating a background job. Requires QSTASH_TOKEN environment variable.

```typescript
"use server"
import { Client } from "@upstash/qstash"

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!,
})

export async function startBackgroundJob() {
  await qstashClient.publishJSON({
    // Replace with your public URL
    url: "https://qstash-bg-job.vercel.app/api/long-task",
    body: {
      hello: "world",
    },
  })
}
```

--------------------------------

### Rotate QStash Signing Keys via API

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Shows how to make an authenticated API request to rotate QStash signing keys. Examples are provided for cURL, JavaScript, Python, and Go, demonstrating different methods for making the HTTP request.

```sh
curl https://qstash.upstash.io/v2/keys/rotate \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch('https://qstash.upstash.io/v2/keys/rotate', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}
response = requests.get(
  'https://qstash.upstash.io/v2/keys/rotate', 
  headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/keys/rotate", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
deffer resp.Body.Close()
```

--------------------------------

### Go: HTTP Server for QStash Webhook

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Sets up an HTTP server in Go to listen for incoming QStash webhooks. It handles request routing, signature verification using environment variables for signing keys, and basic error handling. Requires the net/http, os, io, and fmt packages.

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

### Next.js Workflow: Customer Onboarding

Source: https://upstash.com/docs/qstash/qstash/workflow

Implements a customer onboarding workflow in Next.js using Upstash Workflow. It sends a welcome email, waits 3 days, generates a personalized follow-up message via OpenAI, and sends the follow-up email. Requires `@upstash/workflow/nextjs`.

```typescript
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
    },
  );

  const personalizedMessage = aiResponse.choices[0].message.content;

  // Step 4: Send personalized follow-up email
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, personalizedMessage);
  });
});

```

--------------------------------

### Publish a message to a URL Group

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This example illustrates how to publish a message to a predefined URL Group. URL Groups enable a fan-out pattern, delivering the same message to multiple endpoints simultaneously.

```APIDOC
## POST /v2/publish/{urlGroup}

### Description
Publishes a JSON message to a specified URL Group for fan-out delivery.

### Method
POST

### Endpoint
/v2/publish/{urlGroup}

### Parameters
#### Path Parameters
- **urlGroup** (string) - Required - The name of the URL Group to which the message will be published.

#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type of the payload, typically `application/json`.

#### Request Body
- **(JSON Object)** - Required - The JSON payload of the message to be published.

### Request Example
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
```
```

--------------------------------

### Publish Message to URL Group for Fan-out

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Illustrates publishing a message to a URL Group for fan-out delivery. This allows a single message to be sent to multiple endpoints defined within the group. Examples are provided for shell, TypeScript, and Python.

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
```

--------------------------------

### Publish a message to a specific endpoint

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This example demonstrates how to publish a simple message to a designated HTTP endpoint. It shows the basic structure for sending a JSON payload to a URL via QStash.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a JSON message to a specified URL.

### Method
POST

### Endpoint
/v2/publish/{url}

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to which the message will be published.

#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type of the payload, typically `application/json`.

#### Request Body
- **(JSON Object)** - Required - The JSON payload of the message to be published.

### Request Example
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
```

--------------------------------

### Configure Parallelism for a QStash Queue

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to set the parallelism level for a QStash queue, controlling concurrent message processing. This helps prevent overwhelming target endpoints. Examples are provided for cURL, TypeScript, and Python.

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

### Create an Upstash QStash Queue with Parallelism

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to create or update an Upstash QStash queue using the `@upstash/qstash` client, setting its parallelism to 2. It also shows how to retrieve the queue details after creation to verify the settings.

```APIDOC
## POST /queue/{queueName}/upsert

### Description
Creates or updates a QStash queue with the specified configuration, including parallelism.

### Method
POST

### Endpoint
/queue/{queueName}/upsert

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to create or update.

#### Request Body
- **parallelism** (integer) - Required - The desired level of parallelism for the queue.
```

```APIDOC
## GET /queue/{queueName}/get

### Description
Retrieves the details of a specific QStash queue.

### Method
GET

### Endpoint
/queue/{queueName}/get

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue whose details are to be retrieved.
```

--------------------------------

### Retrieve QStash Signing Keys

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Illustrates how to make a request to the QStash API to retrieve signing keys using cURL, Node.js (JavaScript), Python, and Go.

```APIDOC
## GET /v2/keys

### Description
Retrieves the signing keys used by QStash for message verification.

### Method
GET

### Endpoint
/v2/keys

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example
```bash
curl https://qstash.upstash.io/v2/keys \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch('https://qstash.upstash.io/v2/keys', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/keys',
   headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/keys", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```
```

--------------------------------

### Trigger Pipedream Workflow from QStash Topic Message

Source: https://upstash.com/docs/qstash/qstash/integrations/pipedream

This guide explains how to set up a Pipedream workflow that is triggered by new messages on a QStash topic. It involves configuring the QStash trigger in Pipedream, connecting your QStash account, selecting a topic, and testing the setup. Additional steps can be added using Pipedream's components or custom code.

```Pipedream
steps.trigger.event
```

--------------------------------

### Pause and Resume QStash Schedule using Python SDK

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Shows how to pause, get the status of, and resume a QStash schedule programmatically using its ID with the Python SDK. It verifies the schedule's paused status after the pause operation.

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

### Cloudflare Worker Local Testing and Deployment

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Commands to test a Cloudflare Worker locally using `wrangler dev` and deploy it to the Cloudflare environment using `wrangler deploy`.

```APIDOC
## Cloudflare Worker Local Testing and Deployment

### Description
Commands to test a Cloudflare Worker locally using `wrangler dev` and deploy it to the Cloudflare environment using `wrangler deploy`.

### Method
Not Applicable (CLI Commands)

### Endpoint
Not Applicable (CLI Commands)

### Parameters
None

### Request Example
```bash
npx wrangler dev
npx wrangler deploy
```

### Response
Not Applicable (CLI Commands)
```

--------------------------------

### API Response Example

Source: https://upstash.com/docs/qstash/qstash/api/publish

Illustrates the typical JSON response format received after a successful message publication via the Upstash QStash API, containing the message ID and the target URL.

```json
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```

--------------------------------

### Retry-After Header Examples

Source: https://upstash.com/docs/qstash/qstash/features/retry

Provides examples of using the `Retry-After` header to specify when QStash should retry a message. This can be a duration in seconds, a specific date/time, or a duration string.

```HTTP Headers
Retry-After: 0                             // Next retry will be scheduled immediately without any delay.
Retry-After: 10                            // Next retry will be scheduled after a 10-second delay.
Retry-After: 6m5s                          // Next retry will be scheduled after 6 minutes 5 seconds delay.
Retry-After: Sun, 27 Jun 2024 12:16:24 GMT // Next retry will be scheduled for the specified date, within the allowable limits.
```

--------------------------------

### List All QStash Schedules

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Retrieves a list of all schedules associated with your QStash account.

```APIDOC
## GET /v2/schedules

### Description
Lists all schedules configured in QStash.

### Method
GET

### Endpoint
`/v2/schedules`

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.

### Request Example
```shell
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'
```

### Response
#### Success Response (200)
- **schedules** (array) - An array of schedule objects.
  - **id** (string) - The unique identifier for the schedule.
  - **cron** (string) - The cron expression defining the schedule's timing.
  - **content** (object) - The content of the message to be sent.
  - **destination** (string) - The URL endpoint for the scheduled message.

### Client Library Examples
**TypeScript:**
```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const allSchedules = await client.schedules.list();
```

**Python:**
```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.list()
```
```

--------------------------------

### Navigate to QStash Background Job Project

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Changes the current directory to the newly created Next.js project for QStash background jobs.

```bash
cd qstash-bg-job
```

--------------------------------

### Publish Message to Specific Endpoint

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates publishing a simple message with a JSON payload to a designated HTTP endpoint using QStash. This example shows the basic structure for sending data to a single URL.

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

### GET /v2/schedules/{scheduleId}

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Retrieves a specific schedule by its ID. The response includes details such as cron expression, destination, and retry configuration.

```APIDOC
## GET /v2/schedules/{scheduleId}

### Description
Retrieves a specific schedule by its ID.

### Method
GET

### Endpoint
/v2/schedules/{scheduleId}

### Parameters
#### Path Parameters
- **scheduleId** (string) - Required - The ID of the schedule to retrieve.

#### Query Parameters
None

#### Request Body
None

### Request Example
No request examples provided, only a success response example.

### Response
#### Success Response (200)
- **scheduleId** (string) - The ID of the schedule.
- **createdAt** (integer) - Timestamp when the schedule was created.
- **cron** (string) - The cron expression for the schedule.
- **destination** (string) - The URL the schedule will send requests to.
- **method** (string) - The HTTP method for the request.
- **header** (object) - Headers to include in the request.
- **body** (string) - The request body.
- **retries** (integer) - The number of retries configured for the schedule.

#### Response Example
```json
{
  "scheduleId": "scd_1234",
  "createdAt": 1623345678001,
  "cron": "0 0 1 * *",
  "destination": "https://example.com",
  "method": "POST",
  "header": {
    "Content-Type": ["application/json"]
  },
  "body": "{\"message\":\"hello\"}",
  "retries": 3
}
```
```

--------------------------------

### API Reference: Create Chat Completion Endpoint

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Documents the HTTP POST endpoint for generating textual responses from a large language model, specifying the URL and required authentication method.

```APIDOC
## POST /llm/v1/chat/completions

### Description
Creates a chat completion that generates a textual response for one or more messages using a large language model.

### Method
POST

### Endpoint
https://qstash.upstash.io/llm/v1/chat/completions

### Authentication
Bearer Token
```

--------------------------------

### Set Callback URL for QStash Messages

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to set success and failure callback URLs when publishing messages to QStash. This allows for asynchronous handling of message processing results. Examples are provided for cURL, TypeScript, and Python.

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
```

--------------------------------

### Initialize Upstash QStash Client in TypeScript

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to import and initialize the Upstash QStash client in a TypeScript application. Requires a valid QStash token for authentication, which is passed during client instantiation.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
});
```

--------------------------------

### Install Upstash QStash Library

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Installs the official Upstash QStash Node.js library using npm. This library is essential for interacting with QStash services, including receiving and verifying webhooks.

```shell
npm install @upstash/qstash

```

--------------------------------

### Publish Message with Custom Headers to QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to publish a JSON message to a specific URL using QStash, including forwarding custom HTTP headers. This example shows how to set 'Upstash-Forward-My-Header' for custom header forwarding, which will be delivered to the destination API.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a message to a specified URL, with support for custom headers.

### Method
POST

### Endpoint
/v2/publish/{url}

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to publish the message to.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Forward-My-Header** (string) - Optional - Custom header to forward to the destination.
- **Content-type** (string) - Required - The content type of the message body.

#### Request Body
- **body** (object) - Required - The JSON payload of the message.
```

```APIDOC
## POST /publishJSON

### Description
Publishes a JSON message to a specified URL, allowing for custom headers to be included.

### Method
POST

### Endpoint
/publishJSON

### Parameters
#### Request Body
- **url** (string) - Required - The URL where the message will be published.
- **body** (object) - Required - The JSON payload to send.
- **headers** (object) - Optional - Custom headers to include in the request.
```

--------------------------------

### Publish QStash Message with Callbacks

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to publish a message using QStash, specifying both a success callback URL and a failure callback URL. This allows for asynchronous handling of message delivery confirmation.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a given URL and allows specifying callback URLs for success and failure notifications. The request body is sent as JSON.

### Method
POST

### Endpoint
`/v2/publish/:url`

### Parameters
#### Path Parameters
- **url** (string) - Required - The URL to which the message will be published.

#### Query Parameters
None

#### Request Body
- **hello** (string) - Required - Example field in the message body.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type, typically `application/json`.
- **Upstash-Callback** (string) - Optional - The URL to send success notifications to.
- **Upstash-Failure-Callback** (string) - Optional - The URL to send failure notifications to.

### Request Example
```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
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

```APIDOC
## QStash Client Publish JSON

### Description
Publishes a JSON message using the QStash client library, including optional callback URLs for managing message delivery status.

### Method
N/A (Client Method)

### Endpoint
N/A

### Parameters
#### Request Body (Method Parameters)
- **url** (string) - Required - The target URL for the message.
- **body** (object) - Required - The JSON payload of the message.
- **callback** (string) - Optional - The URL to notify upon successful processing.
- **failureCallback** (string) - Optional - The URL to notify upon failure.

### Request Example
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
N/A (Asynchronous Operation)
```

```APIDOC
## QStash Client Message Publish JSON (Python)

### Description
Publishes a JSON message using the QStash Python client, allowing for the specification of callback URLs to handle delivery confirmations.

### Method
N/A (Client Method)

### Endpoint
N/A

### Parameters
#### Method Parameters
- **url** (string) - Required - The destination URL for the message.
- **body** (dict) - Required - The message payload as a dictionary.
- **callback** (string) - Optional - The URL to receive success callbacks.
- **failure_callback** (string) - Optional - The URL to receive failure callbacks.

### Request Example
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
```

### Response
N/A (Asynchronous Operation)
```

--------------------------------

### Batch Publish Response Example

Source: https://upstash.com/docs/qstash/qstash/features/batch

Illustrates the expected response format when publishing a batch of messages. It shows how message IDs and URLs are returned for successful deliveries, and how errors might be indicated.

```JSON
[
  [
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint1.com"
    },
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint2.com"
    }
  ],
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]

```

--------------------------------

### Invoke Server Action on Button Click (Next.js Page)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Updates the Next.js page component to import and call the `startBackgroundJob` server action when the button is clicked, initiating the background task.

```typescript
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

### QStash Request Signing: JWT Header Example

Source: https://upstash.com/docs/qstash/qstash/features/security

An example of the header part of a JWT used for request signing in Upstash QStash. It specifies the algorithm (HS256) and token type (JWT).

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

--------------------------------

### QStash Environment Variables Configuration

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Specifies the necessary environment variables for QStash integration. These include the QStash token and signing keys, which should be copied from the QStash dashboard.

```dotenv
# Copy all three from your QStash dashboard
QSTASH_TOKEN=
QSTASH_CURRENT_SIGNING_KEY=
QSTASH_NEXT_SIGNING_KEY=
```

--------------------------------

### Send Message

Source: https://upstash.com/docs/qstash/qstash/api/publish

Send a message to a specified destination using various configuration headers.

```APIDOC
## POST /websites/upstash-qstash

### Description
Send a message to a specified destination with custom configurations for retries, timeouts, callbacks, and headers.

### Method
POST

### Endpoint
/websites/upstash-qstash

### Parameters
#### Request Body
- **destination** (string) - Required - The topic name, URL, or QStash API name where the message will be sent.
- **body** (string) - Required - The raw message content.
- **Content-Type** (string) - Optional - The MIME type of the message content (e.g., `application/json`).

#### Headers
- **Upstash-Method** (string) - Optional - The HTTP method for the webhook (default: POST).
- **Upstash-Timeout** (string) - Optional - Timeout for the endpoint (e.g., "1s", "5m").
- **Upstash-Retries** (int) - Optional - Number of retries for message delivery (default: 3).
- **Upstash-Retry-Delay** (string) - Optional - Customizes the delay between retries (e.g., "1000", "pow(2, retried) * 1000").
- **Upstash-Forward-*** (string) - Optional - Custom headers to forward to the destination (e.g., `Upstash-Forward-My-Header`).
- **Upstash-Callback** (string) - Optional - URL for a callback after each attempt. Required for `api/llm` destination.
- **Upstash-Callback-*** (string) - Optional - Configuration for callback requests (e.g., timeout, retries).
- **Upstash-Callback-Forward-*** (string) - Optional - Custom headers for callback requests.
- **Upstash-Failure-Callback** (string) - Optional - URL for a callback on delivery failure.
- **Upstash-Failure-Callback-*** (string) - Optional - Configuration for failure callback requests.
- **Upstash-Failure-Callback-Forward-*** (string) - Optional - Custom headers for failure callback requests.

### Request Example
```json
{
  "destination": "https://example.com/webhook",
  "body": "{\"message\": \"Hello, QStash!\"}"
}
```

### Response
#### Success Response (200)
(Response details not provided in the source text)

#### Response Example
(Response example not provided in the source text)
```

--------------------------------

### Create a QStash Schedule

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Creates a new schedule for sending messages at a specified cron interval. Requires a QStash client initialized with an API token.

```typescript
import { Client } from "@upstash/qstash";

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

### POST /v2/keys/rotate

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This endpoint rotates QStash signing keys. It requires an authorization token in the header.

```APIDOC
## POST /v2/keys/rotate

### Description
Rotates QStash signing keys.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/keys/rotate

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```sh
curl https://qstash.upstash.io/v2/keys/rotate \
  -H "Authorization: Bearer <token>"
```

```javascript
const response = await fetch('https://qstash.upstash.io/v2/keys/rotate', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
}
response = requests.get(
  'https://qstash.upstash.io/v2/keys/rotate', 
  headers=headers
)
```

```go
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/keys/rotate", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

### Response
#### Success Response (200)
Details of the response are not provided in the source text.

#### Response Example
None provided.
```

--------------------------------

### Initialize AWS CDK Project with TypeScript and Upstash QStash

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

Commands to create a new AWS CDK project using TypeScript, install necessary dependencies including @upstash/qstash, and set up a basic Lambda directory structure.

```bash
mkdir my-app
cd my-app
cdk init app -l typescript
npm i @upstash/qstash
mkdir lambda
touch lambda/index.ts
```

--------------------------------

### POST /v2/publish/{destination}

Source: https://upstash.com/docs/qstash/qstash/api/publish

Publishes a message to a specified destination URL. This endpoint allows for asynchronous message delivery with various configuration options.

```APIDOC
## POST /v2/publish/{destination}

### Description
Publishes a message to a specified destination URL. Supports asynchronous message delivery with configurable retries, delays, and header forwarding.

### Method
POST

### Endpoint
`/v2/publish/{destination}`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL to which the message will be published.

#### Request Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - Specifies the content type, typically `application/json`.
- **Upstash-Method** (string) - Optional - The HTTP method to use for publishing (e.g., POST).
- **Upstash-Delay** (string) - Optional - A delay before the message is sent (e.g., `10s`).
- **Upstash-Retries** (integer) - Optional - The number of retries for failed deliveries.
- **Upstash-Retry-Delay** (string) - Optional - The delay strategy for retries (e.g., `pow(2, retried) * 1000`).
- **Upstash-Forward-Custom-Header** (string) - Optional - Custom headers to forward to the destination.

#### Request Body
- **message** (string) - Required - The content of the message to be published.

### Request Example
```json
{
  "message": "Hello, World!"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.
- **url** (string) - The destination URL where the message was sent.

#### Response Example
```json
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```
```

--------------------------------

### Handling Callbacks in Next.js

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

Provides an example of how to set up an API route in Next.js to receive and process QStash callback requests, including signature verification.

```APIDOC
## API Route for QStash Callbacks (Next.js)

### Description
This example shows how to create an API route in a Next.js application to handle incoming QStash callback requests. It includes decoding the base64 encoded body and verifying the request signature using `@upstash/qstash/nextjs`.

### Method
POST (Implicitly handled by Next.js API routes)

### Endpoint
`/api/callback` (Example path)

### Parameters
#### Request Body
- **body** (object) - Contains the callback payload from QStash, including a base64 encoded `body` field.

### Code Example (Next.js)
```javascript
// pages/api/callback.js

import { verifySignature } from "@upstash/qstash/nextjs";

function handler(req, res) {
  // QStash responses are base64-encoded
  const decodedBody = atob(req.body.body);
  console.log("Decoded Callback Body:", decodedBody);

  // Process the decoded data as needed

  return res.status(200).end();
}

export default verifySignature(handler);

export const config = {
  api: {
    bodyParser: false, // Disable default body parsing to handle raw body for signature verification
  },
};
```

### Notes
- Ensure you disable the default body parser (`bodyParser: false`) in `next.config.js` or the API route config to correctly verify the signature.
- Use `atob()` to decode the base64 encoded `body` field from the QStash callback payload.
- It is crucial to verify the signature of incoming requests to ensure they originate from QStash.
```

--------------------------------

### Create Schedule

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Creates a new schedule for sending messages. You can specify the destination URL and the cron expression for when the message should be sent.

```APIDOC
## POST /v2/schedules/:destination

### Description
Creates a schedule to send messages to a specific destination URL at a defined cron interval.

### Method
POST

### Endpoint
`/v2/schedules/:destination`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL where the message will be sent.

#### Headers
- **Upstash-Cron** (string) - Required - The cron expression defining the schedule (e.g., "0 0 * * *").
- **Content-type** (string) - Required - Set to "application/json".

#### Request Body
- **body** (object) - Optional - The JSON payload to send with the message.
  - **hello** (string) - Example field in the body.

### Request Example
```shell
curl -XPOST https://qstash.upstash.io/v2/schedules/https://example.com \
    -H "Upstash-Cron: 0 0 * * *" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }'
```

### Response
#### Success Response (200)
- **scheduleId** (string) - The unique identifier for the created schedule.
- **messageId** (string) - The unique identifier for the message associated with the schedule.

#### Response Example
```json
{
  "scheduleId": "sched_abc123",
  "messageId": "msg_xyz789"
}
```
```

--------------------------------

### Create and Retrieve QStash Queue with Parallelism in TypeScript

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Shows how to create or update a QStash queue with a specific parallelism setting (e.g., 2) using the `@upstash/qstash` TypeScript SDK. It also demonstrates fetching the queue's details to confirm the configuration.

```typescript
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName }).upsert({ parallelism: 2 });

const queueDetails = await client.queue({ queueName }).get();
```

--------------------------------

### Initialize Golang Project and Dependencies

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

This snippet shows the basic commands to create a new Go project directory, initialize go modules, and set up the project structure for a Golang application. It assumes you have Go and go modules enabled.

```bash
mkdir flyio-go
cd flyio-go
go mod init flyio-go

```

--------------------------------

### Publish messages in a batch using QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Publish multiple messages in a single request using the batch endpoint.

```APIDOC
## POST /v2/batch

### Description
Publish multiple messages in a single request to QStash.

### Method
POST

### Endpoint
`/v2/batch`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Set to "application/json".

### Request Body
- **messages** (array) - Required - An array of message objects, each specifying a destination.
  - **destination** (string) - Required - The URL where the message will be sent.

### Request Example
```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d \
     '[
      {
        "destination": "https://example.com/destination1"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'
```

### Response
#### Success Response (200)
- **messageIds** (array) - An array of message IDs for the published messages.

#### Response Example
```json
{
  "messageIds": ["msg_abc", "msg_def"]
}
```
```

--------------------------------

### Shell: List All QStash Schedules

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Retrieves a list of all schedules configured in QStash using a cURL command. It requires authentication via a Bearer token. This is useful for auditing or managing existing schedules.

```shell
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'
```

--------------------------------

### Test and Deploy Cloudflare Workers with Wrangler

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Learn how to test your Cloudflare Worker locally using `wrangler dev` and deploy it to the Cloudflare environment with `wrangler deploy`. These are essential commands for managing Cloudflare Worker applications.

```bash
npx wrangler dev
npx wrangler deploy
```

--------------------------------

### Publishing a message with Failure Callback

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

This example demonstrates how to publish a message to a destination URL and specify a failure callback URL using the `Upstash-Failure-Callback` header.

```APIDOC
## POST /v2/publish/<DESTINATION_URL>

### Description
Publishes a message to a specified destination URL and configures a failure callback URL to be invoked if message delivery fails after all retries.

### Method
POST

### Endpoint
`/v2/publish/<DESTINATION_URL>`

### Parameters
#### Header Parameters
- **Content-Type** (string) - Required - Set to `application/json`.
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Failure-Callback** (string) - Required - The URL to send the failure callback to.

#### Request Body
- **(object)** - The message payload to be sent.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
(No specific success response structure provided for this action, but typically a 200 OK would indicate the message was accepted for publishing.)

### Error Handling
(Error responses would typically follow standard HTTP error codes and formats.)
```

--------------------------------

### API Reference: Create Chat Completion Endpoint

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Specifies the POST endpoint for generating text completions using large language models via QStash. It details the URL, authentication method (Bearer Token), and the endpoint's purpose.

```APIDOC
Endpoint: POST https://qstash.upstash.io/llm/v1/chat/completions
Description: Creates a chat completion that generates a textual response for one or more messages using a large language model.
Authentication: Bearer Token
```

--------------------------------

### AWS CDK Lambda and API Gateway Setup (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

Defines an AWS CDK stack to create a Lambda function for video processing and an API Gateway to expose it. Requires aws-cdk-lib and constructs. Sets up Node.js runtime for Lambda and a POST method on the API Gateway root.

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

### Publish messages in a batch using QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Publishes multiple messages simultaneously in a single API request. This is useful for efficiency when sending many messages.

```shell
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d \
     '[
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
```

--------------------------------

### GET /v2/flowControl/

Source: https://upstash.com/docs/qstash/qstash/api/flow-control/list

Retrieves a list of all configured flow controls and their current wait list sizes.

```APIDOC
## GET /v2/flowControl/

### Description
Retrieves a list of all configured flow controls and their current wait list sizes.

### Method
GET

### Endpoint
/v2/flowControl/

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```curl
curl -X GET https://qstash.upstash.io/v2/flowControl/  -H "Authorization: Bearer <token>"
```

### Response
#### Success Response (200)
- **flowControls** (array) - A list of flow control objects.
  - **flowControlKey** (string) - The key of the flow control.
  - **waitListSize** (integer) - The number of messages in the wait list.

#### Response Example
```json
{
  "flowControls": [
    {
      "flowControlKey": "<string>",
      "waitListSize": 123
    }
  ]
}
```
```

--------------------------------

### Publish LLM Request with QStash and Anthropic

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to publish a single LLM chat completion request to Anthropic's API using QStash's `publishJSON` method. It shows how to specify the LLM API with the Anthropic provider and include an asynchronous callback URL for handling responses.

```APIDOC
## POST /api/publishJSON

### Description
Publishes a JSON payload to a QStash queue, allowing for asynchronous processing and integration with external services.

### Method
POST

### Endpoint
/api/publishJSON

### Parameters
#### Request Body
- **api** (object) - Required - Specifies the target API for the message.
  - **name** (string) - Required - The name of the API, e.g., "llm".
  - **provider** (object) - Required - The provider-specific configuration.
    - **name** (string) - Required - The name of the provider, e.g., "anthropic".
    - **token** (string) - Required - The authentication token for the provider.
- **body** (object) - Required - The payload of the message to be sent.
- **callback** (string) - Optional - The URL to send the response callback to.
```

--------------------------------

### QStash Request Signing: JWT Payload Example

Source: https://upstash.com/docs/qstash/qstash/features/security

An example of the payload part of a JWT used for request signing in Upstash QStash. It includes standard JWT claims like issuer, subject, expiration, and a base64 encoded hash of the request body.

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

### Get Message Logs with cURL

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

Shows how to retrieve message logs from QStash using a cURL command. Authentication is required via an Authorization header.

```shell
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

--------------------------------

### GET /v2/queues

Source: https://upstash.com/docs/qstash/qstash/api/queues/list

Retrieves a list of all queues associated with your QStash account.

```APIDOC
## GET /v2/queues

### Description
Retrieves a list of all queues associated with your QStash account.

### Method
GET

### Endpoint
/v2/queues

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```bash
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"
```

### Response
#### Success Response (200)
An array of queue objects.
- **createdAt** (int) - The creation time of the queue. UnixMilli
- **updatedAt** (int) - The update time of the queue. UnixMilli
- **name** (string) - The name of the queue.
- **parallelism** (int) - The number of parallel consumers consuming from the queue.
- **lag** (int) - The number of unprocessed messages that exist in the queue.

#### Response Example
```json
[
  {
    "createdAt": 1623345678001,
    "updatedAt": 1623345678001,
    "name": "my-queue",
    "parallelism" : 5, 
    "lag" : 100
  }
]
```
```

--------------------------------

### Publishing a Message with Custom Retry Delay

Source: https://upstash.com/docs/qstash/qstash/features/retry

This example shows how to publish a message with a custom retry delay strategy defined by the `Upstash-Retry-Delay` header.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a message with a custom delay strategy between retry attempts, overriding the default exponential backoff.

### Method
POST

### Endpoint
`/v2/publish/https://my-api...`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type, typically `application/json`.
- **Upstash-Retries** (integer) - Optional - The maximum number of retry attempts.
- **Upstash-Retry-Delay** (string) - Optional - A mathematical expression to calculate the delay between retries. Uses the `retried` variable (current retry count starting from 0) and supported functions like `pow`, `min`, `max`.

### Request Body
- **body** (object) - Required - The payload of the message to be sent.
  - **hello** (string) - Example field in the message payload.

### Request Example
```curl
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

### Response
#### Success Response (200)
Indicates the message was successfully published for delivery.

#### Response Example
(Response details not provided in the source text, typically an acknowledgment of receipt.)
```

--------------------------------

### Run QStash CLI Development Server from Binary

Source: https://upstash.com/docs/qstash/qstash/howto/local-development

Executes the QStash CLI development server directly after downloading the binary. Assumes the binary is in the current directory.

```bash
$ ./qstash dev
```

--------------------------------

### Get Message Logs

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

Retrieve logs for all messages that have been published, with optional filtering.

```APIDOC
## GET /v2/logs

### Description
Retrieve logs for all messages that have been published (filtering is also available).

### Method
GET

### Endpoint
/v2/logs

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.

#### Query Parameters
- **filter** (string) - Optional - Filter criteria for the logs.

### Response
#### Success Response (200)
- **logs** (array) - An array of log objects.
  - **messageId** (string) - The ID of the message.
  - **status** (string) - The status of the message (e.g., 'published', 'delivered').
  - **timestamp** (string) - The timestamp of the log entry.

#### Response Example
```json
{
  "logs": [
    {
      "messageId": "msg_12345",
      "status": "published",
      "timestamp": "2023-10-27T10:00:00Z"
    }
  ]
}
```
```

--------------------------------

### Publishing a Message with Custom Retries

Source: https://upstash.com/docs/qstash/qstash/features/retry

This example demonstrates how to publish a message using cURL and specifies a custom number of retries using the `Upstash-Retries` header.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a message to a specified URL. This example shows how to configure the number of retry attempts for the delivery.

### Method
POST

### Endpoint
`/v2/publish/https://my-api...`

### Headers
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-type** (string) - Required - Specifies the content type, typically `application/json`.
- **Upstash-Retries** (integer) - Optional - The maximum number of times QStash will retry sending the message if the initial delivery fails. If not set, QStash uses the default maximum retries based on the plan.

### Request Body
- **body** (object) - Required - The payload of the message to be sent.
  - **hello** (string) - Example field in the message payload.

### Request Example
```curl
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 2" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

### Response
#### Success Response (200)
Indicates the message was successfully published for delivery.

#### Response Example
(Response details not provided in the source text, typically an acknowledgment of receipt.)
```

--------------------------------

### Publish Message using cURL

Source: https://upstash.com/docs/qstash/qstash/api/publish

Publishes a message to a specified URL using the Upstash QStash API. Includes headers for method, delay, retries, retry delay, and custom headers. Requires an authorization token and specifies the message content as JSON.

```curl
curl -X POST "https://qstash.upstash.io/v2/publish/https://www.example.com" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Method: POST" \
  -H "Upstash-Delay: 10s" \
  -H "Upstash-Retries: 3" \
  -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
  -H "Upstash-Forward-Custom-Header: custom-value" \
  -d '{"message":"Hello, World!"}'
```

--------------------------------

### Receive QStash Webhooks in Cloudflare Worker with TypeScript

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Provides the complete TypeScript code for a Cloudflare Worker to receive and verify QStash webhooks. It utilizes the `@upstash/qstash` Receiver, environment variables for signing keys, and includes signature validation with error handling.

```ts
import { Receiver } from "@upstash/qstash";
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string;
  QSTASH_NEXT_SIGNING_KEY: string;
}

export default {
  async fetch(
    request: Request,
    env: Env,
    ctx: ExecutionContext
  ): Promise<Response> {
    const c = new Receiver ({
      currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
      nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
    });

    const body = await request.text();

    const isValid = await c
      .verify ({
        signature: request.headers.get("Upstash-Signature")!,
        body,
      })
      .catch((err) => {
        console.error(err);
        return false;
      });
    if (!isValid) {
      return new Response("Invalid signature", { status: 401 });
    }
    console.log("The signature was valid");

    // do work here

    return new Response("Hello World!");
  }
};

```

--------------------------------

### Publish LLM Request with QStash and Anthropic (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to publish a single LLM chat completion request to Anthropic's API using QStash's `publishJSON` method. It specifies the LLM API with the Anthropic provider and includes an asynchronous callback URL for handling responses. Requires @upstash/qstash SDK.

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

### QStash Message Headers

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Details the standard and custom HTTP headers included by QStash when delivering a message to a destination API endpoint. These headers provide information about the message, retries, and security signatures.

```APIDOC
## QStash Message Headers

### Description
Details the standard and custom HTTP headers included by QStash when delivering a message to a destination API endpoint. It specifies the purpose and typical values for each header, including those related to message identification, retry attempts, and security signatures.

### Headers
- **User-Agent** (string) - Will be set to `Upstash-QStash`
- **Content-Type** (string) - The original `Content-Type` header
- **Upstash-Topic-Name** (string) - The URL Group (topic) name if sent to a URL Group
- **Upstash-Signature** (string) - The signature you need to verify
- **Upstash-Retried** (integer) - How often the message has been retried so far. Starts with 0.
- **Upstash-Message-Id** (string) - The message id of the message.
- **Upstash-Schedule-Id** (string) - The schedule id of the message if it is related to a schedule.
- **Upstash-Caller-Ip** (string) - The IP address of the publisher of this message.
```

--------------------------------

### cURL/JavaScript/Python/Go: Remove Endpoints from URL Group

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Removes specific endpoints from a QStash URL group via the API. These examples demonstrate how to construct a DELETE request with a JSON payload specifying the endpoints to remove. They cover cURL, JavaScript (using fetch), Python (using requests), and Go.

```curl
curl -XDELETE https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ \
    "endpoints": [ \
      { \
        "name": "endpoint1", \
      }, \
      { \
        "url": "https://somewhere-else.com" \
      } \
    ] \
  }'
```

```js
const response = await fetch("https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", {
  method: "DELETE",
  headers: {
    Authorization: "Bearer <token>",
    "Content-Type": "application/json",
  },
  body: {
    endpoints: [
      {
        name: "endpoint1",
      },
      {
        url: "https://somewhere-else.com",
      },
    ],
  },
});
```

```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
}

data = {
   "endpoints": [
      {
        "name": "endpoint1",
      },
      {
        "url": "https://somewhere-else.com"
      }
    ]
}

response = requests.delete(
  'https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints',
  headers=headers,
  data=data
)
```

```go
var data = strings.NewReader(`{
  "endpoints": [
    {
      "name": "endpoint1",
    },
    {
      "url": "https://somewhere-else.com"
    }
  ]
`)
```

--------------------------------

### Configure Parallelism for a QStash Queue

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This snippet shows how to configure the parallelism setting for a QStash queue. Parallelism controls how many messages can be processed concurrently, preventing endpoint overload.

```APIDOC
## POST /v2/queues/

### Description
Creates or updates a QStash queue with specified configuration, including parallelism.

### Method
POST

### Endpoint
/v2/queues/

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue.

#### Request Body
- **queueName** (string) - Required - The name of the queue.
- **parallelism** (integer) - Optional - The maximum number of messages to process concurrently.
```

```APIDOC
## POST /queue/{queueName}/upsert

### Description
Upserts a QStash queue with new configuration. This can be used to change settings like parallelism.

### Method
POST

### Endpoint
/queue/{queueName}/upsert

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue.

#### Request Body
- **parallelism** (integer) - Required - The desired parallelism level for the queue.
```

--------------------------------

### QStash Standard and Custom HTTP Headers

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Lists the standard and custom HTTP headers provided by QStash when delivering a message. It details the purpose of each header, such as message identification, retry count, and signature verification.

```APIDOC
Headers:
  User-Agent:
    Description: Will be set to `Upstash-QStash`
  Content-Type:
    Description: The original `Content-Type` header
  Upstash-Topic-Name:
    Description: The URL Group (topic) name if sent to a URL Group
  Upstash-Signature:
    Description: The signature you need to verify
  Upstash-Retried:
    Description: How often the message has been retried so far. Starts with 0.
  Upstash-Message-Id:
    Description: The message id of the message.
  Upstash-Schedule-Id:
    Description: The schedule id of the message if it is related to a schedule.
  Upstash-Caller-Ip:
    Description: The IP address of the publisher of this message.
```

--------------------------------

### GET /v2/queues/{queueName}

Source: https://upstash.com/docs/qstash/qstash/api/queues/get

Retrieves the details of a specific queue, including its creation time, update time, name, parallelism, and lag.

```APIDOC
## GET /v2/queues/{queueName}

### Description
Retrieves the details of a specific queue, including its creation time, update time, name, parallelism, and lag.

### Method
GET

### Endpoint
/v2/queues/{queueName}

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to retrieve.

#### Request Body
None

### Response
#### Success Response (200)
- **createdAt** (int) - The creation time of the queue. UnixMilli
- **updatedAt** (int) - The update time of the queue. UnixMilli
- **name** (string) - The name of the queue.
- **parallelism** (int) - The number of parallel consumers consuming from the queue.
- **lag** (int) - The number of unprocessed messages that exist in the queue.

#### Response Example
```json
{
  "createdAt": 1623345678001,
  "updatedAt": 1623345678001,
  "name": "my-queue",
  "parallelism": 5,
  "lag": 100
}
```
```

--------------------------------

### Verify QStash Request Signature using SDK

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This snippet demonstrates how to verify incoming QStash request signatures using the official QStash SDKs. It shows the initialization of the `Receiver` with `currentSigningKey` and `nextSigningKey`, and then how to use the `verify` method. The method requires the raw request body, the signature from the `Upstash-Signature` header, and optionally the request URL. It's crucial to use the raw body string to avoid verification failures.

```APIDOC
## POST /webhook/callback

### Description
Verifies the signature of an incoming webhook request from QStash to ensure its authenticity and integrity.

### Method
POST

### Endpoint
/webhook/callback

### Parameters
#### Header Parameters
- **Upstash-Signature** (string) - Required - The signature of the request provided by QStash.

#### Request Body
- **body** (string) - Required - The raw request body received from QStash.

#### Query Parameters
- **url** (string) - Optional - The URL of the request, used for signature verification.

### Request Example
```json
{
  "body": "{\"message\": \"Hello World\"}",
  "signature": "your_signature_here"
}
```

### Response
#### Success Response (200)
- **isValid** (boolean) - Indicates whether the signature verification was successful.
```

--------------------------------

### Understand QStash API Rate Limit Headers

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This APIDOC details the HTTP headers returned by the QStash API when rate limits are exceeded. It categorizes headers for daily, burst, and chat-based limits, explaining the maximum requests/tokens, remaining counts, and reset times.

```APIDOC
API Rate Limit Headers:
  Daily Rate Limit:
    RateLimit-Limit: Maximum number of requests allowed per day
    RateLimit-Remaining: Remaining number of requests for the day
    RateLimit-Reset: Time (in unix timestamp) when the daily limit will reset
  Burst Rate Limit:
    Burst-RateLimit-Limit: Maximum number of requests allowed in the burst window (1 second)
    Burst-RateLimit-Remaining: Remaining number of requests in the burst window (1 second)
    Burst-RateLimit-Reset: Time (in unix timestamp) when the burst limit will reset
  Chat-based Rate Limit:
    x-ratelimit-limit-requests: Maximum number of requests allowed per day
    x-ratelimit-limit-tokens: Maximum number of tokens allowed per day
    x-ratelimit-remaining-requests: Remaining number of requests for the day
    x-ratelimit-remaining-tokens: Remaining number of tokens for the day
    x-ratelimit-reset-requests: Time (in unix timestamp) until the request limit resets
    x-ratelimit-reset-tokens: Time (in unix timestamp) when the token limit will reset
```

--------------------------------

### Fly.io: Deploying the application

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

The command to deploy the configured Golang application to fly.io. After setting up the code, dependencies, and environment variables, this command pushes the application to the fly.io platform.

```bash
flyctl deploy

```

--------------------------------

### QStash Publish Message API Endpoint Definition

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Documents the QStash API endpoint for publishing messages, including the HTTP method, URL structure, authentication requirements, path parameters, and various request headers for controlling message delivery and deduplication.

```APIDOC
## POST /v2/publish/{destination}

### Description
Publishes a message to a specified destination. The destination can be a topic name, a URL, or a QStash API name. Supports various headers for controlling message delivery, such as delays and deduplication.

### Method
POST

### Endpoint
`https://qstash.upstash.io/v2/publish/{destination}`

### Parameters
#### Path Parameters
- **destination** (string, required):
  - Description: The destination for the message. This can be a topic name or ID configured in the Upstash console, a valid URL (prefixed with `http://` or `https://`), or a valid QStash API name (e.g., `api/llm`).

#### Request Headers
- **Authorization**: Bearer Token
- **Upstash-Delay** (string, optional):
  - Description: Delays the message delivery.
  - Format: A number followed by a duration abbreviation (e.g., `10s`, `3m`, `10h`, `1d`).
  - Example: `"50s"`
- **Upstash-Not-Before** (int, optional):
  - Description: Delays the message delivery until a specific time in the future.
  - Format: Unix timestamp in seconds (UTC).
  - Note: If both `Upstash-Not-Before` and `Upstash-Delay` are provided, `Upstash-Not-Before` takes precedence.
- **Upstash-Deduplication-Id** (string, optional):
  - Description: An ID used for message deduplication to ensure only one message with this ID is published.
- **Upstash-Content-Based-Deduplication** (boolean, optional):
  - Description: When set to true, automatically deduplicates messages based on their content (Destination, Body, Headers).

### Response
#### Success Response (200)
- **messageId** (string): The unique identifier for the published message.
- **url** (string): The URL where the message was sent.
- **deduplicated** (boolean, optional): Indicates if the message was deduplicated.

#### Response Example
Example Single Message Response:
```json
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```
Example URL Group Response:
```json
[
  {
    "messageId": "msd_1234",
    "url": "https://www.example.com"
  },
  {
    "messageId": "msd_5678",
    "url": "https://www.somewhere-else.com",
    "deduplicated": true
  }
]
```
```

--------------------------------

### Send Batch Emails with QStash and Resend

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates sending multiple emails in a batch using the `qstash-js` SDK and Resend's Batch Email API. The `batch: true` option is enabled in the provider configuration, and each email is defined with sender, recipient, subject, and HTML content.

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
    }
  ],
});
```

--------------------------------

### Remove Endpoints from URL Group

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Removes one or more endpoints from a specified URL group.

```APIDOC
## DELETE /v2/topics/:urlGroupName/endpoints

### Description
Removes endpoints from a URL group.

### Method
DELETE

### Endpoint
`/v2/topics/:urlGroupName/endpoints`

### Parameters
#### Path Parameters
- **urlGroupName** (string) - Required - The name of the URL group.

#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Content-Type** (string) - Required - Set to `application/json`.

#### Request Body
- **endpoints** (array) - Required - A list of endpoints to remove.
  - **name** (string) - Optional - The name of the endpoint to remove.
  - **url** (string) - Optional - The URL of the endpoint to remove.

### Request Example
**cURL:**
```curl
curl -XDELETE https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ \
    "endpoints": [ \
      { \
        "name": "endpoint1", \
      }, \
      { \
        "url": "https://somewhere-else.com" \
      }
    ]
  }'
```

**JavaScript:**
```javascript
const response = await fetch("https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", {
  method: "DELETE",
  headers: {
    Authorization: "Bearer <token>",
    "Content-Type": "application/json",
  },
  body: {
    endpoints: [
      {
        name: "endpoint1",
      },
      {
        url: "https://somewhere-else.com",
      },
    ],
  },
});
```

**Python:**
```python
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
}

data = {
   "endpoints": [
      {
        "name": "endpoint1",
      },
      {
        "url": "https://somewhere-else.com"
      }
    ]
}

response = requests.delete(
  'https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints',
  headers=headers,
  data=data
)
```

**Go:**
```go
var data = strings.NewReader(`{
  "endpoints": [
    {
      "name": "endpoint1",
    },
    {
      "url": "https://somewhere-else.com"
    }
  ]
`) // Note: In a real Go application, you would construct this JSON more robustly.
// The actual HTTP request would then be made using the http.Client.
```
```

--------------------------------

### Go: Verify QStash Signature

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Verifies the Upstash signature for incoming requests. It uses JWT parsing and SHA256 hashing to ensure the request is authentic and has not been tampered with. Dependencies include the jwt-go and crypto/sha256 libraries.

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

### Connect to Upstash Redis using redis-cli

Source: https://upstash.com/docs/qstash/redis

Connect to your Upstash Redis database using the redis-cli tool. This requires your database's password, endpoint, and port. It demonstrates basic Redis commands like SET, GET, and INCR.

```redis-cli
> redis-cli --tls -a PASSWORD -h ENDPOINT -p PORT
ENDPOINT:PORT> set counter 0
OK
ENDPOINT:PORT> get counter
"0"
ENDPOINT:PORT> incr counter
(int) 1
ENDPOINT:PORT> incr counter
(int) 2
```

--------------------------------

### QStash CLI dev Command Help and Options

Source: https://upstash.com/docs/qstash/qstash/howto/local-development

Displays the usage information and available options for the `dev` command in the QStash CLI. Options include specifying the port and user quota type.

```bash
$ ./qstash dev --help
Usage of dev:
  -port int
        The port to start HTTP server at [env QSTASH_DEV_PORT] (default 8080)
  -quota string
        The quota of users [env QSTASH_DEV_QUOTA] (default "payg")
```

--------------------------------

### Publish with Parallelism Limit

Source: https://upstash.com/docs/qstash/qstash/features/flowcontrol

This code example shows how to publish a JSON message with a parallelism limit. It sets the limit to 10 active calls concurrently, managed by a specific key.

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", parallelism: 10 },
});
```

--------------------------------

### Verify QStash Request Signature (TypeScript, Python)

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Shows how to verify incoming QStash request signatures using the official QStash SDKs. It involves initializing the `Receiver` with signing keys and using the `verify` method with the raw request body and signature. Crucial for security, it requires the raw body string to prevent verification failures. Available for TypeScript and Python.

```typescript
import { Receiver } from "@upstash/qstash";

const receiver = new Receiver({
  currentSigningKey: "YOUR_CURRENT_SIGNING_KEY",
  nextSigningKey: "YOUR_NEXT_SIGNING_KEY",
});

// ... in your request handler

const signature = req.headers["Upstash-Signature"];
const body = req.body;

const isValid = receiver.verify({
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
```

--------------------------------

### Publish QStash Message with Timeout using Python SDK

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This Python snippet demonstrates how to publish a JSON message using the QStash SDK and set a timeout for the request. The 'timeout' parameter specifies how long QStash should wait for a response from the target URL.

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

--------------------------------

### Verify QStash Signature for App Router (TypeScript/Next.js)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Wraps a request handler with `verifySignatureAppRouter` to ensure requests to the endpoint originate from QStash. It requires QSTASH_CURRENT_SIGNING_KEY and QSTASH_NEXT_SIGNING_KEY environment variables.

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

### Create AWS Lambda Deployment Package (Makefile)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/python

This script, intended for a Makefile, handles the creation of a zip file for AWS Lambda deployment. It installs the 'pyjwt' dependency into a 'dist' directory, copies the Lambda function code, and then zips the contents of the 'dist' directory into 'lambda.zip'.

```makefile
zip:
	rm -rf dist
	pip3 install --target ./dist pyjwt
	cp lambda_function.py ./dist/lambda_function.py
	cd dist && zip -r lambda.zip .
	mv ./dist/lambda.zip ./

```

--------------------------------

### POST /v2/queues/{queueName}/resume

Source: https://upstash.com/docs/qstash/qstash/api/queues/resume

Resumes a paused queue, starting the delivery of enqueued messages. If the queue is already active, this operation has no effect.

```APIDOC
## POST /v2/queues/{queueName}/resume

### Description
Resumes a paused queue, restarting message delivery from the earliest undelivered message. If the queue is already active, this action has no effect.

### Method
POST

### Endpoint
/v2/queues/{queueName}/resume

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to resume.

#### Query Parameters
None

#### Request Body
None

### Request Example
```curl
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/resume \
  -H "Authorization: Bearer <token>"
```

### Response
#### Success Response (200)
- **status** (string) - Indicates success, typically "OK".

#### Response Example
```json
{
  "status": "OK"
}
```
```

--------------------------------

### Verify Incoming Webhook Signatures with Upstash QStash SDK

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

A TypeScript example for an AWS Lambda handler that uses the @upstash/qstash SDK to verify incoming webhook signatures. It requires QSTASH_CURRENT_SIGNING_KEY and QSTASH_NEXT_SIGNING_KEY environment variables.

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

### API Rate Limit Headers

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This section documents the specific HTTP headers returned by the QStash API when various rate limits are exceeded. It categorizes headers by daily, burst, and chat-based limits, providing details on the maximum allowed requests/tokens, remaining counts, and reset times.

```APIDOC
## API Rate Limit Headers

### Description
Documents the specific HTTP headers returned by the QStash API when various rate limits are exceeded. It categorizes headers by daily, burst, and chat-based limits, providing details on the maximum allowed requests/tokens, remaining counts, and reset times.

### Daily Rate Limit Headers
- **RateLimit-Limit**: Maximum number of requests allowed per day
- **RateLimit-Remaining**: Remaining number of requests for the day
- **RateLimit-Reset**: Time (in unix timestamp) when the daily limit will reset

### Burst Rate Limit Headers
- **Burst-RateLimit-Limit**: Maximum number of requests allowed in the burst window (1 second)
- **Burst-RateLimit-Remaining**: Remaining number of requests in the burst window (1 second)
- **Burst-RateLimit-Reset**: Time (in unix timestamp) when the burst limit will reset

### Chat-based Rate Limit Headers
- **x-ratelimit-limit-requests**: Maximum number of requests allowed per day
- **x-ratelimit-limit-tokens**: Maximum number of tokens allowed per day
- **x-ratelimit-remaining-requests**: Remaining number of requests for the day
- **x-ratelimit-remaining-tokens**: Remaining number of tokens for the day
- **x-ratelimit-reset-requests**: Time (in unix timestamp) until the request limit resets
- **x-ratelimit-reset-tokens**: Time (in unix timestamp) when the token limit will reset
```

--------------------------------

### Publish to QStash via cURL

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

Example of how to send a POST request to a QStash published endpoint using cURL. It includes authorization headers and a JSON payload. Requires QStash URL and token.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/<YOUR-LAMBDA-URL>" \
-H "Authorization: Bearer <QSTASH_TOKEN>" \
-H "Content-Type: application/json" \
-d "{ \"hello\": \"world\"}"
```

--------------------------------

### Python HTTP Server for Database Cleanup (Python)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

A Python script that uses the built-in 'http.server' module to create a basic HTTP server. It exposes a POST endpoint that triggers the database cleanup logic.

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

### Configure Headers for a QStash URL Group

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This cURL command illustrates how to update a QStash URL Group to define default headers. These headers will automatically apply to all messages published to this group, providing consistent behavior for webhook processing.

```APIDOC
## POST /v2/topics/{URL_GROUP_NAME}

### Description
Updates a QStash URL Group to define default headers that will be applied to all messages published to this group.

### Method
PATCH

### Endpoint
`/v2/topics/<URL_GROUP_NAME>`

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer <QSTASH_TOKEN>

#### Request Body
- **headers** (object) - Required - An object containing key-value pairs for default headers.
  - **key** (string or array of strings) - The header name.
  - **value** (string or array of strings) - The header value(s).

### Request Example
```json
{
    "headers": {
        "Upstash-Header-Forward": ["true"],
        "Upstash-Retries": "3"
    }
}
```
```

--------------------------------

### Create API Endpoint for Background Job Handling (TypeScript/Next.js)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Defines a POST endpoint in a Next.js application to handle background jobs. This endpoint processes incoming JSON data, sends multiple requests with delays, and returns a success response. It's designed to be called by QStash.

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

### Schedule QStash Job via SDK (Python)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

Python code snippet demonstrating how to use the QStash SDK to programmatically create a schedule. It requires the QStash token and specifies the destination URL and cron schedule.

```python
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://YOUR_URL.vercel.app/api",
    cron="0 12 * * *",
)

```

--------------------------------

### Publish with Relative Delay (cURL)

Source: https://upstash.com/docs/qstash/qstash/features/delay

This example demonstrates how to publish a message with a relative delay using the Upstash-Delay header in a cURL request. The delay is specified in a human-readable format like '1m' for one minute.

```cURL
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 1m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

--------------------------------

### Verify Upstash QStash Webhook Signature in AWS Lambda (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This TypeScript code demonstrates how to verify incoming Upstash QStash webhook signatures within an AWS Lambda function using the `@upstash/qstash` SDK.

```APIDOC
## AWS Lambda Handler for QStash Signature Verification

### Description
Verifies incoming Upstash QStash webhook signatures within an AWS Lambda function using the `@upstash/qstash` SDK. It checks for the `upstash-signature` header and validates the request body and signature.

### Language
TypeScript

### Dependencies
- `@upstash/qstash` SDK
- `aws-lambda` types

### Environment Variables
- **QSTASH_CURRENT_SIGNING_KEY**: The current signing key for QStash.
- **QSTASH_NEXT_SIGNING_KEY**: The next signing key for QStash.

### Handler Function Logic
1. Retrieves the `upstash-signature` header from the incoming event.
2. Constructs the Lambda function's URL.
3. Uses `receiver.verify` to validate the request body and signature.
4. Returns `401` for missing or invalid signatures, and `200` for successful verification.
5. Handles potential errors during the verification process.

### Code Example
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
```

--------------------------------

### Retrieve URL Group Response Structure

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Illustrates the JSON response body for a successful QStash API request to retrieve a URL group. It shows the structure of the `endpoints` array, which contains details about each configured endpoint within the group.

```json
{
  "createdAt": 1623345678001,
  "updatedAt": 1623345678001,
  "name": "my-url-group",
  "endpoints": [
    {
      "name": "my-endpoint",
      "url": "https://my-endpoint.com"
    }
  ]
}
```

--------------------------------

### Publish Image Processing Task with QStash (Next.js Route Handler)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Queues an image processing task by publishing a JSON message to a specified URL using the QStash client. It includes image uploading logic and returns the QStash message ID. Requires QSTASH_TOKEN environment variable.

```typescript
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

### Publish a message with timeout

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This snippet demonstrates how to set a timeout for a QStash message using the Python SDK. The `timeout` parameter specifies the maximum duration QStash will wait for a response when calling the target URL.

```APIDOC
## Publish a message with timeout

### Description
Demonstrates how to set a timeout for a QStash message using the Python SDK. The `timeout` parameter specifies the maximum duration QStash will wait for a response when calling the target URL, preventing long-running requests from blocking the system.

### Language
Python

### Code Example
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

--------------------------------

### Configure QStash URL Group Headers with cURL

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to update a QStash URL Group using cURL to set default headers for all messages sent to that group. This includes setting headers like 'Upstash-Header-Forward' and 'Upstash-Retries'.

```Shell
curl -X PATCH https://qstash.upstash.io/v2/topics/<URL_GROUP_NAME> \
    -H "Authorizarion: Bearer <QSTASH_TOKEN>"
    -d '{ "headers": { "Upstash-Header-Forward": ["true"], "Upstash-Retries": "3" } }'
```

--------------------------------

### Publish with Absolute Delay (cURL)

Source: https://upstash.com/docs/qstash/qstash/features/delay

This example shows how to publish a message with an absolute delay using the Upstash-Not-Before header. The delay is set to a specific Unix timestamp, ensuring the message is delivered no earlier than that time.

```cURL
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Not-Before: 1657104947" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

--------------------------------

### Cancel Multiple QStash Messages in Python

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This Python snippet demonstrates how to cancel multiple messages simultaneously. It supports canceling specific message IDs or all messages in the database.

```python
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

# cancel more than one message
client.message.cancel_many(["<msg-id-0>", "<msg-id-1>"])

```

--------------------------------

### QStash Message Retrieval Response

Source: https://upstash.com/docs/qstash/qstash/api/messages/get

Example JSON response body for a successfully retrieved QStash message. It includes details like message ID, topic, URL, method, headers, body, and creation timestamp.

```json
{
  "messageId": "msg_123",
  "topicName": "myTopic",
  "url":"https://example.com",
  "method": "POST",
  "header": {
    "My-Header": ["my-value"]
  },
  "body": "{\"foo\":\"bar\"}",
  "createdAt": 1620000000000
}
```

--------------------------------

### QStash Callback Response Body Structure

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Defines the JSON structure for payloads sent by QStash to a callback URL. It includes message status, headers, base64 encoded body, retry information, and metadata about the source message.

```APIDOC
{
  "status": 200,
  "header": { "key": ["value"] },         // Response header
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==", // base64 encoded response body
  "retried": 2,                           // How many times we retried to deliver the original message
  "maxRetries": 3,                        // Number of retries before the message assumed to be failed to delivered.
  "sourceMessageId": "msg_xxx",           // The ID of the message that triggered the callback
  "topicName": "myTopic",                 // The name of the URL Group (topic) if the request was part of a URL Group
  "endpointName": "myEndpoint",           // The endpoint name if the endpoint is given a name within a topic
  "url": "http://myurl.com",              // The destination url of the message that triggered the callback
  "method": "GET",                        // The http method of the message that triggered the callback
  "sourceHeader": { "key": "value" },     // The http header of the message that triggered the callback
```

--------------------------------

### Define QStash Publish Message API Endpoint

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This APIDOC defines the QStash API endpoint for publishing messages. It details the HTTP method (POST), URL structure, authentication (Bearer Token), path parameters like 'destination', and various optional request headers for controlling message delivery and deduplication.

```APIDOC
API Endpoint: POST https://qstash.upstash.io/v2/publish/{destination}
Authentication: Bearer Token

Path Parameters:
  - destination (string, required):
      Description: Destination can either be a topic name or id that you configured in the Upstash console, a valid url where the message gets sent to, or a valid QStash API name like `api/llm`. If the destination is a URL, make sure the URL is prefixed with a valid protocol (`http://` or `https://`).

Request Headers:
  - Upstash-Delay (string, optional):
      Description: Delay the message delivery.
      Format: number followed by duration abbreviation (e.g., `10s`, `3m`, `10h`, `1d`).
      Example: "50s" | "3m" | "10h" | "1d"
  - Upstash-Not-Before (int, optional):
      Description: Delay the message delivery until a certain time in the future.
      Format: Unix timestamp in seconds, based on the UTC timezone.
      Note: When both `Upstash-Not-Before` and `Upstash-Delay` headers are provided, `Upstash-Not-Before` will be used.
  - Upstash-Deduplication-Id (string, optional):
      Description: Id to use while deduplicating messages, so that only one message with the given deduplication id is published.
  - Upstash-Content-Based-Deduplication (boolean, optional):
      Description: When set to true, automatically deduplicates messages based on their content, so that only one message with the same content is published.
      Content based deduplication creates unique deduplication ids based on the following message fields:
        - Destination
        - Body
        - Headers

Response:
  (Refer to qstash-publish-response.mdx for full details)
  Example Single Message Response:
    {
      "messageId": "msd_1234",
      "url": "https://www.example.com"
    }
  Example URL Group Response:
    [
      {
        "messageId": "msd_1234",
        "url": "https://www.example.com"
      },
      {
        "messageId": "msd_5678",
        "url": "https://www.somewhere-else.com",
        "deduplicated": true
      }
    ]
```

--------------------------------

### Run QStash CLI Development Server with Docker

Source: https://upstash.com/docs/qstash/qstash/howto/local-development

Pulls the QStash CLI Docker image and runs the development server. The port is mapped to the host machine.

```bash
// Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

// Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev
```

--------------------------------

### GET /v2/messages/{messageId}

Source: https://upstash.com/docs/qstash/qstash/api/messages/get

Retrieves the details of a specific message using its unique ID. This endpoint is primarily for accessing messages currently being delivered or retried.

```APIDOC
## GET /v2/messages/{messageId}

### Description
Retrieves the details of a specific message using its unique ID. This endpoint is primarily for accessing messages currently being delivered or retried.

### Method
GET

### Endpoint
/v2/messages/{messageId}

### Parameters
#### Path Parameters
- **messageId** (string) - Required - The id of the message to retrieve.

### Request Example
```curl
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"
```

### Response
#### Success Response (200)
- **messageId** (string) - A unique identifier for this message.
- **topicName** (string) - The URL group (topic) name if this message was sent to a URL Group.
- **endpointName** (string) - The endpoint name of the message if the endpoint is given a name within the URL group.
- **url** (string) - The URL to which the message should be delivered.
- **method** (string) - The HTTP method to use for the message.
- **header** (Record<string, string[]>) - The HTTP headers sent to your API.
- **body** (string) - The body of the message if it is composed of utf8 chars only, empty otherwise.
- **bodyBase64** (string) - The base64 encoded body if the body contains a non-utf8 char only, empty otherwise.
- **maxRetries** (int) - The number of retries that should be attempted in case of delivery failure.
- **notBefore** (int) - The unix timestamp in milliseconds before which the message should not be delivered.
- **createdAt** (int) - The unix timestamp in milliseconds when the message was created.
- **callback** (string) - The url where we send a callback each time the message is attempted to be delivered.
- **failureCallback** (string) - The url where we send a callback to after the message is failed
- **scheduleId** (string) - The scheduleId of the message if the message is triggered by a schedule
- **callerIP** (string) - IP address of the publisher of this message.

#### Response Example
```json
{
  "messageId": "msg_123",
  "topicName": "myTopic",
  "url":"https://example.com",
  "method": "POST",
  "header": {
    "My-Header": ["my-value"]
  },
  "body": "{\"foo\":\"bar\"}",
  "createdAt": 1620000000000
}
```
```

--------------------------------

### Authenticate QStash API with Query Parameter using cURL

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This snippet provides an alternative authentication method for the QStash API, suitable for environments where setting HTTP headers is not feasible. It shows how to pass the QSTASH_TOKEN as a 'qstash_token' query parameter in the URL for cURL requests.

```APIDOC
## Authenticate QStash API with Query Parameter using cURL

### Description
Provides an alternative authentication method for the QStash API, suitable for environments where setting HTTP headers is not feasible. It shows how to pass the QSTASH_TOKEN as a 'qstash_token' query parameter in the URL for cURL requests.

### Method
GET

### Endpoint
`https://qstash.upstash.io/v2/publish/?qstash_token=<QSTASH_TOKEN>`

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```
```

--------------------------------

### Initialize Project Directory and File

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/python

Creates a new directory for the AWS Lambda project and an empty Python file for the handler function.

```bash
mkdir aws-lambda
cd aws-lambda
touch lambda_function.py
```

--------------------------------

### Enqueue JSON message with Anthropic API via QStash

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Enqueues a JSON message to a QStash queue for processing by the Anthropic API. It specifies the LLM model, messages, and a callback URL for results. Requires QStash and Anthropic tokens.

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

### QStash Callback Response Body Structure

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Defines the JSON structure of the payload sent by QStash to the specified callback URL. It includes details about the original message's status, headers, body, retry information, and metadata.

```APIDOC
## QStash Callback Response Structure

### Description
Defines the JSON structure of the payload sent by QStash to the specified callback URL. It includes details about the original message's status, headers, body (base64 encoded), retry information, and various metadata related to the source message.

### Response Body Structure
```json
{
  "status": 200,                                      // Response header
  "header": { "key": ["value"] },                  // Response header
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==",           // base64 encoded response body
  "retried": 2,                                       // How many times we retried to deliver the original message
  "maxRetries": 3,                                    // Number of retries before the message assumed to be failed to delivered.
  "sourceMessageId": "msg_xxx",                     // The ID of the message that triggered the callback
  "topicName": "myTopic",                           // The name of the URL Group (topic) if the request was part of a URL Group
  "endpointName": "myEndpoint",                     // The endpoint name if the endpoint is given a name within a topic
  "url": "http://myurl.com",                        // The destination url of the message that triggered the callback
  "method": "GET",                                  // The http method of the message that triggered the callback
  "sourceHeader": { "key": "value" }              // The http header of the message that triggered the callback
}
```
```

--------------------------------

### Get Flow Control Keys (curl)

Source: https://upstash.com/docs/qstash/qstash/api/flow-control/list

Retrieves the flow control keys and their corresponding wait list sizes from Upstash QStash. This API call requires an authorization token.

```curl
curl -X GET https://qstash.upstash.io/v2/flowControl/  -H "Authorization: Bearer <token>"
```

--------------------------------

### GET /v2/dlq/{dlqId}

Source: https://upstash.com/docs/qstash/qstash/api/dlq/getMessage

Retrieves a specific message from the Dead Letter Queue (DLQ) using its DLQ ID. If the message is not found, a 404 status code is returned.

```APIDOC
## GET /v2/dlq/{dlqId}

### Description
Retrieves a specific message from the Dead Letter Queue (DLQ) using its DLQ ID. If the message is not found, a 404 status code is returned.

### Method
GET

### Endpoint
/v2/dlq/{dlqId}

### Parameters
#### Path Parameters
- **dlqId** (string) - Required - The DLQ ID of the message you want to retrieve. This ID can be found when listing all messages in the DLQ or in the content of a failure callback.

### Request Example
```curl
curl -X GET https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"
```

### Response
#### Success Response (200)
- **messageId** (string) - A unique identifier for this message.
- **topicName** (string) - The URL Group (topic) name if this message was sent to a URL Group.
- **endpointName** (string) - The endpointName of the message if the endpoint is given a name within the URL Group.
- **url** (string) - The URL to which the message should be delivered.
- **method** (string) - The HTTP method to use for the message.
- **header** (Record<string, string[]>) - The HTTP headers sent to your API.
- **body** (string) - The body of the message if it is composed of utf8 chars only, empty otherwise.
- **bodyBase64** (string) - The base64 encoded body if the body contains a non-utf8 char only, empty otherwise.
- **maxRetries** (int) - The number of retries that should be attempted in case of delivery failure.
- **notBefore** (int) - The unix timestamp in milliseconds before which the message should not be delivered.
- **createdAt** (int) - The unix timestamp in milliseconds when the message was created.
- **callback** (string) - The url where we send a callback each time the message is attempted to be delivered.
- **failureCallback** (string) - The url where we send a callback to after the message is failed.
- **scheduleId** (string) - The scheduleId of the message if the message is triggered by a schedule.
- **callerIP** (string) - IP address of the publisher of this message.
- **dlqId** (string) - The unique id within the DLQ. Use this to remove the message from the DLQ DELETE /v2/dlq/{dlqId}
- **queueName** (string) - The name of the queue if this message is enqueued on a queue.
- **responseStatus** (int) - The http status code of the last failed deliver attempt.
- **responseHeader** (Record<string, string[]>) - The response header of the last failed deliver attempt.
- **responseBody** (string) - The response body of the last failed deliver attempt if it is composed of utf8 chars only, empty otherwise.
- **responseBodyBase64** (string) - The base64 encoded response body of the last failed deliver attempt if the response body contains a non-utf8 char only, empty otherwise.

#### Response Example
```json
{
  "messageId": "<string>",
  "topicName": "<string>",
  "endpointName": "<string>",
  "url": "<string>",
  "method": "<string>",
  "header": {},
  "body": "<string>",
  "bodyBase64": "<string>",
  "maxRetries": 123,
  "notBefore": 123,
  "createdAt": 123,
  "callback": "<string>",
  "failureCallback": "<string>",
  "scheduleId": "<string>",
  "callerIP": "<string>",
  "dlqId": "<string>",
  "queueName": "<string>",
  "responseStatus": 123,
  "responseHeader": [
    {}
  ],
  "responseBody": "<string>",
  "responseBodyBase64": "<string>"
}
```
```

--------------------------------

### View QStash Worker Logs with Wrangler

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

This example shows how to use the Wrangler CLI to tail logs from a Cloudflare Worker. It connects to the worker and displays incoming requests, including validation success messages.

```shell
$ npx wrangler tail

⛅️ wrangler 2.0.17
--------------------
Retrieving cached values for account from node_modules/.cache/wrangler
Successfully created tail, expires at 2022-07-11T21:11:36Z
Connected to cloudflare-workers, waiting for logs...
POST https://cloudflare-workers.upstash.workers.dev/ - Ok @ 7/11/2022, 5:13:19 PM
  (log) The signature was valid
```

--------------------------------

### Batch Messages cURL Request

Source: https://upstash.com/docs/qstash/qstash/api/messages/batch

This cURL command demonstrates a basic POST request to the Upstash QStash batch endpoint. It includes the authorization header required to authenticate the request. This is a foundational example for initiating a batch operation.

```curl
curl --request POST \
  --url https://qstash.upstash.io/v2/batch \
  --header 'Authorization: Bearer <token>'
```

--------------------------------

### Receive and Verify QStash Message (Next.js Route Handler)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/vercel-nextjs

Receives and verifies incoming QStash messages using `verifySignatureAppRouter`. It parses the JSON body to extract an image ID and performs image processing. Requires QStash integration for signature verification.

```typescript
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

### Schedule QStash Job via Dashboard (Configuration)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

Configuration details for setting up a QStash schedule through the dashboard. It specifies the endpoint URL, job type, and recurrence.

```text
URL: https://your-vercel-app.vercel.app/api
Type: Schedule
Every: every day at midnight (feel free to customize)

```

--------------------------------

### Send Single Email with QStash and Resend (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Demonstrates how to send a single email using the `qstash-js` SDK's `publishJSON` method with the Resend provider. It requires `QSTASH_TOKEN` and `RESEND_TOKEN` for authentication. The `body` field accepts standard Resend Send Email API parameters like `from`, `to`, `subject`, and `html`.

```APIDOC
## Send Single Email with QStash and Resend (TypeScript)

### Description
Demonstrates how to send a single email using the `qstash-js` SDK's `publishJSON` method with the Resend provider. It requires `QSTASH_TOKEN` and `RESEND_TOKEN` for authentication. The `body` field accepts standard Resend Send Email API parameters like `from`, `to`, `subject`, and `html`.

### Method
POST

### Endpoint
`/publishJSON` (SDK Method)

### Parameters
#### Request Body
- **api** (object) - Required - Configuration for the API integration.
  - **name** (string) - Required - The name of the API, e.g., "email".
  - **provider** (object) - Required - The provider configuration, e.g., `resend({ token: "<RESEND_TOKEN>" })`.
- **body** (object) - Required - The payload for the email, containing Resend parameters.
  - **from** (string) - Required - The sender's email address.
  - **to** (string[]) - Required - A list of recipient email addresses.
  - **subject** (string) - Required - The subject of the email.
  - **html** (string) - Required - The HTML content of the email.

### Request Example
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

### Response
#### Success Response (200)
- **messageId** (string) - The unique ID of the published message.
- **url** (string) - The URL associated with the message.

#### Response Example
```json
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```
```

--------------------------------

### Configure URL Group Headers via API

Source: https://upstash.com/docs/qstash/qstash/howto/webhook

Update a URL Group configuration using the QStash REST API to set default headers for all requests sent to that group. This example demonstrates setting `Upstash-Header-Forward` to `true` and `Upstash-Retries` to `3`.

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

### Chat Completion API Response Structure

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This APIDOC defines the JSON response object for the chat completion endpoint when streaming is disabled. It details the structure, including fields like `id`, `choices` (with `message`, `finish_reason`, `logprobs`), `created`, `model`, and `system_fingerprint`.

```APIDOC
Response:
  id: string - A unique identifier for the chat completion.
  choices: Object[] - A list of chat completion choices. Can be more than one if `n` is greater than `1`.
    message: Object - A chat completion message generated by the model.
      role: string - The role of the author of this message.
      content: string - The contents of the message.
    finish_reason: string - The reason the model stopped generating tokens. This will be `stop` if the model hit a natural stop point or a provided stop sequence, `length` if the maximum number of tokens specified in the request was reached.
    stop_reason: string - The stop string or token id that caused the completion to stop, null if the completion finished for some other reason including encountering the EOS token
    index: number - The index of the choice in the list of choices.
    logprobs: Object - Log probability information for the choice.
      content: Object[] - A list of message content tokens with log probability information.
        token: string - The token.
        logprob: number - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
        bytes: number[] - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
        top_logprobs: Object[] - List of the most likely tokens and their log probability, at this token position. In rare cases, there may be fewer than the number of requested `top_logprobs` returned.
          token: string - The token.
          logprob: number - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
          bytes: number[] - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
  created: number - The Unix timestamp (in seconds) of when the chat completion was created.
  model: string - The model used for the chat completion.
  system_fingerprint: string - This fingerprint represents the backend configuration that the model runs with. Can be used in conjunction with the `seed` request parameter to understand when backend changes have been made that might impact determinism.
```

--------------------------------

### Complete Batch Messages cURL Request with JSON Body

Source: https://upstash.com/docs/qstash/qstash/api/messages/batch

This comprehensive cURL example shows how to send a batch of messages to Upstash QStash. It includes the POST request to the `/v2/batch` endpoint, sets the Authorization and Content-Type headers, and provides a JSON array in the request body. The array contains multiple message objects, each with different destinations, headers, and bodies, illustrating flexible batching options.

```curl
curl -XPOST https://qstash.upstash.io/v2/batch   -H "Authorization: Bearer XXX" \
    -H "Content-Type: application/json" \
    -d '
    [
      {
          "destination": "myUrlGroup",
          "headers":{
            "Upstash-Delay":"5s",
            "Upstash-Forward-Hello":"123456"
          },
          "body": "Hello World"
      },
      {
          "queue": "test",
          "destination": "https://example.com/destination",
          "headers":{
            "Upstash-Forward-Hello":"789"
          }
      },
      {
          "destination": "https://example.com/destination1",
          "headers":{
            "Upstash-Delay":"7s",
            "Upstash-Forward-Hello":"789"
          }
      },
      {
          "destination": "https://example.com/destination2",
          "headers":{
            "Upstash-Delay":"9s",
            "Upstash-Forward-Hello":"again"
          }
      }
    ]'


```

--------------------------------

### Chat Completion API Response Object Definition

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

Defines the structure of the JSON response returned by the chat completion endpoint, including nested objects for choices, messages, log probabilities, and usage statistics. This structure is returned when the `stream` parameter is `false` or not set.

```APIDOC
## Chat Completion API Response Object Definition

### Description
Defines the structure of the JSON response returned by the chat completion endpoint, including nested objects for choices, messages, log probabilities, and usage statistics. This structure is returned when the `stream` parameter is `false` or not set.

### Method
POST

### Endpoint
`/v1/chat/completions` (Assumed, based on context)

### Parameters
#### Query Parameters
- **stream** (boolean) - Optional - If set to `true`, streams message chunks like Server-Sent Events.

#### Request Body
(Details not provided in the input, but typically includes `model`, `messages`, `temperature`, `max_tokens`, etc.)

### Request Example
(Not provided in the input)

### Response
#### Success Response (200)
- **id** (string) - A unique identifier for the chat completion.
- **choices** (Object[]) - A list of chat completion choices. Can be more than one if `n` is greater than `1`.
  - **message** (object) - A chat completion message generated by the model.
    - **role** (string) - The role of the author of this message.
    - **content** (string) - The contents of the message.
  - **finish_reason** (string) - The reason the model stopped generating tokens. This will be `stop` if the model hit a natural stop point or a provided stop sequence, `length` if the maximum number of tokens specified in the request was reached.
  - **stop_reason** (string) - The stop string or token id that caused the completion to stop, null if the completion finished for some other reason including encountering the EOS token.
  - **index** (number) - The index of the choice in the list of choices.
  - **logprobs** (object) - Log probability information for the choice.
    - **content** (object[]) - A list of message content tokens with log probability information.
      - **token** (string) - The token.
      - **logprob** (number) - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
      - **bytes** (number[]) - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
      - **top_logprobs** (object[]) - List of the most likely tokens and their log probability, at this token position. In rare cases, there may be fewer than the number of requested `top_logprobs` returned.
        - **token** (string) - The token.
        - **logprob** (number) - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
        - **bytes** (number[]) - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
- **created** (number) - The Unix timestamp (in seconds) of when the chat completion was created.
- **model** (string) - The model used for the chat completion.
- **system_fingerprint** (string) - This fingerprint represents the backend configuration that the model runs with. Can be used in conjunction with the `seed` request parameter to understand when backend changes have been made that might impact determinism.

#### Response Example
```json
{
  "id": "chatcmpl-123",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Hello! How can I help you today?"
      },
      "finish_reason": "stop",
      "index": 0,
      "logprobs": null
    }
  ],
  "created": 1677652288,
  "model": "gpt-3.5-turbo-0613",
  "system_fingerprint": "fp_abc123"
}
```
```

--------------------------------

### Verify QStash Webhook Signature (Python)

Source: https://upstash.com/docs/qstash/qstash/overall/llms-txt

This Python function verifies the signature of an incoming QStash webhook. It decodes the JWT from the 'upstash-signature' header, validates its structure and claims (issuer, subject, expiration), verifies the signature using HMAC-SHA256, and optionally checks the body hash. It requires the JWT token, a signing key, and the raw request body as input. Failures in any of these steps will raise an exception.

```python
# @param jwt_token - The content of the `upstash-signature` header
# @param signing_key - The signing key to use to verify the signature (Get it from Upstash Console)
# @param body - The raw body of the request

```

--------------------------------

### Batch Messages API Response Example

Source: https://upstash.com/docs/qstash/qstash/api/messages/batch

This JSON snippet represents a typical response from the Upstash QStash batch messages endpoint. It shows an array where each element corresponds to a batch or a single message sent. Each item may contain a 'messageId' and 'url' for successful deliveries or indicate errors for failed ones.

```json
[
  [
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint1.com"
    },
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint2.com"
    }
  ],
  {
    "messageId": "msg_...",
  },
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]


```

--------------------------------

### List All Schedules

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

List all schedules that have been created.

```APIDOC
## GET /v2/schedules

### Description
List all schedules that have been created.

### Method
GET

### Endpoint
/v2/schedules

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.

### Response
#### Success Response (200)
- **schedules** (array) - An array of schedule objects.
  - **scheduleId** (string) - The ID of the schedule.
  - **cronExpression** (string) - The cron expression for the schedule.
  - **url** (string) - The URL the schedule publishes to.

#### Response Example
```json
{
  "schedules": [
    {
      "scheduleId": "sch_abcde",
      "cronExpression": "* * * * *",
      "url": "https://example.com/task"
    }
  ]
}
```
```

--------------------------------

### Configuring Callbacks with Headers

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

Explains how to configure various callback and failure callback settings using specific `Upstash-` prefixed headers.

```APIDOC
## Configuring Callbacks with Headers

### Description
This section outlines the HTTP headers used to configure callback and failure callback behavior, including timeouts, retries, delays, and HTTP methods. It also shows how to forward custom headers.

### Method
N/A (Describes header configurations for API requests)

### Endpoint
N/A

### Parameters
#### Callback Configuration Headers
- **Upstash-Callback-Timeout** (integer) - Timeout for callback requests.
- **Upstash-Callback-Retries** (integer) - Number of retries for callback requests.
- **Upstash-Callback-Delay** (integer) - Delay between callback retries (in seconds).
- **Upstash-Callback-Method** (string) - HTTP method for callback requests (e.g., GET, POST).

#### Failure Callback Configuration Headers
- **Upstash-Failure-Callback-Timeout** (integer) - Timeout for failure callback requests.
- **Upstash-Failure-Callback-Retries** (integer) - Number of retries for failure callback requests.
- **Upstash-Failure-Callback-Delay** (integer) - Delay between failure callback retries (in seconds).
- **Upstash-Failure-Callback-Method** (string) - HTTP method for failure callback requests (e.g., GET, POST).

#### Forwarding Custom Headers
- **Upstash-Callback-Forward-[Header-Name]** (string) - Forwards a custom header to the callback endpoint.
- **Upstash-Failure-Callback-Forward-[Header-Name]** (string) - Forwards a custom header to the failure callback endpoint.

### Example Usage
(These headers would be included in the request when publishing a message to configure its associated callbacks.)
```

--------------------------------

### Trigger Pipedream Workflow from QStash Endpoint Message

Source: https://upstash.com/docs/qstash/qstash/integrations/pipedream

This guide outlines the process of triggering a Pipedream workflow via an HTTP endpoint, specifically designed to receive messages from QStash. It emphasizes configuring the HTTP trigger to return a custom response and handle the event body as raw data for QStash webhook verification. The QStash Verify Webhook action is used to ensure the authenticity of incoming requests.

```Pipedream
steps.trigger.event
```

```Node.js
$.respond(
  {
    status: 200,
    body: "OK"
  }
);
```

--------------------------------

### Golang: Main HTTP Server for QStash Webhooks

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

Sets up an HTTP server in Go to listen for incoming requests on a port defined by the PORT environment variable or defaulting to 8080. It defines a handler function to process incoming webhooks, read the request body, and attempt signature verification.

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

### Configure ngrok Authentication

Source: https://upstash.com/docs/qstash/qstash/howto/local-tunnel

Configures the ngrok CLI with your authentication token, obtained from the ngrok dashboard. This is necessary to connect your local ngrok agent to your ngrok account.

```bash
ngrok config add-authtoken XXX
```

--------------------------------

### List All Schedules with cURL

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

Provides a cURL command to list all schedules managed by QStash. An Authorization header is necessary for authentication.

```shell
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer XXX"
```

--------------------------------

### Publish Message using cURL

Source: https://upstash.com/docs/qstash/qstash/overall/getstarted

Demonstrates how to publish a message to QStash using a cURL command. This involves setting the authorization token, content type, and the message payload. It requires a publicly available HTTP API endpoint and a QStash token.

```cURL
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://<your-api-url>'
```

--------------------------------

### Golang: Import necessary packages

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

Imports required Go packages for handling HTTP requests, crypto operations, JWT parsing, and environment variable access. These are essential for creating the webhook receiver.

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

### Fly.io: Setting environment secrets

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

Shows how to set environment variables, specifically the QStash signing keys, for a fly.io application using the `flyctl secrets set` command. This is crucial for the application to securely verify incoming webhook signatures.

```bash
flyctl secrets set QSTASH_CURRENT_SIGNING_KEY=...
flyctl secrets set QSTASH_NEXT_SIGNING_KEY=...

```

--------------------------------

### QStash Message Delivery Overview

Source: https://upstash.com/docs/qstash/qstash/howto/receiving

This section details how QStash delivers messages to your webhook endpoint. It covers the headers that are forwarded and the structure of the message body.

```APIDOC
## QStash Message Delivery

### Description
When a message is published, QStash delivers it to your chosen destination API endpoint. This documentation outlines the structure of the request your API will receive.

### Headers
QStash forwards headers prefixed with `Upstash-Forward-` to your API. Additionally, the following standard headers are included:

- `User-Agent`: Set to `Upstash-QStash`.
- `Content-Type`: The original `Content-Type` header of the published message.
- `Upstash-Topic-Name`: The URL Group (topic) name, if applicable.
- `Upstash-Signature`: A signature for verifying the message's origin. Refer to the verification documentation for details.
- `Upstash-Retried`: Indicates the number of times the message has been retried (starts at 0).
- `Upstash-Message-Id`: The unique identifier for the message.
- `Upstash-Schedule-Id`: The identifier for the schedule, if the message is part of a schedule.
- `Upstash-Caller-Ip`: The IP address of the entity that published the message.

### Body
The message body is delivered exactly as it was published, without any modifications. If the original message had a JSON body, your API will receive a JSON body. If it was a string, your API will receive a string.
```

--------------------------------

### Publishing a Message with Callback

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

This section demonstrates how to publish a message to QStash and specify a callback URL using the `Upstash-Callback` header.

```APIDOC
## POST /v2/publish/:destination

### Description
Publishes a message to a specified destination and uses a callback URL to receive the response asynchronously.

### Method
POST

### Endpoint
`/v2/publish/:destination`

### Parameters
#### Path Parameters
- **destination** (string) - Required - The URL to which the message will be delivered.

#### Headers
- **Content-Type**: `application/json` - Required
- **Authorization**: `Bearer <QSTASH_TOKEN>` - Required - Your QStash authentication token.
- **Upstash-Callback**: `<CALLBACK_URL>` - Required - The URL to which QStash will send the response.

#### Request Body
- **body** (object) - Required - The content of the message to be published.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
- **message** (string) - Indicates that the message has been published successfully.

#### Response Example
```json
{
  "message": "Message published successfully."
}
```
```

--------------------------------

### Publish Message with Callback URL (cURL)

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

This cURL command demonstrates how to publish a message to QStash with a specified callback URL. It includes setting the content type, authorization, and the crucial `Upstash-Callback` header.

```shell
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api... \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

--------------------------------

### Set Callback URL with cURL

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

Demonstrates how to publish a message and specify callback URLs for success and failure using cURL. Requires an authorization token and a JSON payload.

```shell
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

--------------------------------

### Deploy AWS CDK Application

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

Command to deploy AWS CDK stack. This command initiates the deployment process to AWS, creating or updating resources defined in the CDK application. It might prompt for AWS permissions confirmation.

```bash
cdk deploy
```

--------------------------------

### Deno Webhook Handler with QStash Signature Verification

Source: https://upstash.com/docs/qstash/qstash/quickstarts/deno-deploy

This Deno code snippet sets up an HTTP server to receive webhooks. It uses the Upstash QStash SDK to verify the incoming webhook's signature using signing keys stored as environment variables. The handler logs whether the signature is valid and returns an appropriate response.

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

### Integrating Helicone for LLM Analytics

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Explains how to integrate Helicone for observability of LLM API usage within QStash by providing the Helicone API key during model initialization.

```APIDOC
## POST /v1/publish (with Helicone Analytics)

### Description
Publishes an LLM request with Helicone analytics enabled for observability.

### Method
POST

### Endpoint
/v1/publish

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API details and analytics integration.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Details of the LLM provider.
    - **token** (string) - Required - API token for the LLM provider.
    - **baseUrl** (string) - Optional - Base URL for custom LLM providers.
  - **analytics** (object) - Optional - Configuration for analytics integration.
    - **name** (string) - Required - The name of the analytics provider, e.g., 'helicone'.
    - **token** (string) - Required - API token for the analytics provider.
- **body** (object) - Required - The chat completion request payload.
  - **model** (string) - Required - The LLM model to use.
  - **messages** (array) - Required - An array of message objects for the chat conversation.
- **callback** (string) - Optional - URL to receive asynchronous responses.

### Request Example
```json
{
  "api": {
    "name": "llm",
    "provider": {
      "token": "XXX",
      "baseUrl": "https://api.together.xyz"
    },
    "analytics": {
      "name": "helicone",
      "token": "process.env.HELICONE_API_KEY!"
    }
  },
  "body": {
    "model": "meta-llama/Llama-3-8b-chat-hf",
    "messages": [
      {
        "role": "user",
        "content": "hello"
      }
    ]
  },
  "callback": "https://oz.requestcatcher.com/"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.
- ** 202** (integer) - Indicates the request was accepted for processing.

#### Response Example
```json
{
    "messageId": "msg-ccccccccccccccccccc"
}
```
```

--------------------------------

### Python Script to Delete All Redis Keys (Python)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/python-vercel

A Python script that connects to Upstash Redis and deletes all existing keys. It requires the 'upstash_redis' package and the Redis URL and token.

```python
from upstash_redis import Redis

redis = Redis(url="https://YOUR_REDIS_URL", token="YOUR_TOKEN")

def delete_all_entries():
  keys = redis.keys("*") # Match all keys
  redis.delete(*keys)


delete_all_entries()

```

--------------------------------

### Lambda Build and Zip Script (package.json)

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/nodejs

Defines scripts in package.json for building and zipping the Lambda function code using esbuild. It cleans the dist directory, bundles and minifies the code, and creates a zip archive suitable for AWS Lambda deployment.

```json
{
  "scripts": {
    "build": "rm -rf ./dist; esbuild index.ts --bundle --minify --sourcemap --platform=node --target=es2020 --outfile=dist/index.js && cd dist && zip -r index.zip index.js*"
  }
}
```

--------------------------------

### Verify QStash Request Signature using TypeScript SDK

Source: https://upstash.com/docs/qstash/qstash/howto/signature

This code snippet demonstrates how to use the QStash TypeScript SDK's `Receiver` to verify the signature of an incoming request. It requires your current and next signing keys, the request body, the signature from the header, and your site's URL.

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

### List Upstash QStash Queues (cURL)

Source: https://upstash.com/docs/qstash/qstash/api/queues/list

Demonstrates how to retrieve a list of all queues in Upstash QStash using a cURL command. Requires an API token for authorization.

```curl
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"
```

--------------------------------

### Publish Message to QStash using cURL

Source: https://upstash.com/docs/qstash/qstash/quickstarts/deno-deploy

This cURL command demonstrates how to publish a JSON message to a specific Deno deploy endpoint using QStash. It includes the necessary POST request, endpoint URL, authorization header with a QStash token, and the JSON payload.

```bash
curl --request POST "https://qstash.upstash.io/v2/publish/https://early-frog-33.deno.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### Next.js API Route for Cron Job

Source: https://upstash.com/docs/qstash/qstash/recipes/periodic-data-updates

A Next.js serverless function that fetches Bitcoin price data from a public API and stores it in Redis using ZADD. It uses QStash's `verifySignature` to ensure request authenticity.

```typescript
import { NextApiRequest, NextApiResponse } from "next";
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

### Publish with Rate Limit

Source: https://upstash.com/docs/qstash/qstash/features/flowcontrol

This snippet demonstrates how to publish a JSON message with a specified rate limit using the QStash client. It configures a rate of 10 calls per minute, controlled by a unique key.

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, period: "1m" },
});
```

--------------------------------

### Configuring Failure Callback Headers

Source: https://upstash.com/docs/qstash/qstash/api/schedules/create

This section details how to configure failure callback requests using headers with the `Upstash-Failure-Callback-` prefix.

```APIDOC
## Configuring Failure Callback Headers

### Description
Configure the timeout duration, number of retries, delay, and other settings for failure callback requests using headers prefixed with `Upstash-Failure-Callback-`.

### Method
POST, PUT (Implied by context of setting configurations)

### Endpoint
/websites/upstash-qstash (Implied base endpoint)

### Headers
- **Upstash-Failure-Callback-Forward-"{Header-Name}"** (string) - Optional - Specifies headers to be forwarded along with the failure callback request. The prefix `Upstash-Failure-Callback-Forward-` is stripped, and the rest of the header name is forwarded. For example, `Upstash-Failure-Callback-Forward-My-Header: my-value` results in `My-Header: my-value` being sent.

### Request Example
```json
{
  "Upstash-Failure-Callback-Forward-Authorization": "Bearer your-token",
  "Upstash-Failure-Callback-Timeout": "60s"
}
```

### Response
(No specific response details provided for header configuration itself, assumes success if request is processed.)

```

--------------------------------

### Initialize and Use QStash Receiver

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Initializes a new `Receiver` instance with the provided signing keys from the environment variables. It then demonstrates how to verify the signature of an incoming request using the `verify` method, which requires the request's signature header and body.

```typescript
const receiver = new Receiver({
  currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
  nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
})

```

```typescript
const body = await request.text()

const isValid = await receiver.verify({
  signature: request.headers.get("Upstash-Signature")!,
  body,
})

```

--------------------------------

### List Logs

Source: https://upstash.com/docs/qstash/qstash/api/events/list

Retrieves a list of logs for messages. Supports pagination using a cursor.

```APIDOC
## GET /websites/upstash-qstash/logs

### Description
Retrieves a list of logs for messages. Supports pagination using a cursor.

### Method
GET

### Endpoint
/websites/upstash-qstash/logs

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - A cursor which you can use in subsequent requests to paginate through all events. If no cursor is returned, you have reached the end of the events.

### Response
#### Success Response (200)
- **cursor** (string) - A cursor which you can use in subsequent requests to paginate through all events. If no cursor is returned, you have reached the end of the events.
- **events** (array) - An array of log entries.
  - **time** (int) - Timestamp of this log entry, in milliseconds
  - **messageId** (string) - The associated message id
  - **header** (Record<string, string[]>) - The headers of the message.
  - **body** (string) - Base64 encoded body of the message.
  - **state** (string) - The current state of the message at this point in time. Possible values: CREATED, ACTIVE, RETRY, ERROR, DELIVERED, FAILED, CANCEL_REQUESTED, CANCELLED.
  - **error** (string) - An explanation what went wrong
  - **nextDeliveryTime** (int) - The next scheduled time of the message. (Unix timestamp in milliseconds)
  - **url** (string) - The destination url
  - **topicName** (string) - The name of the URL Group (topic) if this message was sent through a topic
  - **endpointName** (string) - The name of the endpoint if this message was sent through a URL Group
  - **scheduleId** (string) - The scheduleId of the message if the message is triggered by a schedule
  - **queueName** (string) - The name of the queue if this message is enqueued on a queue
  - **header** (string) - The headers that are forwarded to the users endpoint
  - **body** (string) - Base64 encoded body of the message
  - **responseStatus** (int) - The status code of the response. Only set if the state is `ERROR`
  - **responseBody** (string) - The base64 encoded body of the response. Only set if the state is `ERROR`
  - **responseHeaders** (Record<string, string[]>) - The headers of the response. Only set if the state is `ERROR`
  - **timeout** (int) - The timeout (in milliseconds) of the outgoing http requests, after which Qstash cancels the request
  - **method** (string) - Method is the HTTP method of the message for outgoing request
  - **callback** (string) - Callback is the URL address where QStash sends the response of a publish
  - **callbackHeaders** (Record<string, string[]>) - The headers that are passed to the callback url
  - **failureCallback** (string) - Failure Callback is the URL address where QStash sends the response of a publish
  - **failureCallbackHeaders** (Record<string, string[]>) - The headers that are passed to the failure callback url
  - **maxRetries** (int) - The number of retries that should be attempted in case of delivery failure
  - **retryDelayExpression** (string) - The mathematical expression used to calculate delay between retry attempts. If not set, the default backoff is used.

#### Response Example
{
  "cursor": "eyJmZXRjaGVkQXQiOjE2NzgyNjc4OTAwMDB9",
  "events": [
    {
      "time": 1678267890000,
      "messageId": "msg_abc123",
      "header": {
        "Content-Type": ["application/json"]
      },
      "body": "eyJoZWxsbyI6ICJ3b3JsZCJ9",
      "state": "DELIVERED",
      "error": null,
      "nextDeliveryTime": null,
      "url": "https://example.com/webhook",
      "topicName": "my-topic",
      "endpointName": "endpoint-xyz",
      "scheduleId": null,
      "queueName": null,
      "responseStatus": null,
      "responseBody": null,
      "responseHeaders": null,
      "timeout": 5000,
      "method": "POST",
      "callback": "https://my-callback.com/success",
      "callbackHeaders": {
        "X-Callback-Header": ["value1"]
      },
      "failureCallback": "https://my-callback.com/failure",
      "failureCallbackHeaders": {
        "X-Failure-Callback-Header": ["value2"]
      },
      "maxRetries": 3,
      "retryDelayExpression": "5s"
    }
  ]
}
```

--------------------------------

### POST /websites/upstash-qstash

Source: https://upstash.com/docs/qstash/qstash/api/enqueue

Send a message to a QStash queue. The queue will be created if it does not exist. Various headers can customize delivery, retries, and callbacks.

```APIDOC
## POST /websites/upstash-qstash

### Description
Send a message to a QStash queue. The queue will be created if it does not exist. Various headers can customize delivery, retries, and callbacks.

### Method
POST

### Endpoint
/websites/upstash-qstash

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **queueName** (string) - Required - The name of the queue that message will be enqueued on. If doesn’t exist, it will be created automatically.
- **destination** (string) - Required - Destination can either be a topic name or id that you configured in the Upstash console, a valid url where the message gets sent to, or a valid QStash API name like `api/llm`. If the destination is a URL, make sure the URL is prefixed with a valid protocol (`http://` or `https://`).
- **body** (string) - Optional - The raw request message passed to the endpoints as is.

#### Headers
- **Content-Type** (string) - Optional - ContentType is the MIME type of the message. We highly recommend sending a `Content-Type` header along, as this will help your destination API to understand the content of the message. Set this to whatever data you are sending through QStash, if your message is json, then use `application/json`.
- **Upstash-Method** (string) - Optional - The HTTP method to use when sending a webhook to your API. Defaults to "POST".
- **Upstash-Timeout** (string) - Optional - Timeout value to set how long your endpoint is going to take. Examples: `"1s"`, `"5m"`, `"2h"`.
- **Upstash-Retries** (int) - Optional - How often should this message be retried in case the destination API is not available. Defaults to 3.
- **Upstash-Retry-Delay** (string) - Optional - Customize the delay between retry attempts. Supports mathematical expressions using the variable `retried`. Examples: `"1000"`, `"1000 * (1 + retried)"`, `"pow(2, retried) * 1000"`.
- **Upstash-Forward-*** (string) - Optional - Send custom headers by prefixing the header name with `Upstash-Forward-`. Example: `Upstash-Forward-My-Header: my-value`.
- **Upstash-Callback** (string) - Optional - Define a callback URL that will be called after each attempt. For the `api/llm` destination, specifying a callback is required.
- **Upstash-Callback-*** (string) - Optional - Configure callback request parameters like timeout, retries, and delay using this prefix.
- **Upstash-Callback-Forward-*** (string) - Optional - Specify headers for the callback request using this prefix. Example: `Upstash-Callback-Forward-My-Header: my-value`.
- **Upstash-Failure-Callback** (string) - Optional - Define a failure callback URL that will be called when a delivery fails after all retries are exhausted.
- **Upstash-Failure-Callback-*** (string) - Optional - Configure failure callback request parameters like timeout, retries, and delay using this prefix.
- **Upstash-Failure-Callback-Forward-*** (string) - Optional - Specify headers for the failure callback request using this prefix.

### Request Example
```json
{
  "queueName": "my-queue",
  "destination": "https://example.com/webhook",
  "body": "{\"message\": \"Hello QStash!\"}"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the sent message.

#### Response Example
```json
{
  "messageId": "msg_abcdef1234567890"
}
```
```

--------------------------------

### List Queues in Upstash QStash (curl)

Source: https://upstash.com/docs/qstash/qstash/api/queues/get

This snippet demonstrates how to list queues in Upstash QStash using a curl command. It requires an authorization token for authentication. The response includes details about the queues, such as their names, creation and update times, parallelism, and lag.

```curl
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"
```

--------------------------------

### Create a Queue using cURL

Source: https://upstash.com/docs/qstash/qstash/api/queues/upsert

This snippet demonstrates how to create a new queue in Upstash QStash using a cURL command. It requires an authorization token and specifies the queue name and parallelism settings. The API returns a 200 status on success or a 412 if the queue limit is exceeded.

```curl
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue" , 
    "parallelism" : 5,
  }'
```

--------------------------------

### Publish Message with Callback

Source: https://upstash.com/docs/qstash/qstash/overall/apiexamples

Publish a message to a specific endpoint and optionally provide callback URLs for success and failure.

```APIDOC
## POST /v2/publish/:url

### Description
Receive a response from the endpoint and send it to the specified callback URL. If the endpoint does not return a response, QStash will send it to the failure callback URL.

### Method
POST

### Endpoint
/v2/publish/:url

### Parameters
#### Header Parameters
- **Authorization** (string) - Required - Bearer token for authentication.
- **Upstash-Callback** (string) - Optional - The URL to send the response to on success.
- **Upstash-Failure-Callback** (string) - Optional - The URL to send the response to on failure.

#### Request Body
- **body** (object) - Required - The message payload to send.

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
  "messageId": "msg_12345"
}
```
```

--------------------------------

### URL Group Configuration

Source: https://upstash.com/docs/qstash/qstash/howto/webhook

URL Groups allow server-side templating for publishing messages. You can define default headers and multiple endpoints within a group to fan-out webhook calls to various destinations.

```APIDOC
## PATCH /v2/topics/<URL_GROUP_NAME>

### Description
Update the configuration for a specific URL Group, including default headers and forwarding settings.

### Method
PATCH

### Endpoint
`/v2/topics/<URL_GROUP_NAME>`

### Parameters
#### Path Parameters
- **URL_GROUP_NAME** (string) - Required - The name of the URL Group to update.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.

#### Request Body
- **headers** (object) - Optional - A map of headers to set as defaults for the URL Group.
  - **Upstash-Header-Forward** (array of strings) - Optional - Set to `["true"]` to forward all headers.
  - **Upstash-Retries** (string) - Optional - Default number of retries for requests in this group.
- **endpoints** (array of objects) - Optional - A list of webhook endpoints associated with this group.
  - **url** (string) - Required - The URL of the endpoint.

### Request Example
```json
{
  "headers": {
    "Upstash-Header-Forward": ["true"],
    "Upstash-Retries": "3"
  },
  "endpoints": [
    {
      "url": "https://example.com/api/webhook"
    }
  ]
}
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message of the update.

#### Response Example
```json
{
  "message": "URL Group updated successfully"
}
```
```

```APIDOC
## POST /v2/publish/<URL_GROUP_NAME>

### Description
Publish a message to all endpoints configured within a specific URL Group.

### Method
POST

### Endpoint
`/v2/publish/<URL_GROUP_NAME>`

### Parameters
#### Path Parameters
- **URL_GROUP_NAME** (string) - Required - The name of the URL Group to publish to.

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.

#### Request Body
- **body** (object) - Required - The payload to send to the webhook endpoints.

### Request Example
```json
{
  "body": {
    "event": "user_created",
    "userId": "user-123"
  }
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message batch.

#### Response Example
```json
{
  "messageId": "msg_batch_xyz789"
}
```
```

--------------------------------

### List Events

Source: https://upstash.com/docs/qstash/qstash/api/logs/list

Retrieves a list of events with pagination support. Each event contains detailed information about a message's lifecycle.

```APIDOC
## GET /websites/upstash-qstash/events

### Description
Retrieves a paginated list of events. The `cursor` parameter is used for subsequent requests to fetch more logs.

### Method
GET

### Endpoint
/websites/upstash-qstash/events

### Parameters
#### Query Parameters
- **cursor** (string) - Optional - A cursor for pagination. If omitted, the first page of logs is returned.

### Response
#### Success Response (200)
- **cursor** (string) - A cursor for the next page of results. Absent if this is the last page.
- **events** (Array) - An array of event objects.
  - **time** (int) - Required - Timestamp of the log entry in milliseconds.
  - **messageId** (string) - Required - The ID of the associated message.
  - **header** (Record<string, string[]>) - Required - Headers of the message.
  - **body** (string) - Required - Base64 encoded body of the message.
  - **state** (string) - Required - The current state of the message. Possible values: `CREATED`, `ACTIVE`, `RETRY`, `ERROR`, `DELIVERED`, `FAILED`, `CANCEL_REQUESTED`, `CANCELLED`.
  - **error** (string) - An explanation of any error that occurred.
  - **nextDeliveryTime** (int) - The next scheduled delivery time in milliseconds (Unix timestamp).
  - **url** (string) - The destination URL for the message.
  - **topicName** (string) - The name of the topic if the message was sent via a topic.
  - **endpointName** (string) - The name of the endpoint if the message was sent via a URL group.
  - **scheduleId** (string) - The ID of the schedule if the message was triggered by a schedule.
  - **queueName** (string) - The name of the queue if the message was enqueued.
  - **header** (string) - Headers forwarded to the user's endpoint.
  - **body** (string) - Base64 encoded body of the message.
  - **responseStatus** (int) - The HTTP status code of the response (only if state is `ERROR`).
  - **responseBody** (string) - Base64 encoded response body (only if state is `ERROR`).
  - **responseHeaders** (Record<string, string[]>) - Headers of the response (only if state is `ERROR`).
  - **timeout** (int) - Timeout in milliseconds for outgoing HTTP requests.
  - **method** (string) - The HTTP method for the outgoing request.
  - **callback** (string) - The URL for sending publish response callbacks.
  - **callbackHeaders** (Record<string, string[]>) - Headers passed to the callback URL.
  - **failureCallback** (string) - The URL for sending failure callbacks.
  - **failureCallbackHeaders** (Record<string, string[]>) - Headers passed to the failure callback URL.
  - **maxRetries** (int) - The maximum number of retries for delivery failure.
  - **retryDelayExpression** (string) - Mathematical expression to calculate retry delay.
  - **label** (string) - A label assigned to the message by the user.

#### Response Example
{
  "cursor": "some-cursor-string",
  "events": [
    {
      "time": 1678886400000,
      "messageId": "msg-123",
      "header": {
        "Content-Type": ["application/json"]
      },
      "body": "eyJoZWxsbyI6IndvcmxkIn0=",
      "state": "DELIVERED",
      "url": "https://example.com/webhook",
      "method": "POST",
      "topicName": "my-topic",
      "queueName": "my-queue",
      "maxRetries": 3,
      "label": "test-message"
    }
  ]
}
```

--------------------------------

### Publish Message to QStash using cURL

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

This snippet shows how to publish a JSON message to a specified URL using QStash. It requires the destination URL, your QStash token for authorization, and the message content in JSON format. The destination URL is typically your application's public URL on platforms like fly.io.

```shell
curl --request POST "https://qstash.upstash.io/v2/publish/https://winter-cherry-9545.fly.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

### Sending Chat Completion Requests in Batches

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Illustrates how to send multiple chat completion requests in a single batch operation, optimizing throughput for LLM API calls.

```APIDOC
## POST /v1/batch

### Description
Sends multiple LLM chat completion requests in a single batch.

### Method
POST

### Endpoint
/v1/batch

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **batch** (array) - Required - An array of message objects, each containing API and body details for an LLM request.
  - Each object in the array should have:
    - **api** (object) - Required - Specifies the LLM API details.
      - **name** (string) - Required - Must be 'llm'.
      - **provider** (object) - Required - Details of the LLM provider.
        - **token** (string) - Required - API token for the LLM provider.
    - **body** (object) - Required - The chat completion request payload.
    - **callback** (string) - Optional - URL to receive asynchronous responses.

### Request Example
```json
[
    {
        "api": {
            "name": "llm",
            "provider": {
                "openai": {
                    "token": "_OPEN_AI_TOKEN_"
                }
            }
        },
        "body": {
            "model": "gpt-3.5-turbo",
            "messages": [
                {
                    "role": "user",
                    "content": "Hello"
                }
            ]
        },
        "callback": "https://abc.requestcatcher.com"
    },
    {
        "api": {
            "name": "llm",
            "provider": {
                "openai": {
                    "token": "_OPEN_AI_TOKEN_"
                }
            }
        },
        "body": {
            "model": "gpt-3.5-turbo",
            "messages": [
                {
                    "role": "user",
                    "content": "Hi there"
                }
            ]
        },
        "callback": "https://abc.requestcatcher.com"
    }
]
```

### Response
#### Success Response (200)
- **results** (array) - An array containing the results for each batch item.
  - Each object in the array may contain:
    - **messageId** (string) - The ID of the processed message.
    - **status** (string) - Status of the batch item processing.

#### Response Example
```json
{
    "results": [
        {
            "messageId": "msg-aaaaaaaaaaaaaaa",
            "status": "published"
        },
        {
            "messageId": "msg-bbbbbbbbbbbbbbb",
            "status": "published"
        }
    ]
}
```
```

--------------------------------

### Publish with Rate, Parallelism, and Period

Source: https://upstash.com/docs/qstash/qstash/features/flowcontrol

This snippet illustrates publishing a JSON message with combined flow control parameters: rate, parallelism, and period. It sets a rate of 10 calls per minute, a parallelism limit of 20, and a period of 1 minute.

```typescript
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, parallelism: 20, period: "1m" },
});
```

--------------------------------

### Batch Publish with Headers and Body

Source: https://upstash.com/docs/qstash/qstash/features/batch

Construct batch requests with custom headers and bodies for each message. This enables fine-grained control over message content and delivery parameters, such as delays.

```cURL
curl -XPOST https://qstash.upstash.io/v2/batch   -H "Authorization: Bearer XXX" \
    -H "Content-Type: application/json" \
    -d ' \
    [ \
      {
          "destination": "myUrlGroup",
          "headers":{
            "Upstash-Delay":"5s",
            "Upstash-Forward-Hello":"123456"
          },
          "body": "Hello World"
      },
      {
          "destination": "https://example.com/destination1",
          "headers":{
            "Upstash-Delay":"7s",
            "Upstash-Forward-Hello":"789"
          }
      },
      {
          "destination": "https://example.com/destination2",
          "headers":{
            "Upstash-Delay":"9s",
            "Upstash-Forward-Hello":"again"
          }
      }
    ]'

```

--------------------------------

### Handle QStash Callback in Next.js

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

This Next.js API route handler demonstrates how to receive and process a QStash callback. It includes decoding the base64-encoded response body and uses `@upstash/qstash/nextjs` to verify the signature, ensuring the callback's authenticity.

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

### Publish Webhook

Source: https://upstash.com/docs/qstash/qstash/howto/webhook

Configure your webhook URL as a QStash publish request. You can specify request configurations like retries and timeouts using HTTP headers or query parameters. Headers prefixed with `Upstash-Forward-` are forwarded by default, or you can enable forwarding of all headers with `Upstash-Header-Forward: true`.

```APIDOC
## POST /v2/publish/<WEBHOOK_URL>

### Description
Publish a message to a specific webhook URL via QStash.

### Method
POST

### Endpoint
`/v2/publish/<WEBHOOK_URL>`

### Parameters
#### Query Parameters
- **qstash_token** (string) - Required - Your QStash token.
- **upstash-retries** (integer) - Optional - Number of retries for the request.
- **upstash-delay** (string) - Optional - Delay before retrying (e.g., '100s').
- **upstash-header-forward** (boolean) - Optional - Set to `true` to forward all incoming request headers.

#### Request Body
- **body** (object) - Required - The payload to send to the webhook.

### Request Example
```json
{
  "body": {
    "message": "Hello from QStash!"
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

### Configuring Message Delivery Delay

Source: https://upstash.com/docs/qstash/qstash/api/schedules/create

Learn how to delay the delivery of scheduled messages using the `Upstash-Delay` header.

```APIDOC
## Configuring Message Delivery Delay

### Description
Delay the delivery of scheduled messages using the `Upstash-Delay` header. This setting affects when a scheduled message is actually delivered after its scheduled time.

### Method
POST, PUT (Implied by context of setting configurations)

### Endpoint
/websites/upstash-qstash (Implied base endpoint)

### Headers
- **Upstash-Delay** (string) - Optional - Specifies the delay for message delivery. The format is a number followed by a duration abbreviation: `s` (seconds), `m` (minutes), `h` (hours), `d` (days). Examples: `"50s"`, `"3m"`, `"10h"`, `"1d"`.

### Request Example
```json
{
  "Upstash-Delay": "15m"
}
```

### Response
(No specific response details provided for delay configuration itself, assumes success if request is processed.)

```

--------------------------------

### POST /v2/queues/

Source: https://upstash.com/docs/qstash/qstash/api/queues/upsert

Creates a new queue in QStash. You can specify the queue name and the desired parallelism for consumers.

```APIDOC
## POST /v2/queues/

### Description
Creates a new queue in QStash. You can specify the queue name and the desired parallelism for consumers.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/queues/

### Parameters
#### Request Body
- **queueName** (string) - Required - The name of the queue.
- **parallelism** (int) - Required - The number of parallel consumers consuming from the queue. Note: Setting parallelism with queues will be deprecated; use Flow Control for more options.

### Request Example
{
  "queueName": "my-queue",
  "parallelism": 5
}

### Response
#### Success Response (200)
- **message** (string) - Indicates the queue was added successfully.

#### Error Response (412)
- **error** (string) - Indicates failure due to exceeding the allowed number of queues limit.

### Response Example
```json
{
  "message": "Queue 'my-queue' created successfully."
}
```
```

--------------------------------

### Create a Schedule with Cron Expression (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/features/schedules

Demonstrates how to create a schedule that publishes a message every minute using a cron expression. Requires the Upstash QStash client and a valid QStash token.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
});

```

--------------------------------

### Next.js Client: Trigger Background Job

Source: https://upstash.com/docs/qstash/qstash/features/background-jobs

This client-side component in a Next.js application features a button that, when clicked, sends a POST request to the '/api/start-email-job' endpoint with a list of users. This initiates the background job process.

```typescript
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

### Schedule an Item to a Queue (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/features/schedules

Explains how to schedule an item to be added to a specific queue at a designated time. Requires the Upstash QStash client, a valid QStash token, and the queue name.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
  queueName: "yourQueueName",
});

```

--------------------------------

### Publish Anthropic LLM Request with QStash

Source: https://upstash.com/docs/qstash/qstash/integrations/anthropic

Publishes a JSON request to the Anthropic LLM API via QStash. It specifies the 'llm' API name and the Anthropic provider, using a callback URL for asynchronous response handling. This is suitable for scenarios where streaming completions are not directly supported.

```javascript
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

### POST /v2/batch - Batching messages with headers and body

Source: https://upstash.com/docs/qstash/qstash/features/batch

Send messages in a batch with custom headers and request bodies for each message.

```APIDOC
## POST /v2/batch - Batching messages with headers and body

### Description
Send a batch of messages, allowing for custom headers and bodies for each individual message.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/batch

### Parameters
#### Request Body
- **destination** (string) - Required - The destination URL or URL Group.
- **headers** (object) - Optional - Custom headers for the message. Example: `{"Upstash-Delay": "5s"}`.
- **body** (string) - Optional - The message body.

### Request Example
```json
[
  {
      "destination": "myUrlGroup",
      "headers":{
        "Upstash-Delay":"5s",
        "Upstash-Forward-Hello":"123456"
      },
      "body": "Hello World"
  },
  {
      "destination": "https://example.com/destination1",
      "headers":{
        "Upstash-Delay":"7s",
        "Upstash-Forward-Hello":"789"
      }
  },
  {
      "destination": "https://example.com/destination2",
      "headers":{
        "Upstash-Delay":"9s",
        "Upstash-Forward-Hello":"again"
      }
  }
]
```

### Response
#### Success Response (200)
An array containing responses for each message, which may be an array of message IDs for URL Groups or single message IDs.

#### Response Example
```json
[
  [
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint1.com"
    },
    {
      "messageId": "msg_...",
      "url": "https://myUrlGroup-endpoint2.com"
    }
  ],
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]
```
```

--------------------------------

### Publish Message with Custom Headers (cURL)

Source: https://upstash.com/docs/qstash/qstash/howto/publishing

Demonstrates how to publish a JSON message with custom headers using cURL. It shows how to set authorization, forward a custom header, specify content type, and send the message body to a QStash publish endpoint.

```Bash
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

--------------------------------

### Send Single Email with QStash and Resend (Node.js)

Source: https://upstash.com/docs/qstash/qstash/integrations/resend

Demonstrates sending a single email using the qstash-js SDK with the Resend provider. Requires QSTASH_TOKEN and RESEND_TOKEN environment variables for authentication. The 'body' field accepts parameters supported by the Resend Send Email API.

```javascript
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

### Assigning a Schedule ID

Source: https://upstash.com/docs/qstash/qstash/api/schedules/create

Understand how to assign a specific ID to a schedule using the `Upstash-Schedule-Id` header.

```APIDOC
## Assigning a Schedule ID

### Description
Assign a custom schedule ID when creating a schedule, or update an existing schedule's settings if an ID is provided. If no ID is provided, QStash assigns a random ID.

### Method
POST, PUT (Implied by context of setting configurations)

### Endpoint
/websites/upstash-qstash (Implied base endpoint)

### Headers
- **Upstash-Schedule-Id** (string) - Optional - Assigns a specific ID to the schedule. If a schedule with this ID already exists, its settings will be updated.

### Request Example
```json
{
  "Upstash-Schedule-Id": "my-daily-report-schedule"
}
```

### Response
#### Success Response (200)
- **scheduleId** (string) - Required - The unique ID of the created or updated schedule.

#### Response Example
```json
{
  "scheduleId": "my-daily-report-schedule"
}
```

```

--------------------------------

### Integrate Helicone Analytics with Custom LLM Provider (JavaScript)

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Configures QStash to send LLM usage data to Helicone for analytics. This involves passing the Helicone API key during the initialization of a custom LLM provider. It enables monitoring and insights into LLM interactions through the Helicone platform.

```javascript
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

### Batch Anthropic LLM Requests with QStash

Source: https://upstash.com/docs/qstash/qstash/integrations/anthropic

Sends multiple Anthropic LLM requests concurrently using QStash's batching feature. Each request in the batch is configured with the Anthropic provider and a unique callback URL for processing. This optimizes sending numerous LLM prompts efficiently.

```javascript
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

### POST /v2/publish/{destination_url}

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/python

Publishes a message to a specified destination URL using QStash. Requires authentication with a QStash token.

```APIDOC
## POST /v2/publish/{destination_url}

### Description
Publishes a message to a specified destination URL using QStash. This endpoint is typically used to send webhook notifications or data to a registered endpoint.

### Method
POST

### Endpoint
`/v2/publish/{destination_url}`

### Parameters

#### Path Parameters
- **destination_url** (string) - Required - The URL of the destination endpoint where the message will be published.

#### Query Parameters
None

#### Request Body
- **body** (object) - Required - The message payload to be sent. This is expected to be a JSON object.

### Request Example
```json
{
  "hello": "world"
}
```

### Headers
- **Authorization**: Bearer <QSTASH_TOKEN>
- **Content-Type**: application/json

### Response
#### Success Response (200)
- **messageId** (string) - The unique identifier for the published message.

#### Response Example
```json
{
  "messageId": "msg_abc123"
}
```

### Error Handling
- **400 Bad Request**: Invalid request payload or missing parameters.
- **401 Unauthorized**: Invalid or missing QStash token.
- **404 Not Found**: The destination URL does not exist or is not reachable.
```

--------------------------------

### Create a Schedule to a URL Group (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/features/schedules

Shows how to create a schedule that publishes messages to a URL Group. You can specify the URL Group by its name or ID. Requires the Upstash QStash client and a valid QStash token.

```typescript
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "urlGroupName",
  cron: "* * * * *",
});

```

--------------------------------

### Publish Webhook Request with QStash

Source: https://upstash.com/docs/qstash/qstash/howto/webhook

Configure a QStash publish request to forward webhook calls to your endpoint. You can specify configurations like retries and delay using HTTP headers or query parameters. Headers prefixed with `Upstash-Forward-` are forwarded by default, or you can enable forwarding all headers with `Upstash-Header-Forward: true`.

```http
POST https://qstash.upstash.io/v2/publish/https://example.com/api/webhook?qstash_token=<QSTASH_TOKEN>
Header: Upstash-Retries: 3
Header: Upstash-Delay: 100s
Header: Upstash-Header-Forward: true
```

--------------------------------

### Publishing a Message with Callback Headers

Source: https://upstash.com/docs/qstash/qstash/api/enqueue

Defines how to use Upstash-Failure-Callback-Forward-* headers to specify headers sent with failure callback requests.

```APIDOC
## POST /websites/upstash-qstash

### Description
This endpoint allows publishing messages to Upstash QStash. It supports advanced features like failure callbacks and content-based deduplication.

### Method
POST

### Endpoint
/websites/upstash-qstash

#### Query Parameters
- **Upstash-Deduplication-Id** (string) - Optional - Id to use while deduplicating messages, so that only one message with the given deduplication id is published.
- **Upstash-Content-Based-Deduplication** (boolean) - Optional - When set to true, automatically deduplicates messages based on their content.
- **Upstash-Failure-Callback** (string) - Optional - Callback URL to be invoked when the delivery fails.
- **Upstash-Failure-Callback-Forward-*** (string) - Optional - Headers to be forwarded with the failure callback request. The prefix `Upstash-Failure-Callback-Forward-` is stripped, and the rest of the header name and value are forwarded. Example: `Upstash-Failure-Callback-Forward-My-Header: my-value` will forward `My-Header: my-value`.

### Request Body
(Not explicitly defined in the provided text, but typically contains the message payload).

### Response
#### Success Response (200)
- **messageId** (string) - The unique id of this message.
- **deduplicated** (boolean) - Whether this message is a duplicate and was not sent to the destination.

#### Array of Objects Response (for topic destinations)
- **array** (object[]) - An array containing objects for each URL in the topic.
  - **messageId** (string) - The unique id of this message.
  - **url** (string) - The URL where the message was sent to.
  - **deduplicated** (boolean) - Whether this message is a duplicate and was not sent to the destination.

#### Response Example (Single Object)
```json
{
  "messageId": "msg_abc123",
  "deduplicated": false
}
```

#### Response Example (Array of Objects)
```json
[
  {
    "messageId": "msg_xyz789",
    "url": "http://example.com/callback",
    "deduplicated": false
  }
]
```
```

--------------------------------

### Upstash QStash Queue Response Structure

Source: https://upstash.com/docs/qstash/qstash/api/queues/list

Illustrates the JSON structure returned when listing Upstash QStash queues. Each queue object contains creation and update timestamps, name, parallelism, and lag.

```json
[
  {
    "createdAt": 1623345678001,
    "updatedAt": 1623345678001,
    "name": "my-queue",
    "parallelism" : 5, 
    "lag" : 100
  },
  // ...
]
```

--------------------------------

### POST /v2/batch - Publishing messages to queues

Source: https://upstash.com/docs/qstash/qstash/features/batch

Send a batch of messages to specified queues. Each message can be associated with a queue name.

```APIDOC
## POST /v2/batch - Publishing messages to queues

### Description
Batch send messages, specifying a queue for each message.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/batch

### Parameters
#### Request Body
- **queue** (string) - Required - The name of the queue.
- **destination** (string) - Required - The destination URL for the message.

### Request Example
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
An array of responses for each message in the batch.

#### Response Example
```json
[
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]
```
```

--------------------------------

### POST /v2/batch - Publishing messages to URL Groups

Source: https://upstash.com/docs/qstash/qstash/features/batch

Send a batch of messages using URL Groups. The destination can be a URL Group name or a specific URL.

```APIDOC
## POST /v2/batch - Publishing messages to URL Groups

### Description
Send messages in a batch to a URL Group or a mix of URL Groups and specific URLs.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/batch

### Parameters
#### Request Body
- **destination** (string) - Required - The name of the URL Group or the destination URL.

### Request Example
```json
[
  {
    "destination": "myUrlGroup"
  },
  {
    "destination": "https://example.com/destination2"
  }
]
```

### Response
#### Success Response (200)
An array of responses, corresponding to each message sent.

#### Response Example
```json
[
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]
```
```

--------------------------------

### Stream Response

Source: https://upstash.com/docs/qstash/qstash/api/llm/create

This section describes the structure of the response when the `stream` parameter is set to `true`. It details the properties returned for each chunk of a streamed response, including identifiers, choices, deltas, and usage information.

```APIDOC
## Stream Response

### Description
Returned when `stream` is `true`. This details the structure of each chunk in a streamed response.

### Method
N/A (Describes response structure, not a specific request method)

### Endpoint
N/A

### Parameters
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **id** (string) - A unique identifier for the chat completion. Each chunk has the same ID.
- **choices** (Object[]) - A list of chat completion choices. Can be more than one if `n` is greater than `1`. Can also be empty for the last chunk.
  - **delta** (Object) - A chat completion delta generated by streamed model responses.
    - **role** (string) - The role of the author of this message.
    - **content** (string) - The contents of the chunk message.
  - **finish_reason** (string) - The reason the model stopped generating tokens. This will be `stop` if the model hit a natural stop point or a provided stop sequence, `length` if the maximum number of tokens specified in the request was reached.
  - **index** (number) - The index of the choice in the list of choices.
  - **logprobs** (Object) - Log probability information for the choice.
    - **content** (Object[]) - A list of message content tokens with log probability information.
      - **token** (string) - The token.
      - **logprob** (number) - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
      - **bytes** (number[]) - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
    - **top_logprobs** (Object[]) - List of the most likely tokens and their log probability, at this token position. In rare cases, there may be fewer than the number of requested `top_logprobs` returned.
      - **token** (string) - The token.
      - **logprob** (number) - The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
      - **bytes** (number[]) - A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
- **created** (number) - The Unix timestamp (in seconds) of when the chat completion was created. Each chunk has the same timestamp.
- **model** (string) - The model used for the chat completion.
- **system_fingerprint** (string) - This fingerprint represents the backend configuration that the model runs with. Can be used in conjunction with the `seed` request parameter to understand when backend changes have been made that might impact determinism.
- **object** (string) - The object type, which is always `chat.completion.chunk`.
- **usage** (Object) - It contains a null value except for the last chunk which contains the token usage statistics for the entire request.
  - **completion_tokens** (number) - Number of tokens in the generated completion.
  - **prompt_tokens** (number) - Number of tokens in the prompt.
  - **total_tokens** (number) - Total number of tokens used in the request (prompt + completion).

#### Response Example
N/A
```

--------------------------------

### Chat Completion Response (Non-Streaming)

Source: https://upstash.com/docs/qstash/qstash/api/llm/create

Details the structure of the response received when requesting a chat completion without streaming enabled.

```APIDOC
## GET /websites/upstash-qstash/completions

### Description
This endpoint provides chat completions. The response structure detailed here is for non-streaming requests.

### Method
GET

### Endpoint
/websites/upstash-qstash/completions

### Parameters
#### Query Parameters
- **stream** (boolean) - Optional - If `false` or not set, returns the response in this format.

### Response
#### Success Response (200)
- **id** (string) - A unique identifier for the chat completion.
- **choices** (Object[]) - A list of chat completion choices. Can be more than one if `n` is greater than `1`.
  - **message** (Object) - A chat completion message generated by the model.
    - **role** (string) - The role of the author of this message.
    - **content** (string) - The contents of the message.
  - **finish_reason** (string) - The reason the model stopped generating tokens (`stop`, `length`).
  - **logprobs** (Object) - Log probability information for the choice.
    - **content** (Object[]) - A list of message content tokens with log probability information.
      - **token** (string) - The token.
      - **logprob** (number) - The log probability of this token.
      - **bytes** (number[]) - UTF-8 bytes representation of the token.
    - **top_logprobs** (Object[]) - List of the most likely tokens and their log probability.
      - **token** (string) - The token.
      - **logprob** (number) - The log probability of this token.
      - **bytes** (number[]) - UTF-8 bytes representation of the token.
  - **index** (number) - The index of the choice in the list.
- **created** (number) - The Unix timestamp (in seconds) of when the chat completion was created.
- **model** (string) - The model used for the chat completion.
- **system_fingerprint** (string) - Backend configuration fingerprint.
- **object** (string) - The object type, always `chat.completion`.
- **usage** (Object) - Usage statistics for the completion request.
  - **completion_tokens** (number) - Number of tokens in the generated completion.
  - **prompt_tokens** (number) - Number of tokens in the prompt.
  - **total_tokens** (number) - Total number of tokens used in the request.

#### Response Example
```json
{
  "id": "chatcmpl-123",
  "object": "chat.completion",
  "created": 1677652288,
  "model": "gpt-3.5-turbo-0613",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Hello world!"
      },
      "finish_reason": "stop",
      "logprobs": {
        "content": [
          {
            "token": "Hello",
            "logprob": -0.1,
            "bytes": [72, 101, 108, 108, 111],
            "top_logprobs": [
              {
                "token": "Hello",
                "logprob": -0.1,
                "bytes": [72, 101, 108, 108, 111]
              }
            ]
          }
        ]
      }
    }
  ],
  "usage": {
    "prompt_tokens": 10,
    "completion_tokens": 5,
    "total_tokens": 15
  },
  "system_fingerprint": "fp_abc123"
}
```
```

--------------------------------

### Publish Message to QStash via ngrok Tunnel

Source: https://upstash.com/docs/qstash/qstash/howto/local-tunnel

Publishes a JSON message to QStash, targeting a public URL provided by ngrok, which forwards the request to your local API endpoint. Ensure the correct authorization token and API path are used.

```bash
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://e02f-2a02-810d-af40-5284-b139-58cc-89df-b740.eu.ngrok.io/api/webhooks'
```

--------------------------------

### Publish Message with Failure Callback (cURL)

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

This cURL command demonstrates how to publish a message to Upstash QStash while specifying a failure callback URL. The `Upstash-Failure-Callback` header is crucial for this functionality. It sends a JSON payload to the destination URL.

```curl
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

--------------------------------

### Send Batch Emails with QStash and Resend (Node.js)

Source: https://upstash.com/docs/qstash/qstash/integrations/resend

Illustrates sending multiple emails simultaneously using Resend's Batch Email API via the qstash-js SDK. The `batch: true` option is enabled in the provider configuration. Each email in the batch is defined as an object within the 'body' array, allowing individual customization.

```javascript
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

### Publish LLM Chat Completion Request (JavaScript)

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Publishes a single LLM chat completion request using QStash. It specifies the LLM API destination and requires a callback URL for asynchronous processing. This method is suitable for general LLM API calls where retries and batching are beneficial.

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

--------------------------------

### Batch Publish to URL Groups

Source: https://upstash.com/docs/qstash/qstash/features/batch

Efficiently send messages to a URL Group or a mix of URL Groups and specific destinations. This simplifies broadcasting messages to predefined groups of URLs.

```cURL
curl -XPOST https://qstash.upstash.io/v2/batch \
    -H 'Authorization: Bearer XXX' \
    -H 'Content-type: application/json' \
    -d ' \
     [ \
      {
        "destination": "myUrlGroup"
      },
      {
        "destination": "https://example.com/destination2"
      }
     ]'

```

--------------------------------

### Configure QStash Credentials in wrangler.toml

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Demonstrates how to manually configure QStash credentials within the `wrangler.toml` configuration file. This involves setting the `QSTASH_URL`, `QSTASH_TOKEN`, `QSTASH_CURRENT_SIGNING_KEY`, and `QSTASH_NEXT_SIGNING_KEY` variables, which are essential for the Cloudflare Worker to authenticate with QStash.

```toml
[vars]
QSTASH_URL="REPLACE_HERE"
QSTASH_TOKEN="REPLACE_HERE"
QSTASH_CURRENT_SIGNING_KEY="REPLACE_HERE"
QSTASH_NEXT_SIGNING_KEY="REPLACE_HERE"

```

--------------------------------

### POST /v2/batch - Publishing messages to destinations

Source: https://upstash.com/docs/qstash/qstash/features/batch

Send a batch of messages to specified destinations. Each object in the array represents a message with its destination.

```APIDOC
## POST /v2/batch - Publishing messages to destinations

### Description
Allows sending multiple messages simultaneously to predefined destinations.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/batch

### Parameters
#### Request Body
- **destination** (string) - Required - The URL of the destination endpoint.

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
An array of responses, one for each message sent in the batch.

#### Response Example
```json
[
  {
    "messageId": "msg_..."
  },
  {
    "messageId": "msg_..."
  }
]
```
```

--------------------------------

### Create a Schedule

Source: https://upstash.com/docs/qstash/qstash/features/schedules

Creates a new schedule to publish a message at a given cron expression. The destination can be a URL, a URL Group name or ID, or a queue name.

```APIDOC
## POST /v1/schedules

### Description
Creates a new schedule to publish a message at a given cron expression. The destination can be a URL, a URL Group name or ID, or a queue name.

### Method
POST

### Endpoint
/v1/schedules

### Parameters
#### Request Body
- **destination** (string) - Required - The destination URL, URL Group name/ID, or queue name.
- **cron** (string) - Required - The cron expression defining the schedule.
- **queueName** (string) - Optional - The name of the queue to add the message to.
- **scheduleId** (string) - Optional - An explicit ID to use for the schedule, useful for overwriting.

### Request Example
```json
{
  "destination": "https://example.com",
  "cron": "* * * * *"
}
```

### Response
#### Success Response (200)
- **scheduleId** (string) - The ID of the created schedule.

#### Response Example
```json
{
  "scheduleId": "generated-schedule-id"
}
```
```

--------------------------------

### Default Exponential Backoff Algorithm Calculation

Source: https://upstash.com/docs/qstash/qstash/features/retry

Illustrates the mathematical formula for the default exponential backoff algorithm used by QStash to calculate retry delays. The delay increases exponentially with each retry, capped at 86400 seconds (1 day).

```Mathematical Expression
n = how many times this request has been retried
delay =  min(86400, e ** (2.5*n)) // in seconds
```

--------------------------------

### QStash Failure Callback Configuration Headers

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

These headers allow configuration of failure callbacks for Upstash QStash messages. They control aspects like timeout, retries, delay, and HTTP method for failure callback attempts.

```headers
Upstash-Callback-Timeout 
Upstash-Callback-Retries
Upstash-Callback-Delay 
Upstash-Callback-Method 
Upstash-Failure-Callback-Timeout 
Upstash-Failure-Callback-Retries
Upstash-Failure-Callback-Delay
Upstash-Failure-Callback-Method
```

--------------------------------

### POST /v2/publish/{url}

Source: https://upstash.com/docs/qstash/qstash/howto/publishing

Publishes a message to a specified URL. The message content is sent in the request body. Custom headers can be forwarded by prefixing them with 'Upstash-Forward-'.

```APIDOC
## POST /v2/publish/{url}

### Description
Publishes a message to a specified URL. The message content is sent in the request body. Custom headers can be forwarded by prefixing them with 'Upstash-Forward-'. Destination URLs must include a protocol (http:// or https://).

### Method
POST

### Endpoint
`/v2/publish/{url}`

### Parameters
#### Path Parameters
- **url** (string) - Required - The destination URL or URL Group name.

#### Query Parameters
None specified.

#### Request Body
- **body** (any) - Required - The content of the message to be sent. Can be any data type.

### Request Example
```curl
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation of message publication.

#### Response Example
```json
{
  "message": "Message published successfully."
}
```
```

--------------------------------

### Enqueue LLM Chat Completion Request (JavaScript)

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Enqueues an LLM chat completion request to a specified QStash queue. Similar to publishing, it utilizes QStash features for asynchronous handling and requires a callback URL. This is useful for managing LLM tasks within a queueing system.

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

--------------------------------

### Handling Retries with Retry-After Headers

Source: https://upstash.com/docs/qstash/qstash/features/retry

This section explains how to use `Retry-After` or rate limit headers in your response to QStash to control the timing of retry attempts.

```APIDOC
## Handling Retry Timing

### Description
When QStash attempts to deliver a message to your endpoint and it fails (non-2xx status code), QStash will retry. Instead of relying on the default backoff, you can influence the retry schedule by including specific headers in your response to QStash.

### Supported Headers
- **Retry-After**: Specifies the delay before the next retry attempt. Can be in seconds, RFC1123 date format, or duration format (e.g., `6m5s`).
- **X-RateLimit-Reset**: Specifies the time (in seconds since epoch) when rate limits are reset.
- **X-RateLimit-Reset-Requests**: Specifies the time when the rate limit for request counts resets.
- **X-RateLimit-Reset-Tokens**: Specifies the time when the rate limit for token counts resets.

### Constraints
- The maximum delay for any retry, including those specified via headers, is capped at one day (86400 seconds). Values beyond this limit will default to the maximum backoff.

### Response Examples
```
Retry-After: 0                             // Next retry will be scheduled immediately.
Retry-After: 10                            // Next retry will be scheduled after a 10-second delay.
Retry-After: 6m5s                          // Next retry will be scheduled after 6 minutes 5 seconds.
Retry-After: Sun, 27 Jun 2024 12:16:24 GMT // Next retry will be scheduled for the specified date.
```

### Notes
Using these headers is particularly useful for integrating with rate-limiting mechanisms in your application, ensuring that retries align with availability windows.
```

--------------------------------

### Publish Message Details (JSON)

Source: https://upstash.com/docs/qstash/qstash/howto/publishing

Shows the expected structure of the message body and headers that will be delivered to the destination API after being processed by QStash. This includes the message content and any forwarded headers.

```JSON
// body
{ "hello": "world" }

// headers
My-Header:      my-value
Content-Type:   application/json
```

--------------------------------

### QStash Callback Response Structure

Source: https://upstash.com/docs/qstash/qstash/features/callbacks

Details the structure of the JSON object that QStash sends to your specified callback URL upon completion of a message delivery.

```APIDOC
## Callback Response Structure

### Description
This is the format of the JSON payload received at your callback URL. It contains information about the original message and its delivery status.

### Response Body Structure
- **status** (number) - The HTTP status code of the original request.
- **header** (object) - The response headers from the original request. Values are arrays of strings.
- **body** (string) - The base64 encoded response body from the original request.
- **retried** (number) - The number of times QStash retried to deliver the original message.
- **maxRetries** (number) - The maximum number of retries configured for the message.
- **sourceMessageId** (string) - The unique identifier of the message that triggered this callback.
- **topicName** (string) - The name of the URL Group (topic) if the message was part of one.
- **endpointName** (string) - The name of the endpoint if it was named within a topic.
- **url** (string) - The destination URL of the original message.
- **method** (string) - The HTTP method used for the original message delivery.
- **sourceHeader** (object) - The HTTP headers of the original message.
- **sourceBody** (string) - The base64 encoded body of the original message.
- **notBefore** (string) - The Unix timestamp (in milliseconds) when the original message was scheduled for delivery.
- **createdAt** (string) - The Unix timestamp (in milliseconds) when the original message was created.
- **scheduleId** (string) - The ID of the schedule if the message was triggered by a schedule.
- **callerIP** (string) - The IP address from which the original message was published.

### Response Example
```json
{
  "status": 200,
  "header": { "content-type": ["application/json"] },
  "body": "YmFzZTY0IGVuY29kZWQgcm9keQ==",
  "retried": 0,
  "maxRetries": 3,
  "sourceMessageId": "msg_abc123",
  "topicName": "myTopic",
  "endpointName": "myEndpoint",
  "url": "http://myurl.com",
  "method": "POST",
  "sourceHeader": { "content-type": "application/json" },
  "sourceBody": "eyJ1c2VySWQiOiIxMjMifQ==",
  "notBefore": "1701198458025",
  "createdAt": "1701198447054",
  "scheduleId": "scd_xyz789",
  "callerIP": "178.247.74.179"
}
```
```

--------------------------------

### Publishing a Chat Completion Request

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Demonstrates how to publish a single chat completion request to an LLM API using QStash. This utilizes QStash features like retries and callbacks for asynchronous processing.

```APIDOC
## POST /v1/publish

### Description
Publishes a single LLM chat completion request.

### Method
POST

### Endpoint
/v1/publish

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API details, including name and provider.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Details of the LLM provider (e.g., openai).
    - **token** (string) - Required - API token for the LLM provider.
- **body** (object) - Required - The chat completion request payload, conforming to the LLM provider's API.
  - **model** (string) - Required - The LLM model to use.
  - **messages** (array) - Required - An array of message objects for the chat conversation.
- **callback** (string) - Optional - URL to receive asynchronous responses.

### Request Example
```json
{
    "api": {
        "name": "llm",
        "provider": {
            "openai": {
                "token": "_OPEN_AI_TOKEN_"
            }
        }
    },
    "body": {
        "model": "gpt-3.5-turbo",
        "messages": [
            {
                "role": "user",
                "content": "Write a hello world program in Rust."
            }
        ]
    },
    "callback": "https://abc.requestcatcher.com/"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the published message.
- ** 202** (integer) - Indicates the request was accepted for processing.

#### Response Example
```json
{
    "messageId": "msg-xxxxxxxxxxxxxxxxx"
}
```
```

--------------------------------

### Import Necessary Libraries for QStash Verification

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/python

Imports required Python libraries for handling JSON, environment variables, cryptographic operations (HMAC, SHA256, Base64), time, and JWT decoding.

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

### Enqueueing a Chat Completion Request

Source: https://upstash.com/docs/qstash/qstash/integrations/llm

Shows how to enqueue a chat completion request to a specific queue using QStash. This is useful for managing ordered LLM processing.

```APIDOC
## POST /v1/queues/{queueName}/enqueue

### Description
Enqueues a chat completion request into a specified queue.

### Method
POST

### Endpoint
/v1/queues/{queueName}/enqueue

### Parameters
#### Path Parameters
- **queueName** (string) - Required - The name of the queue to enqueue the message into.

#### Query Parameters
None

#### Request Body
- **api** (object) - Required - Specifies the LLM API details, including name and provider.
  - **name** (string) - Required - Must be 'llm'.
  - **provider** (object) - Required - Details of the LLM provider (e.g., openai).
    - **token** (string) - Required - API token for the LLM provider.
- **body** (object) - Required - The chat completion request payload, conforming to the LLM provider's API.
  - **model** (string) - Required - The LLM model to use.
  - **messages** (array) - Required - An array of message objects for the chat conversation.
- **callback** (string) - Optional - URL to receive asynchronous responses.

### Request Example
```json
{
    "api": {
        "name": "llm",
        "provider": {
            "openai": {
                "token": "_OPEN_AI_TOKEN_"
            }
        }
    },
    "body": {
        "model": "gpt-3.5-turbo",
        "messages": [
            {
                "role": "user",
                "content": "Write a hello world program in Rust."
            }
        ]
    },
    "callback": "https://abc.requestcatcher.com"
}
```

### Response
#### Success Response (200)
- **messageId** (string) - The ID of the enqueued message.
- ** 202** (integer) - Indicates the request was accepted for processing.

#### Response Example
```json
{
    "messageId": "msg-yyyyyyyyyyyyyyy"
}
```
```

--------------------------------

### POST /v2/publish/:url

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Publishes a message to a specified URL via QStash. The destination URL is typically provided during a deployment step.

```APIDOC
## POST /v2/publish/:url

### Description
Publishes a message to a specified URL using QStash. The destination URL is usually provided during a previous deployment step.

### Method
POST

### Endpoint
/v2/publish/https://cloudflare-workers.upstash.workers.dev

### Parameters
#### Path Parameters
- **url** (string) - Required - The destination URL to which the message will be published.

#### Headers
- **Authorization** (string) - Required - Bearer token for authentication (e.g., "Bearer <QSTASH_TOKEN>").
- **Content-Type** (string) - Required - Specifies the content type of the request body, typically "application/json".

### Request Body
- **hello** (string) - Example field - Description of the message content.

### Request Example
```json
{
  "hello": "world"
}
```

### Response
#### Success Response (200)
Indicates that the message was successfully published and verified by the destination worker.

#### Response Example
```
POST https://cloudflare-workers.upstash.workers.dev/ - Ok @ 7/11/2022, 5:13:19 PM
  (log) The signature was valid
```
```

--------------------------------

### Golang: JWT Signature Verification for QStash

Source: https://upstash.com/docs/qstash/qstash/quickstarts/fly-io/go

Implements the JWT verification logic for incoming QStash webhook signatures. It parses the JWT token, validates the signing method and key, and checks claims such as issuer, expiration, and the request body hash. Requires the `golang-jwt/jwt` library.

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

### Add Helicone Analytics to Anthropic LLM Request with QStash

Source: https://upstash.com/docs/qstash/qstash/integrations/anthropic

Configures an Anthropic LLM request published via QStash to include Helicone analytics. This involves passing the Helicone API key within the `analytics` object to monitor usage. It requires setting the `HELICONE_API_KEY` environment variable.

```javascript
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

### Define Environment Variables for QStash

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Defines the `Env` interface for a Cloudflare Worker, specifying the required environment variables: `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY`. These keys are used by the QStash Receiver to validate incoming webhook signatures.

```typescript
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string
  QSTASH_NEXT_SIGNING_KEY: string
}

```

--------------------------------

### Add Endpoints to URL Group (curl)

Source: https://upstash.com/docs/qstash/qstash/api/url-groups/add-endpoint

This snippet demonstrates how to add multiple endpoints to a specified URL group (topic) using a cURL command. It requires an authorization token and a JSON payload containing the endpoints' names and URLs. The API will create the URL group or endpoints if they do not already exist.

```curl
curl -XPOST https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ \
    "endpoints": [ \
      { \
        "name": "endpoint1", \
        "url": "https://example.com" \
      }, \
      { \
        "name": "endpoint2", \
        "url": "https://somewhere-else.com" \
      } \
    ] \
  }'
```

--------------------------------

### QStash API Authentication - Query Parameter

Source: https://upstash.com/docs/qstash/qstash/api/authentication

Authenticate QStash API requests by including your QSTASH_TOKEN as a query parameter `qstash_token` when header authentication is not possible.

```APIDOC
## POST /v2/publish/...

### Description
Publish a message to QStash using a query parameter for authentication.

### Method
POST

### Endpoint
https://qstash.upstash.io/v2/publish/...

### Parameters
#### Path Parameters
None

#### Query Parameters
- **qstash_token** (string) - Required - Your QStash API token.

#### Request Body
None (Assumed for publish example, actual body depends on the specific publish operation)

### Request Example
```bash
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

### Response
#### Success Response (200)
Details of the published message or success status.

#### Response Example
```json
{
  "messageId": "msg_..."
}
```
```

--------------------------------

### Request Authorization

Source: https://upstash.com/docs/qstash/qstash/features/security

All requests to the QStash API must include an authorization token in the `Authorization` header.

```APIDOC
## Request Authorization

### Description
When interacting with the QStash API, you will need an authorization token. You can get your token from the Console.
Send this token along with every request made to `QStash` inside the `Authorization` header.

### Header
`Authorization: Bearer <QSTASH_TOKEN>`
```

--------------------------------

### Overwrite an Existing Schedule (TypeScript)

Source: https://upstash.com/docs/qstash/qstash/features/schedules

Demonstrates how to overwrite an existing schedule by providing its `scheduleId`. This allows for updating or replacing a previously created schedule. Requires the Upstash QStash client and a valid QStash token.

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

### Import QStash Receiver in TypeScript

Source: https://upstash.com/docs/qstash/qstash/quickstarts/cloudflare-workers

Imports the `Receiver` class from the `@upstash/qstash` library. This class is used to handle incoming QStash messages and verify their signatures.

```typescript
import { Receiver } from "@upstash/qstash"

```

--------------------------------

### Customize Retry Delay with Expression (cURL)

Source: https://upstash.com/docs/qstash/qstash/features/retry

Shows how to override the default exponential backoff by providing a custom retry delay expression using the `Upstash-Retry-Delay` header in cURL. This allows for flexible retry scheduling.

```cURL
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

--------------------------------

### AWS Lambda Handler for QStash Webhook Verification

Source: https://upstash.com/docs/qstash/qstash/quickstarts/aws-lambda/python

The main handler function for the AWS Lambda. It parses incoming event data, retrieves signing keys from environment variables, and calls the verify function. It returns a 400 error if verification fails or 200 if successful.

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
```

