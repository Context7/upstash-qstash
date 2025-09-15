```
================
CODE SNIPPETS
================
TITLE: Install QStash Python Library via pip
DESCRIPTION: This command installs the `qstash` Python library using pip, the Python package installer. It's the first step to integrate QStash into your Python project.

SOURCE: https://upstash.com/docs/qstash/sdks/py/gettingstarted.mdx

LANGUAGE: bash
CODE:
```
pip install qstash
```

--------------------------------

TITLE: Initialize and Use Synchronous QStash Client
DESCRIPTION: This snippet demonstrates how to initialize the synchronous QStash client by providing your QStash token. It then shows a basic example of publishing a JSON message. This client blocks execution until the message publishing operation completes.

SOURCE: https://upstash.com/docs/qstash/sdks/py/gettingstarted.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(...)
```

--------------------------------

TITLE: Install Upstash QStash Client via NPM
DESCRIPTION: This command installs the official Upstash QStash client library using npm, making it available for use in your Node.js or TypeScript projects. It's the first step to integrate QStash functionality.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/gettingstarted.mdx

LANGUAGE: bash
CODE:
```
npm install @upstash/qstash
```

--------------------------------

TITLE: Initialize and Use Asynchronous QStash Client
DESCRIPTION: This example illustrates how to set up and use the asynchronous QStash client within an `asyncio` event loop. The `AsyncQStash` client allows for non-blocking operations, which is ideal for concurrent applications. It shows how to publish a JSON message asynchronously.

SOURCE: https://upstash.com/docs/qstash/sdks/py/gettingstarted.mdx

LANGUAGE: python
CODE:
```
import asyncio

from qstash import AsyncQStash


async def main():
    client = AsyncQStash("<QSTASH_TOKEN>")
    await client.message.publish_json(...)


asyncio.run(main())
```

--------------------------------

TITLE: Initialize Next.js Application and Install QStash
DESCRIPTION: Commands to create a new Next.js project, navigate into its directory, install the official Upstash QStash client library, and start the development server.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: bash
CODE:
```
npx create-next-app@latest qstash-bg-job
cd qstash-bg-job
npm install @upstash/qstash
npm run dev
```

--------------------------------

TITLE: QStash Get Signing Keys - Response Example
DESCRIPTION: An example of the successful JSON response received when retrieving signing keys from the QStash API, showing the 'current' and 'next' key values.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/get.mdx

LANGUAGE: json
CODE:
```
{ "current": "sig_123", "next": "sig_456" }
```

--------------------------------

TITLE: Example: Retrieve a Queue
DESCRIPTION: Demonstrates how to make an HTTP GET request to retrieve a queue using cURL, Node.js, Python, and Go.

SOURCE: https://upstash.com/docs/qstash/api/queues/get.mdx

LANGUAGE: shell
CODE:
```
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: javascript
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/queue/my-queue', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/queue/my-queue',
   headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/queue/my-queue", nil)
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

--------------------------------

TITLE: Request Examples to List QStash Schedules
DESCRIPTION: Provides code examples in various programming languages to make a GET request to the QStash API to list all schedules, including the necessary Bearer token authorization header for authentication.

SOURCE: https://upstash.com/docs/qstash/api/schedules/list.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/schedules \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/schedules', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/schedules', 
  headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/schedules", nil)
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

--------------------------------

TITLE: Create Python Application Directory and Install Dependencies
DESCRIPTION: These commands set up the project directory and install the 'upstash-redis' library, which is required for interacting with the Redis database.

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: bash
CODE:
```
mkdir clean-db-cron
```

LANGUAGE: bash
CODE:
```
cd clean-db-cron
```

LANGUAGE: bash
CODE:
```
pip install upstash-redis
```

--------------------------------

TITLE: Initialize Upstash QStash Client
DESCRIPTION: This TypeScript snippet demonstrates how to import the `Client` class from the `@upstash/qstash` library and initialize a new client instance. A valid QStash token is required for authentication and must be provided during client instantiation.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/gettingstarted.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
});
```

--------------------------------

TITLE: Request Examples: Rotate QStash Signing Keys
DESCRIPTION: Demonstrates how to make an authenticated request to rotate QStash signing keys using various programming languages and cURL. Note: The API specification indicates a POST method, but the provided examples use GET.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/rotate.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/keys/rotate \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: javascript
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/keys/rotate', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}
response = requests.get(
  'https://qstash.upstash.io/v2/keys/rotate', 
  headers=headers
)
```

LANGUAGE: go
CODE:
```
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

--------------------------------

TITLE: Example HTTP Requests to List QStash Queues
DESCRIPTION: Demonstrates how to make authenticated GET requests to the QStash API to retrieve a list of all queues using various programming languages and cURL.

SOURCE: https://upstash.com/docs/qstash/api/queues/list.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/queues \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/queues", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/queues',
  headers=headers
)
```

LANGUAGE: go
CODE:
```
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

--------------------------------

TITLE: Launch Fly.io Application
DESCRIPTION: Demonstrates the `flyctl launch` command to initialize a new Fly.io application, including interactive prompts for app name, region, and database setup, resulting in a `fly.toml` configuration file.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: bash
CODE:
```
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

TITLE: Retrieve Schedule: Successful Response Example
DESCRIPTION: An example of the JSON response body returned upon a successful retrieval of a schedule.

SOURCE: https://upstash.com/docs/qstash/api/schedules/get.mdx

LANGUAGE: json
CODE:
```
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

TITLE: Example JSON Response for Get URL Group
DESCRIPTION: An example of the successful JSON response body returned by the QStash API when retrieving a URL Group, illustrating the structure of the `endpoints` array.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: json
CODE:
```
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

TITLE: Retrieve All URL Groups Request Examples
DESCRIPTION: Examples demonstrating how to make a GET request to the /v2/topics endpoint to retrieve all URL Groups. Requires a Bearer token for authorization.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/list.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/topics \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: Node
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/topics", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

LANGUAGE: Python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/topics',
  headers=headers
)
```

LANGUAGE: Go
CODE:
```
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

--------------------------------

TITLE: Retrieve QStash Signing Keys - Request Examples
DESCRIPTION: Illustrates how to make a request to the QStash API to retrieve signing keys using cURL, Node.js (JavaScript), Python, and Go.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/get.mdx

LANGUAGE: curl
CODE:
```
curl https://qstash.upstash.io/v2/keys \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: javascript
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/keys', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/keys',
   headers=headers
)
```

LANGUAGE: go
CODE:
```
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

--------------------------------

TITLE: Publish a message to a specific endpoint
DESCRIPTION: This example demonstrates how to publish a simple message to a designated HTTP endpoint. It shows the basic structure for sending a JSON payload to a URL via QStash.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Deploy Fly.io Application
DESCRIPTION: Simple command to deploy the Go application to Fly.io after configuration and secret setup, pushing the local code to the Fly.io platform.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: bash
CODE:
```
flyctl deploy
```

--------------------------------

TITLE: Publish a message to a URL Group for fan-out delivery
DESCRIPTION: This example illustrates how to publish a message to a predefined URL Group. URL Groups enable a fan-out pattern, delivering the same message to multiple endpoints simultaneously.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/myUrlGroup'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  urlGroup: "myUrlGroup",
  body: {
    hello: "world",
  },
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Run QStash Development Server from Direct Binary
DESCRIPTION: After downloading and extracting the QStash CLI binary from the artifact repository, this command shows how to execute it directly to start the development server on your local machine.

SOURCE: https://upstash.com/docs/qstash/howto/local-development.mdx

LANGUAGE: shell
CODE:
```
$ ./qstash dev
```

--------------------------------

TITLE: Run QStash Development Server with NPX
DESCRIPTION: This snippet demonstrates how to start the QStash development server using `npx` from the `@upstash/qstash-cli` NPM package. It also shows how to specify a custom port for the server.

SOURCE: https://upstash.com/docs/qstash/howto/local-development.mdx

LANGUAGE: javascript
CODE:
```
npx @upstash/qstash-cli dev

// Start on a different port
npx @upstash/qstash-cli dev -port=8081
```

--------------------------------

TITLE: Retrieve Schedule: Request Examples
DESCRIPTION: Demonstrates how to make a GET request to retrieve a schedule using its ID with various programming languages and cURL.

SOURCE: https://upstash.com/docs/qstash/api/schedules/get.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/schedules/scd_1234 \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/schedules/scd_1234', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/schedules/scd_1234', 
  headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/schedules/scd_1234", nil)
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

--------------------------------

TITLE: Retrieve QStash Message Request Examples
DESCRIPTION: Provides code examples in cURL, Node.js, Python, and Go demonstrating how to send a GET request to the Upstash QStash API to retrieve a specific message using its ID and a bearer token for authorization.

SOURCE: https://upstash.com/docs/qstash/api/messages/get.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/messages/msg_123", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/messages/msg_123',
  headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/messages/msg_123", nil)
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

--------------------------------

TITLE: List All Schedules using QStash API and SDKs
DESCRIPTION: This snippet demonstrates how to retrieve a list of all schedules configured within Upstash QStash. It provides examples using direct cURL commands for the REST API, as well as implementations using the official TypeScript and Python SDKs. Authentication requires a valid QStash token.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer XXX"
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
const scheds = await client.schedules.list();
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.list()
# Async version is also available
```

--------------------------------

TITLE: Deploy Application to Vercel using CLI
DESCRIPTION: These bash commands demonstrate how to install the Vercel CLI globally and then deploy the current application to Vercel, making it accessible via a public URL.

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: bash
CODE:
```
npm install -g vercel
```

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Programmatic Examples: Pause QStash Queue
DESCRIPTION: Code examples demonstrating how to pause an Upstash QStash queue using `curl`, Node.js, Python, and Go clients.

SOURCE: https://upstash.com/docs/qstash/api/queues/pause.mdx

LANGUAGE: sh
CODE:
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/pause \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
import { Client } from "@upstash/qstash";
/**
 * Import a fetch polyfill only if you are using node prior to v18.
 * This is not necessary for nextjs, deno or cloudflare workers.
 */
import "isomorphic-fetch";

const c = new Client({
  token: "<QSTASH_TOKEN>",
});

c.queue({ queueName: "<QUEUE_NAME>" }).pause()
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

client.queue.pause("<QUEUE_NAME>")
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/qstash-go"
)

func main() {
	client := qstash.NewClient("<QSTASH_TOKEN>")

	// error checking is omitted for brevity
	err := client.Queues().Pause("<QUEUE_NAME>")
}
```

--------------------------------

TITLE: Example: Successful Queue Retrieval Response
DESCRIPTION: Illustrates the JSON structure of a successful response when retrieving a queue, including queue metadata and status.

SOURCE: https://upstash.com/docs/qstash/api/queues/get.mdx

LANGUAGE: json
CODE:
```
{
 
  "createdAt": 1623345678001,
  "updatedAt": 1623345678001,
  "name": "my-queue",
  "parallelism" : 5, 
  "lag" : 100
}
```

--------------------------------

TITLE: Publish a Message to QStash using cURL
DESCRIPTION: This code snippet demonstrates how to publish a JSON message to QStash using cURL. It requires an Authorization Bearer token and sets the Content-Type header to application/json. The message body is a simple JSON object, and the target URL is the QStash publish endpoint followed by the recipient API URL. Two examples are provided: one with a generic placeholder URL and another with a specific requestcatcher.com URL for testing.

SOURCE: https://upstash.com/docs/qstash/overall/getstarted.mdx

LANGUAGE: bash
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://<your-api-url>'
```

LANGUAGE: bash
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer <QSTASH_TOKEN>' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://firstqstashmessage.requestcatcher.com/test'
```

--------------------------------

TITLE: Configure QStash Client Retry Policy
DESCRIPTION: This example illustrates how to customize the retry behavior of the QStash client by passing a `retry` object to the constructor. You can specify the number of `retries` and a custom `backoff` function to control the delay between retry attempts for requests sent to QStash. The default number of attempts is 6.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/gettingstarted.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Example Response: Rotate QStash Signing Keys
DESCRIPTION: An example of the successful JSON response received after rotating QStash signing keys, showing the current and next key values.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/rotate.mdx

LANGUAGE: json
CODE:
```
{ "current": "sig_123", "next": "sig_456" }
```

--------------------------------

TITLE: Example Output of Cloudflare Worker Project Initialization
DESCRIPTION: A log showing the interactive prompts and successful creation of a Cloudflare Worker project using `npm create cloudflare@latest`, including options for directory, application type, TypeScript, and Git.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: text
CODE:
```
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

TITLE: List URL Groups
DESCRIPTION: This snippet illustrates how to fetch all existing URL groups associated with the QStash account. It initializes the client and then uses the `list` method on the `urlGroups` service to get an array of all groups. The example then iterates through the returned array, logging the name and endpoints of each URL group.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const allUrlGroups = await client.urlGroups.list();
for (const urlGroup of allUrlGroups) {
  console.log(urlGroup.name, urlGroup.endpoints);
}
```

--------------------------------

TITLE: Get message logs from QStash
DESCRIPTION: Retrieve logs for all messages that have been published (filtering is also available).

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = await client.logs()
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.event.list()
# Async version is also available
```

--------------------------------

TITLE: Fetch QStash Events using Python Requests
DESCRIPTION: Example demonstrating how to initiate a GET request to the QStash Events API using Python's `requests` library. An Authorization Bearer token is required in the request headers.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: python
CODE:
```
import requests
headers = {
    'Authorization': 'Bearer <token>',
```

--------------------------------

TITLE: Resume Schedule with Python Client
DESCRIPTION: Example using the `qstash` Python client library to resume a QStash schedule. Shows how to initialize the client with a token and call the `schedule.resume` method.

SOURCE: https://upstash.com/docs/qstash/api/schedules/resume.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

client.schedule.resume("<SCHEDULE_ID>")
```

--------------------------------

TITLE: Install Project Dependencies
DESCRIPTION: Installs the necessary Node.js packages for the project, including `@upstash/qstash` for QStash integration and `@upstash/redis` for Redis database interaction. `@upstash/redis` can be substituted with any other database client.

SOURCE: https://upstash.com/docs/qstash/recipes/periodic-data-updates.mdx

LANGUAGE: bash
CODE:
```
npm install @upstash/qstash @upstash/redis
```

--------------------------------

TITLE: Resume Schedule with Go Client
DESCRIPTION: Example using the `github.com/upstash/qstash-go` client library to resume a QStash schedule in Go. Illustrates client initialization and calling the `Schedules().Resume` method.

SOURCE: https://upstash.com/docs/qstash/api/schedules/resume.mdx

LANGUAGE: go
CODE:
```
package main

import "github.com/upstash/qstash-go"

func main() {
	client := qstash.NewClient("<QSTASH_TOKEN>")

	// error checking is omitted for brevity
	err := client.Schedules().Resume("<SCHEDULE_ID>")
}
```

--------------------------------

TITLE: Fetch QStash Events using Node.js
DESCRIPTION: Example demonstrating how to make a GET request to the QStash Events API using JavaScript's `fetch` API in a Node.js environment. An Authorization Bearer token is required in the request headers.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: javascript
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/events", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

--------------------------------

TITLE: Send a custom header with a published message
DESCRIPTION: This example shows how to include custom HTTP headers when publishing a message. Custom headers can be used to pass additional metadata or instructions to the receiving endpoint.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

TITLE: Remove Schedule: Multi-language Request Examples
DESCRIPTION: Practical examples demonstrating how to send a DELETE request to the QStash API to remove a schedule using cURL, Node.js, Python, and Go. Each example includes the necessary authorization header setup with a bearer token.

SOURCE: https://upstash.com/docs/qstash/api/schedules/remove.mdx

LANGUAGE: curl
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/schedules/scd_123 \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: javascript
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/schedules/scd_123', {
  method: 'DELETE',
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.delete(
  'https://qstash.upstash.io/v2/schedules/scd_123', 
  headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/schedules/scd_123", nil)
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

--------------------------------

TITLE: Retrieve URL Group using Go HTTP Client
DESCRIPTION: Go language example showing how to construct an HTTP GET request to the QStash API for a URL Group, set the Authorization header, and handle the response.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/topics/my-url-group", nil)
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

--------------------------------

TITLE: Retrieve Flow Control Info with cURL
DESCRIPTION: Example cURL command to perform a GET request to the QStash API, retrieving information about a specific flow control key. This command requires a bearer token for authentication.

SOURCE: https://upstash.com/docs/qstash/api/flow-control/get.mdx

LANGUAGE: Shell
CODE:
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Example Response for Listing URL Groups
DESCRIPTION: An example JSON response demonstrating the structure of the data returned when successfully listing URL Groups from the /v2/topics endpoint. It shows an array containing URL Group objects with their `createdAt`, `updatedAt`, `name`, and `endpoints`.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/list.mdx

LANGUAGE: json
CODE:
```
[
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
  },
  // ...
]
```

--------------------------------

TITLE: Fetch QStash Events using cURL
DESCRIPTION: Example demonstrating how to make a GET request to the QStash Events API using the cURL command-line tool. An Authorization Bearer token is required in the request header.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: shell
CODE:
```
curl https://qstash.upstash.io/v2/events \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Retrieve URL Group using Python Requests
DESCRIPTION: Python example demonstrating how to use the `requests` library to get a URL Group from the QStash API, including handling the Authorization header.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/topics/my-url-group',
   headers=headers
)
```

--------------------------------

TITLE: Initialize AWS Lambda Project with CDK and QStash
DESCRIPTION: This snippet provides a sequence of bash commands to initialize an AWS Lambda project using the AWS CDK. It includes steps for creating a new directory, initializing a TypeScript CDK application, installing `esbuild` and `@upstash/qstash` dependencies, and setting up the basic directory structure for the lambda function.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: bash
CODE:
```
mkdir my-app
cd my-app
cdk init app -l typescript
npm i esbuild @upstash/qstash
mkdir lambda
touch lambda/index.ts
```

--------------------------------

TITLE: Retrieve QStash Events from API
DESCRIPTION: These code examples demonstrate how to make a GET request to the QStash API's `/v2/events` endpoint to fetch a list of events. Both snippets show how to set necessary headers for authentication and handle the API response.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: Python
CODE:
```
response = requests.get(
  'https://qstash.upstash.io/v2/events',
   headers=headers
)
```

LANGUAGE: Go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/events", nil)
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

--------------------------------

TITLE: Get a URL Group by Name (Python)
DESCRIPTION: This Python example shows how to retrieve a specific URL group by its name using the `get` method of the QStash client's `url_group` module. It then prints the name and associated endpoints of the retrieved group.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/url-groups.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
url_group = client.url_group.get("my-url-group")

print(url_group.name, url_group.endpoints)
```

--------------------------------

TITLE: Example: Pause Schedule using QStash Clients
DESCRIPTION: Illustrates how to programmatically pause an Upstash QStash schedule using `curl`, Node.js, Python, and Go clients. Each example demonstrates the necessary client initialization and the method call to pause a specified schedule.

SOURCE: https://upstash.com/docs/qstash/api/schedules/pause.mdx

LANGUAGE: sh
CODE:
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/pause \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
import { Client } from "@upstash/qstash";
/**
 * Import a fetch polyfill only if you are using node prior to v18.
 * This is not necessary for nextjs, deno or cloudflare workers.
 */
import "isomorphic-fetch";

const c = new Client({
  token: "<QSTASH_TOKEN>",
});

c.schedules.pause({
  schedule: "<SCHEDULE_ID>"
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

client.schedule.pause("<SCHEDULE_ID>")
```

LANGUAGE: go
CODE:
```
package main

import "github.com/upstash/qstash-go"

func main() {

	client := qstash.NewClient("<QSTASH_TOKEN>")

	// error checking is omitted for brevity
	err := client.Schedules().Pause("<SCHEDULE_ID>")
}
```

--------------------------------

TITLE: List all schedules
DESCRIPTION: Provides an example of fetching a comprehensive list of all schedules currently configured under the QStash account. The result is an array containing objects, each representing a schedule with its properties.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const allSchedules = await client.schedules.list();
console.log(allSchedules);
```

--------------------------------

TITLE: Initialize Go Project for Fly.io
DESCRIPTION: Commands to create a new directory, navigate into it, and initialize a Go module for a Fly.io application, setting up the basic project structure.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: bash
CODE:
```
mkdir flyio-go
cd flyio-go
go mod init flyio-go
```

--------------------------------

TITLE: QStash Get Message API Response Example
DESCRIPTION: Illustrates the expected JSON structure and content of a successful response when retrieving a message from the Upstash QStash API. It includes fields such as message ID, topic name, URL, HTTP method, headers, body, and creation timestamp.

SOURCE: https://upstash.com/docs/qstash/api/messages/get.mdx

LANGUAGE: json
CODE:
```
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

TITLE: Get a schedule by schedule ID
DESCRIPTION: Demonstrates how to retrieve the detailed information of a specific schedule using its unique identifier. The example then logs the cron expression associated with the fetched schedule.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const res = await client.schedules.get("scheduleId");
console.log(res.cron);
```

--------------------------------

TITLE: Example: Upsert a Queue via API Request
DESCRIPTION: Demonstrates how to make an API request to create or update a queue using cURL, Node.js, Python, and Go. Includes necessary headers for authorization and content type, along with the JSON request body.

SOURCE: https://upstash.com/docs/qstash/api/queues/upsert.mdx

LANGUAGE: sh curl
CODE:
```
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue" ,
    "parallelism" : 5,
  }'
```

LANGUAGE: js Node
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/queues/', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    "queueName": "my-queue" ,
    "parallelism" : 5,
  })
});
```

LANGUAGE: python Python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
}

json_data = {
    "queueName": "my-queue" ,
    "parallelism" : 5,
  }

response = requests.post(
  'https://qstash.upstash.io/v2/queues/',
  headers=headers,
  json=json_data
)
```

LANGUAGE: go Go
CODE:
```
var data = strings.NewReader(`{
    "queueName": "my-queue" ,
    "parallelism" : 5,
  }`)
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/queues/", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Curl Example: List All DLQ Messages
DESCRIPTION: Demonstrates how to make a basic HTTP GET request using curl to list all messages currently in the QStash Dead Letter Queue (DLQ), requiring a bearer token for authentication.

SOURCE: https://upstash.com/docs/qstash/api/dlq/listMessages.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Example Deno Deploy Log Output for Validated Webhook
DESCRIPTION: This snippet illustrates the expected log output in the Deno Deploy console after a QStash webhook is successfully received and its signature is validated by the deployed application. It confirms the server is listening and that the signature verification passed.

SOURCE: https://upstash.com/docs/qstash/quickstarts/deno-deploy.mdx

LANGUAGE: bash
CODE:
```
europe-west3isolate start time: 2.21 ms
Listening on http://localhost:8000/
The signature was valid
```

--------------------------------

TITLE: Get URL Group by name
DESCRIPTION: This example shows how to retrieve a specific URL group by its name using the `@upstash/qstash` client. After initializing the client, it calls the `get` method on the `urlGroups` service, passing the name of the desired group. The retrieved group object's name and endpoints are then logged to the console.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
const urlGroup = await urlGroups.get("urlGroupName");
console.log(urlGroup.name, urlGroup.endpoints);
```

--------------------------------

TITLE: Initialize Cloudflare Worker Project with C3
DESCRIPTION: Commands to create a new Cloudflare Worker project using `create-cloudflare-cli` (C3) for both npm and yarn package managers. This sets up the basic project structure and installs necessary tools like Wrangler.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: shell npm
CODE:
```
npm create cloudflare@latest
```

LANGUAGE: shell yarn
CODE:
```
yarn create cloudflare@latest
```

--------------------------------

TITLE: API Reference: Get a Queue
DESCRIPTION: Details the HTTP GET endpoint for retrieving a queue, including authentication, request parameters, and response fields.

SOURCE: https://upstash.com/docs/qstash/api/queues/get.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: GET https://qstash.upstash.io/v2/queues/{queueName}
Authentication: Bearer Token

Request Parameters:
  queueName:
    Type: string
    Required: true
    Description: The name of the queue to retrieve.

Response Fields (200 OK):
  createdAt:
    Type: int
    Required: true
    Description: The creation time of the queue. UnixMilli
  updatedAt:
    Type: int
    Required: true
    Description: The update time of the queue. UnixMilli
  name:
    Type: string
    Required: true
    Description: The name of the queue.
  parallelism:
    Type: int
    Required: true
    Description: The number of parallel consumers consuming from the queue.
  lag:
    Type: int
    Required: true
    Description: The number of unprocessed messages that exist in the queue.
```

--------------------------------

TITLE: Create QStash Schedule with cURL, Node.js, Python, and Go
DESCRIPTION: Practical code examples demonstrating how to create a scheduled message using the QStash API. These examples show how to make a POST request to the schedules endpoint, including the Authorization header with a Bearer token and the Upstash-Cron header for defining the schedule.

SOURCE: https://upstash.com/docs/qstash/api/schedules/create.mdx

LANGUAGE: curl
CODE:
```
curl -XPOST https://qstash.upstash.io/v2/schedules/https://www.example.com/endpoint \
  -H "Authorization: Bearer <token>" \
  -H "Upstash-Cron: */5 * * * *"
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/schedules/https://www.example.com/endpoint', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer <token>',
    'Upstash-Cron': '*/5 * * * *'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Upstash-Cron': '*/5 * * * *'
}

response = requests.post(
  'https://qstash.upstash.io/v2/schedules/https://www.example.com/endpoint',
   headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/schedules/https://www.example.com/endpoint", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Upstash-Cron", "*/5 * * * *")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Install Upstash QStash Library
DESCRIPTION: Command to install the `@upstash/qstash` package using npm, which provides the necessary tools for integrating QStash webhook reception and signature verification in your Cloudflare Worker.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: bash
CODE:
```
npm install @upstash/qstash
```

--------------------------------

TITLE: Resume Schedule with Node.js Client
DESCRIPTION: Example using the `@upstash/qstash` Node.js client library to programmatically resume a QStash schedule. Demonstrates client initialization and calling the `schedules.resume` method.

SOURCE: https://upstash.com/docs/qstash/api/schedules/resume.mdx

LANGUAGE: js
CODE:
```
import { Client } from "@upstash/qstash";
/**
 * Import a fetch polyfill only if you are using node prior to v18.
 * This is not necessary for nextjs, deno or cloudflare workers.
 */
import "isomorphic-fetch";

const c = new Client({
  token: "<QSTASH_TOKEN>",
});

c.schedules.resume({
  schedule: "<SCHEDULE_ID>"
});
```

--------------------------------

TITLE: Retrieve URL Group using Node.js Fetch API
DESCRIPTION: Node.js example using the Fetch API to make a GET request to the QStash API for retrieving a URL Group, including setting the Authorization header for authentication.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/topics/my-url-group', {
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

--------------------------------

TITLE: QStash Flow Control API Reference
DESCRIPTION: Documents the GET /v2/flowControl/{flowControlKey} endpoint for retrieving flow control information, detailing the required path parameters, authentication method, and the structure of the successful response.

SOURCE: https://upstash.com/docs/qstash/api/flow-control/get.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: GET https://qstash.upstash.io/v2/flowControl/{flowControlKey}
Authentication: Bearer Token

Request Parameters:
  flowControlKey (string): The key of the flow control. See the flow control for more details.

Response Fields:
  flowControlKey (string): The key of the flow control.
  waitListSize (integer): The number of messages in the wait list that waits for `parallelism` set in the flow control.
```

--------------------------------

TITLE: Example Delivered Message Body and Headers
DESCRIPTION: Illustrates the structure of the JSON body and HTTP headers that QStash would deliver to the destination API after successfully publishing a message with custom headers. This shows how the original message and forwarded headers are presented.

SOURCE: https://upstash.com/docs/qstash/howto/publishing.mdx

LANGUAGE: json
CODE:
```
// body
{ "hello": "world" }

// headers
My-Header:      my-value
Content-Type:   application/json
```

--------------------------------

TITLE: Example JSON Response for Listing QStash Schedules
DESCRIPTION: Illustrates a sample successful JSON response (HTTP 200 OK) when listing QStash schedules, showing the structure and typical values for a single schedule object within the returned array.

SOURCE: https://upstash.com/docs/qstash/api/schedules/list.mdx

LANGUAGE: json
CODE:
```
[
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
]
```

--------------------------------

TITLE: Schedule a message to run once a day using cron
DESCRIPTION: This example demonstrates how to schedule a message to be published repeatedly based on a cron expression. The message will be sent to the specified destination once every day at midnight (0 0 * * *).

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Cron: 0 0 * * *" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "0 0 * * *",
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="0 0 * * *",
)
# Async version is also available
```

--------------------------------

TITLE: Publish messages in a batch using QStash
DESCRIPTION: Publish multiple messages in a single request.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
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

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

TITLE: Configure Retry Policy for QStash Client
DESCRIPTION: This code snippet shows how to customize the retry behavior for the QStash client by passing a `retry` dictionary to the constructor. You can specify the number of retries and a custom backoff function. This configuration applies to the client's attempts to send requests to QStash, not QStash's internal message retries.

SOURCE: https://upstash.com/docs/qstash/sdks/py/gettingstarted.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Bundle and Deploy Lambda Function with Makefile
DESCRIPTION: This Makefile script automates the process of bundling a Python Lambda function along with its dependencies (specifically PyJWT) into a deployable zip file. It first cleans any previous build artifacts, then installs Python packages into a distribution directory, copies the main Lambda function file, zips the entire contents of the distribution directory, and finally moves the resulting zip file to the root for easy upload to AWS.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: yaml
CODE:
```
zip:
    rm -rf dist
	pip3 install --target ./dist pyjwt
	cp lambda_function.py ./dist/lambda_function.py
	cd dist && zip -r lambda.zip .
	mv ./dist/lambda.zip ./
```

--------------------------------

TITLE: Bulk Cancel Messages Request Examples
DESCRIPTION: Examples demonstrating how to send a DELETE request to bulk cancel messages using cURL, Node.js, Python, and Go. These examples show how to include specific message IDs in the request body.

SOURCE: https://upstash.com/docs/qstash/api/messages/bulk-cancel.mdx

LANGUAGE: curl
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/messages/ \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <token>" \
  -d '{"messageIds": ["msg_id_1", "msg_id_2", "msg_id_3"]}'
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/messages', {
  method: 'DELETE',
  headers: {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
      messageIds: [
          "msg_id_1",
          "msg_id_2",
          "msg_id_3"
      ]
  })
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json'
}

data = {
  "messageIds": [
    "msg_id_1",
    "msg_id_2",
    "msg_id_3"
  ]
}

response = requests.delete(
  'https://qstash.upstash.io/v2/messages',
  headers=headers,
  json=data
)
```

LANGUAGE: go
CODE:
```
var data = strings.NewReader(`{
  "messageIds": [
    "msg_id_1",
    "msg_id_2",
    "msg_id_3"
  ]
}`)
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/messages", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Configure Helicone Analytics for Custom LLM Models in QStash
DESCRIPTION: This TypeScript example demonstrates how to publish a JSON payload to QStash, configuring it to send LLM usage analytics to Helicone. It shows the setup for a custom LLM provider, including how to pass the Helicone API key within the `api.analytics` field.

SOURCE: https://upstash.com/docs/qstash/integrations/llm.mdx

LANGUAGE: TypeScript
CODE:
```
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

TITLE: Retrieve URL Group using cURL
DESCRIPTION: Example cURL command to fetch a URL Group from the QStash API, demonstrating the required Authorization header for authentication.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/topics/my-url-group \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Expose Local Application with localtunnel.me
DESCRIPTION: Command to start a localtunnel.me tunnel, exposing a local application running on a specified port (e.g., 3000) to the internet. This provides a public URL for QStash to send requests to.

SOURCE: https://upstash.com/docs/qstash/howto/local-tunnel.mdx

LANGUAGE: bash
CODE:
```
npx localtunnel --port 3000
```

--------------------------------

TITLE: Remove Queue Request Examples
DESCRIPTION: Practical code examples demonstrating how to send a DELETE request to the Upstash QStash API to remove a queue using cURL, Node.js, Python, and Go.

SOURCE: https://upstash.com/docs/qstash/api/queues/remove.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/queue/my-queue', {
  method: "DELETE",
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.delete(
  'https://qstash.upstash.io/v2/queue/my-queue',
   headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/queue/my-queue", nil)
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

--------------------------------

TITLE: List All URL Groups (Python)
DESCRIPTION: This Python example demonstrates how to fetch all URL groups associated with the QStash account using the `list` method of the QStash client's `url_group` module. It then iterates through the retrieved groups and prints their names and endpoints.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/url-groups.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
all_url_groups = client.url_group.list()

for url_group in all_url_groups:
    print(url_group.name, url_group.endpoints)
```

--------------------------------

TITLE: Successful Response Example for List QStash Queues
DESCRIPTION: An example of a successful JSON response (HTTP 200 OK) when listing QStash queues, showing the structure of an array containing queue objects with their `createdAt`, `updatedAt`, `name`, `parallelism`, and `lag` properties.

SOURCE: https://upstash.com/docs/qstash/api/queues/list.mdx

LANGUAGE: json
CODE:
```
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

TITLE: Deploy Application to Vercel using CLI
DESCRIPTION: Commands to install the Vercel command-line interface globally and then deploy the Next.js application. This step makes the custom API endpoint publicly accessible, allowing QStash to invoke it.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: bash
CODE:
```
npm install -g vercel
vercel
```

--------------------------------

TITLE: Publish to URL with Delay, Headers, and Body (TypeScript)
DESCRIPTION: This example demonstrates how to publish a JSON message to a specific URL using the QStash client. It includes a 3-second delay, custom headers, and a JSON body.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  headers: { "test-header": "test-value" },
  delay: "3s",
});
```

--------------------------------

TITLE: Understand Upstash-Retried Header Values
DESCRIPTION: Shows examples of the 'Upstash-Retried' HTTP header, which QStash adds to requests sent to your API. This header indicates the number of times the current request has been retried, starting from 0 for the first attempt.

SOURCE: https://upstash.com/docs/qstash/features/retry.mdx

LANGUAGE: HTTP
CODE:
```
Upstash-Retried: 0 // This is the first attempt
Upstash-Retried: 1 // This request has been sent once before and now is the second attempt
Upstash-Retried: 2 // This request has been sent twice before and now is the third attempt
```

--------------------------------

TITLE: Start ngrok HTTP Tunnel
DESCRIPTION: Command to initiate an ngrok HTTP tunnel, forwarding public traffic to a specified local port (e.g., 3000). The output displays the session status, account details, and the public forwarding URL that can be used by QStash.

SOURCE: https://upstash.com/docs/qstash/howto/local-tunnel.mdx

LANGUAGE: bash
CODE:
```
$ ngrok http 3000



Session Status                online
Account                       Andreas Thomas (Plan: Free)
Version                       3.1.0
Region                        Europe (eu)
Latency                       -
Web Interface                 http://127.0.0.1:4040
Forwarding                    https://e02f-2a02-810d-af40-5284-b139-58cc-89df-b740.eu.ngrok.io -> http://localhost:3000

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```

--------------------------------

TITLE: Publish a message with a specified delay
DESCRIPTION: This example demonstrates how to add a delay to a published message. QStash will hold the message for the specified duration (e.g., 5 minutes) before sending it to the target endpoint.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 5m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  delay: 300,
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Enqueue Message with Go (net/http)
DESCRIPTION: Go language example demonstrating how to construct and send an HTTP POST request to enqueue a message to QStash. It includes setting request headers for authorization and various Upstash message properties.

SOURCE: https://upstash.com/docs/qstash/api/enqueue.mdx

LANGUAGE: go
CODE:
```
var data = strings.NewReader(`{"message":"Hello, World!"}`)
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
req.Header.Set("Upstash-Method", "POST")
req.Header.Set("Upstash-Retries", "3")
req.Header.Set("Upstash-Forward-Custom-Header", "custom-value")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Bulk Cancel Messages Response Example
DESCRIPTION: An example of the JSON response received after successfully performing a bulk message cancellation, indicating the number of messages cancelled.

SOURCE: https://upstash.com/docs/qstash/api/messages/bulk-cancel.mdx

LANGUAGE: json
CODE:
```
{
  "cancelled": 10
}
```

--------------------------------

TITLE: Create AWS Lambda Project Directory and File
DESCRIPTION: This snippet demonstrates how to set up the basic directory structure for an AWS Lambda project, creating a new folder and an empty `lambda_function.py` file.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: bash
CODE:
```
mkdir aws-lambda
cd aws-lambda
touch lambda_function.py
```

--------------------------------

TITLE: Original Webhook Endpoint URL Example
DESCRIPTION: This snippet illustrates a typical webhook endpoint URL that a service would call directly. It serves as a baseline to demonstrate how QStash intercepts and manages these calls.

SOURCE: https://upstash.com/docs/qstash/howto/webhook.mdx

LANGUAGE: HTTP
CODE:
```
https://example.com/api/webhook
```

--------------------------------

TITLE: Cancel QStash Message Code Examples
DESCRIPTION: Practical code examples demonstrating how to programmatically cancel a QStash message using cURL, Node.js, Python, and Go, by sending a DELETE request to the API endpoint.

SOURCE: https://upstash.com/docs/qstash/api/messages/cancel.mdx

LANGUAGE: sh
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/messages/msg_123 \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/messages/msg_123', {
  method: 'DELETE',
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.delete(
  'https://qstash.upstash.io/v2/messages/msg_123', 
  headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/messages/msg_123", nil)
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

--------------------------------

TITLE: Retrieve DLQ Message with cURL
DESCRIPTION: Example cURL command to fetch a message from the QStash Dead Letter Queue using a specific DLQ ID and a bearer token for authentication. Replace `<token>` with your actual QStash API token.

SOURCE: https://upstash.com/docs/qstash/api/dlq/getMessage.mdx

LANGUAGE: sh
CODE:
```
curl -X GET https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: GET /v2/topics API Documentation
DESCRIPTION: Detailed API documentation for the GET /v2/topics endpoint, which retrieves a list of all URL Groups. Authentication is required using a Bearer token. The response provides an array of URL Group objects, each containing creation/update timestamps, name, and a list of associated endpoints with their names and URLs.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/list.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: GET https://qstash.upstash.io/v2/topics
Authentication: Bearer Token

Request Parameters:
  None

Response (200 OK): Array of URL Group Objects
  URL Group Object Properties:
    createdAt: int (required)
      Description: The creation time of the URL Group. UnixMilli
    updatedAt: int (required)
      Description: The update time of the URL Group. UnixMilli
    name: string (required)
      Description: The name of the URL Group.
    endpoints: Array of Endpoint Objects (required)
      Endpoint Object Properties:
        name: string (required)
          Description: The name of the endpoint.
        url: string (required)
          Description: The URL of the endpoint
```

--------------------------------

TITLE: Publish messages to a FIFO queue with QStash
DESCRIPTION: By default, messages are published concurrently. With a queue, you can enqueue messages in FIFO order.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
            'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' 
            -d '{"message":"Hello, World!"}'
```

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

TITLE: Publish with Callback URL and Custom Method (TypeScript)
DESCRIPTION: [Callbacks](/qstash/features/callbacks) are useful for long running functions. Here, QStash will return the response of the publish request to the callback URL.

We also change the `method` to `GET` in this use case so QStash will make a `GET` request to the `url`. The default is `POST`.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Fetch QStash Logs via GET Request
DESCRIPTION: This snippet demonstrates how to retrieve logs from the QStash API using a GET request. It requires an Authorization header with a bearer token for authentication. The response contains a list of log events.

SOURCE: https://upstash.com/docs/qstash/api/logs/list.mdx

LANGUAGE: python
CODE:
```
response = requests.get(
  'https://qstash.upstash.io/v2/logs',
   headers=headers
)
```

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/logs", nil)
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

--------------------------------

TITLE: QStash API: Get Signing Keys Endpoint
DESCRIPTION: Details the QStash API endpoint for retrieving signing keys, including the HTTP method, URL, authentication requirements, and the structure of the expected response fields.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/get.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://qstash.upstash.io/v2/keys
Auth Method: bearer
```

LANGUAGE: APIDOC
CODE:
```
Response Fields:
  current (string, required): Your current signing key.
  next (string, required): The next signing key.
```

--------------------------------

TITLE: API Reference: Get Schedule by ID
DESCRIPTION: Documents the REST API endpoint for retrieving a schedule, including request parameters, authentication, and the structure of the successful response.

SOURCE: https://upstash.com/docs/qstash/api/schedules/get.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: GET https://qstash.upstash.io/v2/schedules/{scheduleId}
Authentication: Bearer Token

Request Parameters:
- scheduleId (string, required): The id of the schedule to retrieve.

Response Fields (200 OK):
- createdAt (int, required): The creation time of the object. UnixMilli
- scheduleId (string, required): The id of the schedule.
- cron (string, required): The cron expression used to schedule the message.
- callerIP (string, required): IP address where this schedule created from.
- destination (string, required): Url or URL Group name
- method (string, required): The HTTP method to use for the message.
- header (Record<string, string[]>, required): The headers of the message.
- body (string, required): The body of the message.
- retries (int, optional): The number of retries that should be attempted in case of delivery failure.
- delay (int, optional): The delay in seconds before the message is delivered.
- callback (string, optional): The url where we send a callback to after the message is delivered
```

--------------------------------

TITLE: API Reference: List QStash Logs
DESCRIPTION: Detailed API documentation for the GET /v2/logs endpoint, including authentication method and all available query parameters for filtering and paginating message logs.

SOURCE: https://upstash.com/docs/qstash/api/logs/list.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: GET https://qstash.upstash.io/v2/logs
Authentication: bearer

Query Parameters:
- cursor (string): By providing a cursor you can paginate through all of the logs.
- messageId (string): Filter logs by message id.
- state (string): Filter logs by state.
  Possible Values:
    - CREATED: The message has been accepted and stored in QStash
    - ACTIVE: The task is currently being processed by a worker.
    - RETRY: The task has been scheduled to retry.
    - ERROR: The execution threw an error and the task is waiting to be retried or failed.
    - IN_PROGRESS: The task is in one of ACTIVE, RETRY or ERROR state.
    - DELIVERED: The message was successfully delivered.
    - FAILED: The task has errored too many times or encountered an error that it cannot recover from.
    - CANCEL_REQUESTED: The cancel request from the user is recorded.
    - CANCELLED: The cancel request from the user is honored.
- url (string): Filter logs by url.
- topicName (string): Filter logs by URL Group (topic) name.
- scheduleId (string): Filter logs by schedule id.
- queueName (string): Filter logs by queue name.
- fromDate (number): Filter logs by starting date, in milliseconds (Unix timestamp). This is inclusive.
- toDate (number): Filter logs by ending date, in milliseconds (Unix timestamp). This is inclusive.
- count (number): The number of logs to return. Default and max is 1000.
- order (string): The sorting order of logs by timestamp. Valid values are "earliestFirst" and "latestFirst". The default is "latestFirst".
```

--------------------------------

TITLE: API Reference: Get URL Group
DESCRIPTION: Detailed API documentation for retrieving a URL Group, including the HTTP method, endpoint path, authentication requirements, request parameters, and the structure of the expected response fields.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/get.mdx

LANGUAGE: APIDOC
CODE:
```
API: GET https://qstash.upstash.io/v2/topics/{urlGroupName}
Authentication: bearer

Request Parameters:
  urlGroupName:
    Type: string
    Required: true
    Description: The name of the URL Group (topic) to retrieve.

Response Fields:
  createdAt:
    Type: int
    Required: true
    Description: The creation time of the URL Group. UnixMilli
  updatedAt:
    Type: int
    Required: true
    Description: The update time of the URL Group. UnixMilli
  name:
    Type: string
    Required: true
    Description: The name of the URL Group.
  endpoints:
    Type: Array
    Required: true
    Description: A list of endpoints associated with the URL Group.
    Properties:
      name:
        Type: string
        Required: false
        Description: The name of the endpoint.
      url:
        Type: string
        Required: true
        Description: The URL of the endpoint.
```

--------------------------------

TITLE: Example: Add Endpoints to QStash URL Group
DESCRIPTION: Demonstrates how to make a POST request to add or update endpoints in a QStash URL Group using various programming languages. Each example includes the necessary authentication header and JSON request body structure.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/add-endpoint.mdx

LANGUAGE: curl
CODE:
```
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

LANGUAGE: javascript
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    'endpoints': [
      {
        'name': 'endpoint1',
        'url': 'https://example.com'
      },
      {
        'name': 'endpoint2',
        'url': 'https://somewhere-else.com'
      }
    ]
  })
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
}

json_data = {
    'endpoints': [
        {
            'name': 'endpoint1',
            'url': 'https://example.com',
        },
        {
            'name': 'endpoint2',
            'url': 'https://somewhere-else.com',
        },
    ],
}

response = requests.post(
  'https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints',
  headers=headers,
  json=json_data
)
```

LANGUAGE: go
CODE:
```
var data = strings.NewReader(`{
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
}`)
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: QStash Batch API Response Example
DESCRIPTION: Example JSON response from the QStash batch API, showing the message IDs and URLs for successfully processed messages. The response structure varies based on the message type (e.g., URL group vs. direct URL).

SOURCE: https://upstash.com/docs/qstash/api/messages/batch.mdx

LANGUAGE: json
CODE:
```
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
  },
  {
    "messageId": "msg_..."
  }
]
```

--------------------------------

TITLE: Retrieve All QStash Events with Pagination using Cursor
DESCRIPTION: This Python example demonstrates how to fetch all events from QStash, managing pagination using a cursor. Since events can be numerous, they are paginated. The code iteratively fetches event pages, appending them to a list, until the cursor indicates no more pages are available.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/events.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Send QStash Publish Message Request Examples
DESCRIPTION: Demonstrates how to send a POST request to the QStash publish endpoint using various programming languages, including setting authorization, content type, and custom Upstash headers for message control and forwarding.

SOURCE: https://upstash.com/docs/qstash/api/publish.mdx

LANGUAGE: curl
CODE:
```
curl -X POST "https://qstash.upstash.io/v2/publish/https://www.example.com" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Method: POST" \
  -H "Upstash-Delay: 10s" \
  -H "Upstash-Retries: 3" \
  -H "Upstash-Forward-Custom-Header: custom-value" \
  -d '{"message":"Hello, World!"}'
```

LANGUAGE: Node
CODE:
```
const response = await fetch(
  "https://qstash.upstash.io/v2/publish/https://www.example.com",
  {
    method: "POST",
    headers: {
      Authorization: "Bearer <token>",
      "Content-Type": "application/json",
      "Upstash-Method": "POST",
      "Upstash-Delay": "10s",
      "Upstash-Retries": "3",
      "Upstash-Forward-Custom-Header": "custom-value"
    },
    body: JSON.stringify({
      message: "Hello, World!"
    })
  }
);
```

LANGUAGE: Python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
    'Upstash-Method': 'POST',
    'Upstash-Delay': '10s',
    'Upstash-Retries': '3',
    'Upstash-Forward-Custom-Header': 'custom-value'
}

json_data = {
    'message': 'Hello, World!',
}

response = requests.post(
  'https://qstash.upstash.io/v2/publish/https://www.example.com',
   headers=headers,
   json=json_data
)
```

LANGUAGE: Go
CODE:
```
var data = strings.NewReader(`{"message":"Hello, World!"}`)
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/publish/https://www.example.com", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
req.Header.Set("Upstash-Method", "POST")
req.Header.Set("Upstash-Delay", "10s")
req.Header.Set("Upstash-Retries", "3")
req.Header.Set("Upstash-Forward-Custom-Header", "custom-value")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Configure Pipedream Workflow with QStash Topic Trigger
DESCRIPTION: This guide details the steps to set up a Pipedream workflow that is triggered by messages published to a QStash topic. It covers creating a QStash topic, configuring the Pipedream trigger, connecting QStash, and selecting the topic to listen for messages.

SOURCE: https://upstash.com/docs/qstash/integrations/pipedream.mdx

LANGUAGE: APIDOC
CODE:
```
1. Create a Topic in QStash:
   - If not already done, create a Topic in the QStash dashboard.

2. Create a new Pipedream workflow:
   - Sign into Pipedream and create a new workflow.

3. Add QStash Topic Message as a trigger:
   - In the workflow Trigger, search for 'QStash' and select the 'Create Topic Endpoint' trigger.
   - Connect your QStash account by retrieving your token from the QStash dashboard.
   - Click the 'Topic' prop and select a specific topic to listen for new messages.
   - Click 'Continue'. Pipedream will create a unique HTTP endpoint and add it to your QStash topic.

4. Test with a sample message:
   - Use the Request Builder in the QStash dashboard to publish a test message to your topic.
   - Alternatively, use the 'Create topic message' action in a separate Pipedream workflow to send a message.

5. Add additional steps:
   - Click the plus icon beneath the Trigger step.
   - Build a workflow with pre-built components or Node.js/Python code steps.

6. Deploy your Pipedream workflow:
   - Click the 'Deploy' button in the top right of your Pipedream workflow. Your deployed workflow will then process new messages to your QStash topic.
```

--------------------------------

TITLE: QStash CLI `dev` Command Options
DESCRIPTION: This section documents the available command-line options for the `qstash dev` command, including parameters for configuring the server's port and user quota type, along with their corresponding environment variables and default values.

SOURCE: https://upstash.com/docs/qstash/howto/local-development.mdx

LANGUAGE: APIDOC
CODE:
```
$ ./qstash dev --help
Usage of dev:
  -port int
        The port to start HTTP server at [env QSTASH_DEV_PORT] (default 8080)
  -quota string
        The quota of users [env QSTASH_DEV_QUOTA] (default "payg")
```

--------------------------------

TITLE: Create a QStash Schedule for a URL Group (Hourly)
DESCRIPTION: Shows how to create a schedule targeting a named URL group instead of a direct URL, using the QStash Python SDK. The example cron expression sets it to run hourly.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.schedule.create(
    destination="my-url-group",
    cron="0 * * * *",
)
```

--------------------------------

TITLE: Next.js QStash Background Job Implementation
DESCRIPTION: This comprehensive example illustrates the full lifecycle of a background job using QStash within a Next.js application. It includes the client-side initiation, the server-side API responsible for publishing the job to QStash, and the dedicated API endpoint that executes the long-running background task.

SOURCE: https://upstash.com/docs/qstash/features/background-jobs.mdx

LANGUAGE: tsx
CODE:
```
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

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: typescript
CODE:
```
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

TITLE: Resume Schedule with cURL
DESCRIPTION: Example cURL command to send a POST request to the QStash API to resume a specific schedule. Requires an Authorization Bearer token.

SOURCE: https://upstash.com/docs/qstash/api/schedules/resume.mdx

LANGUAGE: sh
CODE:
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/resume \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: JSON Response Example: Successful DLQ Message Listing
DESCRIPTION: Provides an example of a successful JSON response (HTTP 200 OK) when listing messages from the QStash Dead Letter Queue (DLQ), showing the structure of the 'messages' array with a sample message object.

SOURCE: https://upstash.com/docs/qstash/api/dlq/listMessages.mdx

LANGUAGE: json
CODE:
```
{
  "messages": [
    {
      "messageId": "msg_123",
      "topicId": "tpc_123",
      "url":"https://example.com",
      "method": "POST",
      "header": {
        "My-Header": ["my-value"]
      },
      "body": "{\"foo\":\"bar\"}",
      "createdAt": 1620000000000,
      "state": "failed"
    }
  ]
}
```

--------------------------------

TITLE: Initialize QStash Receiver with Signing Keys
DESCRIPTION: Instantiates the `Receiver` class, providing it with the `currentSigningKey` and `nextSigningKey` retrieved from the Cloudflare Worker's environment variables. This setup prepares the receiver for signature validation.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: ts
CODE:
```
const receiver = new Receiver({
  currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
  nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
});
```

--------------------------------

TITLE: Run QStash Development Server with Docker
DESCRIPTION: This snippet provides commands to pull the QStash CLI Docker image from the public AWS ECR repository and run it. It includes port mapping to expose the development server on a local port.

SOURCE: https://upstash.com/docs/qstash/howto/local-development.mdx

LANGUAGE: shell
CODE:
```
// Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

// Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev
```

--------------------------------

TITLE: Set callback URL for QStash messages
DESCRIPTION: Receive a response from the endpoint and send it to the specified callback URL. If the endpoint does not return a response, QStash will send it to the failure callback URL.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

TITLE: QStash API: Create Schedule Endpoint Reference
DESCRIPTION: Comprehensive API documentation for the QStash 'Create Schedule' endpoint, detailing the HTTP method, URL structure, authentication, request parameters (path and headers), and the expected JSON response format.

SOURCE: https://upstash.com/docs/qstash/api/schedules/create.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/v2/schedules/{destination}
Authentication: Bearer Token

Request Parameters:
- Path Parameter:
  - destination (string, required):
    Description: Destination can either be a topic name or id that you configured in the Upstash console or a valid url where the message gets sent to. If the destination is a URL, make sure the URL is prefixed with a valid protocol (http:// or https://).
- Header Parameters:
  - Upstash-Cron (string, required):
    Description: Cron allows you to send this message periodically on a schedule. Add a Cron expression and we will requeue this message automatically whenever the Cron expression triggers. Note: it can take up to 60 seconds until the schedule is registered on an available qstash node.
    Example: "*/5 * * * *"
  - Upstash-Delay (string, optional):
    Description: Delay the message delivery. Delay applies to the delivery of the scheduled messages. Format for this header is a number followed by duration abbreviation, like "10s". Available durations are s (seconds), m (minutes), h (hours), d (days).
    Example: "50s" | "3m" | "10h" | "1d"
  - Upstash-Schedule-Id (string, optional):
    Description: Assign a schedule id to the created schedule. This header allows you to set the schedule id yourself instead of QStash assigning a random id. If a schedule with the provided id exists, the settings of the existing schedule will be updated with the new settings.

Response:
- scheduleId (string, required):
  Description: The unique id of this schedule. You can use it to delete the schedule later.

Response Example (200 OK):
{
  "scheduleId": "scd_1234"
}
```

--------------------------------

TITLE: Publish to a URL with a 3 second delay and headers/body
DESCRIPTION: This snippet shows how to publish a JSON message to a specified URL using the QStash client. It includes examples of adding a delay, custom headers, and a JSON body. The message ID of the published message is then printed.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Publish a method with a callback URL
DESCRIPTION: This snippet shows how to configure callback URLs for a QStash message. It sets a primary callback URL for successful responses and a failure callback URL for errors. Additionally, it demonstrates changing the HTTP method of the request to 'GET' instead of the default 'POST'.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Batching Messages to QStash Queues
DESCRIPTION: This snippet demonstrates how to send a batch of messages to different QStash queues, optionally specifying a destination URL for each. It provides examples for cURL, TypeScript, and Python, showing how to use the `queue` or `queueName` parameter in batch requests.

SOURCE: https://upstash.com/docs/qstash/features/batch.mdx

LANGUAGE: cURL
CODE:
```
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

LANGUAGE: TypeScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: QStash Get Message API Endpoint Definition
DESCRIPTION: Defines the HTTP method, endpoint, authentication, and required parameters for retrieving a message by its ID from the Upstash QStash API. It also includes an important warning about message transience.

SOURCE: https://upstash.com/docs/qstash/api/messages/get.mdx

LANGUAGE: APIDOC
CODE:
```
Method: GET
Endpoint: https://qstash.upstash.io/v2/messages/{messageId}
Auth Method: bearer
Parameters:
  messageId (string, required): The id of the message to retrieve.
Warning: Messages are removed from the database shortly after they're delivered. This endpoint is intended to be used for accessing messages that are in the process of being delivered/retried.
```

--------------------------------

TITLE: Example JWT Header for Upstash-Signature
DESCRIPTION: Illustrates the typical structure of the JSON Web Token (JWT) header found in the `Upstash-Signature` for request signing, specifying the cryptographic algorithm and token type.

SOURCE: https://upstash.com/docs/qstash/features/security.mdx

LANGUAGE: JSON
CODE:
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

--------------------------------

TITLE: Create a QStash Schedule with Callbacks (Hourly)
DESCRIPTION: Illustrates creating an hourly schedule with the QStash Python SDK, including optional callback and failure callback URLs to handle results and errors from the scheduled execution.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Control Retry Delay with Retry-After Header Examples
DESCRIPTION: Provides examples of how to use the 'Retry-After' HTTP header in your API response to explicitly control when QStash should next retry a message. This header supports values in seconds, RFC1123 date format, or duration format.

SOURCE: https://upstash.com/docs/qstash/features/retry.mdx

LANGUAGE: HTTP
CODE:
```
Retry-After: 0                             // Next retry will be scheduled immediately without any delay.
Retry-After: 10                            // Next retry will be scheduled after a 10-second delay.
Retry-After: 6m5s                          // Next retry will be scheduled after 6 minutes 5 seconds delay.
Retry-After: Sun, 27 Jun 2024 12:16:24 GMT // Next retry will be scheduled for the specified date, within the allowable limits.
```

--------------------------------

TITLE: Publish with Content-Based Deduplication (TypeScript)
DESCRIPTION: This example demonstrates publishing a message with content-based deduplication enabled. This feature prevents duplicate messages from being processed based on their content.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  contentBasedDeduplication: true,
});
```

--------------------------------

TITLE: Publish to a URL group with a 3 second delay and headers/body
DESCRIPTION: This example demonstrates publishing a JSON message to a predefined URL group in QStash. It illustrates how to include a delay, custom headers, and a JSON body. The response, which is an array of messages for each URL in the group, is then processed to print the message ID of the first message.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Retrieve QStash Signing Keys (Python)
DESCRIPTION: This snippet demonstrates how to retrieve the current and next signing keys for your QStash account using the Python SDK. It initializes the QStash client with your token and then calls the `signing_key.get()` method to fetch the keys. The retrieved keys are then printed to the console.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/keys.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
signing_key = client.signing_key.get()

print(signing_key.current, signing_key.next)
```

--------------------------------

TITLE: Configure Message Retries on Publish (TypeScript)
DESCRIPTION: This example demonstrates how to configure the number of retries for a published message. The maximum number of retries depends on your QStash plan.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  retries: 1,
});
```

--------------------------------

TITLE: Enqueue Message with Python (Requests Library)
DESCRIPTION: Python example using the `requests` library to send a JSON message to a QStash queue. It shows how to configure headers for authentication, content type, and Upstash-specific message handling.

SOURCE: https://upstash.com/docs/qstash/api/enqueue.mdx

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
    'Upstash-Method': 'POST',
    'Upstash-Retries': '3',
    'Upstash-Forward-Custom-Header': 'custom-value',
}

json_data = {
    'message': 'Hello, World!',
}

response = requests.post(
  'https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com',
   headers=headers,
   json=json_data
)
```

--------------------------------

TITLE: QStash Logs API Response Example (200 OK)
DESCRIPTION: This JSON snippet illustrates a successful 200 OK response from the QStash logs API. It includes a 'cursor' for pagination and an 'events' array, where each object represents a log event with details such as time, message ID, state, URL, headers, and body.

SOURCE: https://upstash.com/docs/qstash/api/logs/list.mdx

LANGUAGE: json
CODE:
```
{
  "cursor": "1686652644442-12",
  "events":[
    {
      "time": "1686652644442",
      "messageId": "msg_123",
      "state": "delivered",
      "url": "https://example.com",
      "header": { "Content-Type": [ "application/x-www-form-urlencoded" ] },
      "body": "bWVyaGFiYSBiZW5pbSBhZGltIHNhbmNhcg=="
    }
  ]
}
```

--------------------------------

TITLE: Delete Multiple DLQ Messages Request Examples
DESCRIPTION: Examples demonstrating how to send a DELETE request to remove multiple messages from the DLQ using various programming languages and cURL. The request body requires an array of `dlqIds`.

SOURCE: https://upstash.com/docs/qstash/api/dlq/deleteMessages.mdx

LANGUAGE: sh
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/dlq \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
     "dlqIds": ["11111-0", "22222-0", "33333-0"]
    }'
```

LANGUAGE: js
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/dlq", {
  method: "DELETE",
  headers: {
    Authorization: "Bearer <token>",
    "Content-Type": "application/json",
  },
  body: {
    dlqIds: [
      "11111-0",
      "22222-0",
      "33333-0",
    ],
  },
});
```

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
    'Content-Type': 'application/json',
}

data = {
  "dlqIds": [
    "11111-0",
    "22222-0",
    "33333-0"
  ]
}

response = requests.delete(
  'https://qstash.upstash.io/v2/dlq',
  headers=headers,
  data=data
)
```

LANGUAGE: go
CODE:
```
var data = strings.NewReader(`{
  "dlqIds": [
    "11111-0",
    "22222-0",
    "33333-0"
  ]
}`)
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/dlq", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Retrieve QStash Queue Details including Parallelism
DESCRIPTION: This snippet demonstrates how to retrieve the details of a QStash queue, including its configured parallelism. This allows users to verify the current settings of their queues. Examples are provided for cURL, TypeScript, and Python.

SOURCE: https://upstash.com/docs/qstash/features/queues.mdx

LANGUAGE: bash
CODE:
```
curl https://qstash.upstash.io/v2/queues/my-queue \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queue = client.queue({
  queueName: "my-queue"
})

const res = await queue.get()
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.get("my-queue")
```

--------------------------------

TITLE: Pause and resume a schedule
DESCRIPTION: Demonstrates the functionality to temporarily halt the execution of a schedule and then reactivate it. The example also includes checking the `isPaused` status of a schedule to confirm its current state.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });
const scheduleId = "my-schedule"

// pause schedule
await client.schedules.pause({ schedule: scheduleId });

// check if paused
const result = await client.schedules.get(scheduleId);
console.log(result.isPaused) // prints true

// resume schedule
await client.schedules.resume({ schedule: scheduleId });
```

--------------------------------

TITLE: Create or Update a URL Group with Endpoints (Python)
DESCRIPTION: This Python example demonstrates how to create a new URL group or update an existing one by adding multiple endpoints using the `upsert_endpoints` method of the QStash client's `url_group` module. It requires a QStash token for authentication.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/url-groups.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.url_group.upsert_endpoints(
    url_group="my-url-group",
    endpoints=[
        {"url": "https://my-endpoint-1"},
        {"url": "https://my-endpoint-2"},
    ],
)
```

--------------------------------

TITLE: QStash DLQ Get Message API Reference
DESCRIPTION: Documents the API endpoint for retrieving a specific message from the Dead Letter Queue (DLQ) by its ID, including the HTTP method, base URL, authentication, path parameters, and expected response behavior.

SOURCE: https://upstash.com/docs/qstash/api/dlq/getMessage.mdx

LANGUAGE: APIDOC
CODE:
```
GET /v2/dlq/{dlqId}
Host: qstash.upstash.io
Authentication: Bearer Token

Path Parameters:
  dlqId (string, required):
    Description: The DLQ ID of the message to retrieve. This ID is visible when listing DLQ messages via the /v2/dlq endpoint or within the content of a failure callback.

Responses:
  200 OK: Message retrieved successfully.
  404 Not Found: The message was not found in the DLQ (e.g., it has been removed manually or automatically).
```

--------------------------------

TITLE: Handling QStash Callbacks in Next.js API Route
DESCRIPTION: Provides an example of a Next.js API route (`pages/api/callback.js`) for processing QStash callback requests. It demonstrates how to decode the base64-encoded response body received from QStash and integrates with `@upstash/qstash/nextjs` for automatic signature verification, ensuring the authenticity of the callback.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: javascript
CODE:
```
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

TITLE: QStash List Schedules API Endpoint & Response Structure
DESCRIPTION: Documents the GET /v2/schedules API endpoint, its authentication method, and the detailed structure of the successful response, outlining each field's type, requirement status, and purpose.

SOURCE: https://upstash.com/docs/qstash/api/schedules/list.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://qstash.upstash.io/v2/schedules
AuthMethod: bearer

Response (200 OK):
  Array of Objects:
    createdAt (int, required): The creation time of the object. UnixMilli
    id (string, required): The id of the schedule.
    cron (string, required): The cron expression used to schedule the message.
    destination (string, required): Url or URL Group (topic) name
    method (string, required): The HTTP method to use for the message.
    header (Record<string, string[]>, required): The headers of the message.
    body (string, required): The body of the message.
    retries (int, optional): The number of retries that should be attempted in case of delivery failure.
    delay (int, optional): The delay in seconds before the message is delivered.
    callback (string, optional): The url where we send a callback to after the message is delivered
```

--------------------------------

TITLE: Publish Message with Failure Callback
DESCRIPTION: Demonstrates how to publish a message to QStash with a specified failure callback URL. The callback URL will be invoked if the message delivery fails after all retries. Examples are provided for cURL, TypeScript, and Python.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: bash
CODE:
```
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  failureCallback: "https://my-callback...",
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Curl Example: Paginate DLQ Messages with Cursor
DESCRIPTION: Illustrates how to use the 'cursor' query parameter with curl to paginate through messages in the QStash DLQ, retrieving the next set of messages after a previous request.

SOURCE: https://upstash.com/docs/qstash/api/dlq/listMessages.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/dlq?cursor=xxx \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Enqueue Message with Node.js (Fetch API)
DESCRIPTION: Node.js example using the Fetch API to enqueue a message to QStash, demonstrating how to set headers for authorization, content type, and QStash-specific options like method, retries, and custom header forwarding.

SOURCE: https://upstash.com/docs/qstash/api/enqueue.mdx

LANGUAGE: js
CODE:
```
const response = await fetch(
  "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com",
  {
    method: "POST",
    headers: {
      Authorization: "Bearer <token>",
      "Content-Type": "application/json",
      "Upstash-Method": "POST",
      "Upstash-Retries": "3",
      "Upstash-Forward-Custom-Header": "custom-value",
    },
    body: JSON.stringify({
      message: "Hello, World!",
    }),
  }
);
```

--------------------------------

TITLE: Get all logs with pagination using cursor
DESCRIPTION: Demonstrates how to retrieve all logs from Upstash QStash using pagination. It iterates through results using a cursor to handle large numbers of logs, ensuring all available logs are fetched.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/logs.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const logs = [];
let cursor = null;
while (true) {
  const res = await client.logs({ cursor });
  logs.push(...res.logs);
  cursor = res.cursor;
  if (!cursor) {
    break;
  }
}
```

--------------------------------

TITLE: QStash Development Server Test User Credentials
DESCRIPTION: These code blocks provide predefined environment variables for different test users, including `QSTASH_URL`, `QSTASH_TOKEN`, `QSTASH_CURRENT_SIGNING_KEY`, and `QSTASH_NEXT_SIGNING_KEY`, to be used with the local development server for testing various scenarios.

SOURCE: https://upstash.com/docs/qstash/howto/local-development.mdx

LANGUAGE: javascript
CODE:
```
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7kYjw48mhY7kAjqNGcy6cr29RJ6r
QSTASH_NEXT_SIGNING_KEY=sig_5ZB6DVzB1wjE8S6rZ7eenA8Pdnhs
```

LANGUAGE: javascript
CODE:
```
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJ0ZXN0VXNlcjEiLCJQYXNzd29yZCI6InRlc3RQYXNzd29yZCJ9
QSTASH_CURRENT_SIGNING_KEY=sig_7GVPjvuwsfqF65iC8fSrs1dfYruM
QSTASH_NEXT_SIGNING_KEY=sig_5NoELc3EFnZn4DVS5bDs2Nk4b7Ua
```

LANGUAGE: javascript
CODE:
```
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJ0ZXN0VXNlcjIiLCJQYXNzd29yZCI6InRlc3RQYXNzd29yZCJ9
QSTASH_CURRENT_SIGNING_KEY=sig_6jWGaWRxHsw4vMSPJprXadyvrybF
QSTASH_NEXT_SIGNING_KEY=sig_7qHbvhmahe5GwfePDiS5Lg3pi6Qx
```

LANGUAGE: javascript
CODE:
```
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJ0ZXN0VXNlcjMiLCJQYXNzd29yZCI6InRlc3RQYXNzd29yZCJ9
QSTASH_CURRENT_SIGNING_KEY=sig_5T8FcSsynBjn9mMLBsXhpacRovJf
QSTASH_NEXT_SIGNING_KEY=sig_7GFR4YaDshFcqsxWRZpRB161jguD
```

--------------------------------

TITLE: Enqueue Message with cURL
DESCRIPTION: Example cURL command to send a message to a QStash queue, including authorization, content type, and custom Upstash headers for method, retries, and forwarding.

SOURCE: https://upstash.com/docs/qstash/api/enqueue.mdx

LANGUAGE: sh
CODE:
```
curl -X POST "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Method: POST" \
  -H "Upstash-Retries: 3" \
  -H "Upstash-Forward-Custom-Header: custom-value" \
  -d '{"message":"Hello, World!"}'
```

--------------------------------

TITLE: Set max retry count for QStash messages
DESCRIPTION: Configure how many times QStash should retry to send the message to the endpoint before sending it to the dead letter queue.

SOURCE: https://upstash.com/docs/qstash/overall/apiexamples.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.publishJSON({
  url: "https://example.com",
  body: {
    hello: "world",
  },
  retries: 3,
});
```

LANGUAGE: python
CODE:
```
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

TITLE: List All QStash DLQ Messages with Pagination (Python)
DESCRIPTION: This Python example demonstrates how to retrieve all messages from the QStash Dead Letter Queue (DLQ) using a paginated approach. It iterates through the results using a cursor until all messages are collected, suitable for large DLQs. The `client.dlq.list()` method is used to fetch batches of messages.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/dlq.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Batching Messages to QStash URL Groups
DESCRIPTION: This snippet illustrates how to send messages in a batch where some messages target a predefined QStash URL Group and others target specific URLs. Examples are provided for cURL, TypeScript, and Python, demonstrating the mixed usage of `destination` and `urlGroup`.

SOURCE: https://upstash.com/docs/qstash/features/batch.mdx

LANGUAGE: cURL
CODE:
```
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

LANGUAGE: TypeScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: Qstash DLQ Get Message API
DESCRIPTION: New API endpoint to retrieve a specific message from the Dead Letter Queue (DLQ).

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API: DLQ Get Message
  - Endpoint: /v2/dlq/getMessage
  - Method: GET
  - Purpose: Retrieve a single message from the DLQ by ID.
```

--------------------------------

TITLE: Publish a message with content-based-deduplication
DESCRIPTION: This example shows how to enable content-based deduplication for a QStash message. By setting `content_based_deduplication` to `True`, QStash will prevent duplicate messages with identical content from being processed within a certain timeframe.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    content_based_deduplication=True,
)
```

--------------------------------

TITLE: Publish Message to QStash via ngrok URL
DESCRIPTION: Example `curl` command to publish a JSON message to a QStash endpoint. It demonstrates how to use the ngrok forwarding URL, combined with the API path, as the destination for the QStash publish operation.

SOURCE: https://upstash.com/docs/qstash/howto/local-tunnel.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://e02f-2a02-810d-af40-5284-b139-58cc-89df-b740.eu.ngrok.io/api/webhooks'
```

--------------------------------

TITLE: Create QStash Schedule Programmatically with Python SDK
DESCRIPTION: This Python code snippet demonstrates how to use the QStash Python SDK to programmatically create a scheduled job. It initializes the QStash client with a token and then calls the 'schedule.create' method, specifying the destination URL and a cron expression for scheduling.

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://YOUR_URL.vercel.app/api",
    cron="0 12 * * *",
)
```

--------------------------------

TITLE: Implement QStash Webhook Receiver in Go
DESCRIPTION: Complete Go code for setting up an HTTP server, handling incoming QStash webhooks, importing necessary packages, and verifying the QStash signature using JWT and body hash validation. This includes the main function for the server and the helper function for signature verification.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: go
CODE:
```
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

LANGUAGE: go
CODE:
```
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

LANGUAGE: go
CODE:
```
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

TITLE: Publish Message to QStash via cURL
DESCRIPTION: Example cURL command to send a JSON payload to a QStash endpoint, including necessary authentication and content type headers for publishing a message.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: bash
CODE:
```
curl --request POST "https://qstash.upstash.io/v2/publish/https://cloudflare-workers.upstash.workers.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

TITLE: List All QStash Schedules
DESCRIPTION: This section provides examples for retrieving a comprehensive list of all schedules associated with your QStash account. This operation is useful for identifying specific schedule IDs, which are often necessary for other management tasks like deletion.

SOURCE: https://upstash.com/docs/qstash/howto/delete-schedule.mdx

LANGUAGE: shell
CODE:
```
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const allSchedules = await client.schedules.list();
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.list()
```

--------------------------------

TITLE: Example: Remove Endpoints via API
DESCRIPTION: Demonstrates how to remove endpoints from a URL Group using various programming languages and cURL, sending a DELETE request with the specified endpoints in the request body.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove-endpoint.mdx

LANGUAGE: curl
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "endpoints": [
      {
        "name": "endpoint1",
      },
      {
        "url": "https://somewhere-else.com"
      }
    ]
  }'
```

LANGUAGE: js
CODE:
```
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

LANGUAGE: python
CODE:
```
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

LANGUAGE: go
CODE:
```
var data = strings.NewReader(`{
  "endpoints": [
    {
      "name": "endpoint1",
    },
    {
      "url": "https://somewhere-else.com"
    }
  ]
}`)
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/topics/:urlGroupName/endpoints", data)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
req.Header.Set("Content-Type", "application/json")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
defer resp.Body.Close()
```

--------------------------------

TITLE: Configure the number of retries
DESCRIPTION: This example illustrates how to specify the number of retries for a QStash message. It sets the `retries` parameter to control how many times QStash will attempt to deliver the message if the initial attempt fails. The maximum number of retries depends on the user's QStash plan.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Enqueue Message to QStash Queue for Ordered Delivery
DESCRIPTION: This snippet demonstrates how to enqueue a message into a QStash queue, ensuring ordered delivery (FIFO). Messages are sent to a specified URL via the queue. It shows examples using cURL, TypeScript, and Python.

SOURCE: https://upstash.com/docs/qstash/features/queues.mdx

LANGUAGE: bash
CODE:
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
  'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' -d '{"message":"Hello, World!"}'
```

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

TITLE: Batching Messages to Specific Destinations with QStash
DESCRIPTION: This snippet demonstrates how to send a batch of messages to different HTTP destinations using the QStash `batch` endpoint. It includes examples for cURL, TypeScript, and Python, showing how to specify multiple URLs in a single request.

SOURCE: https://upstash.com/docs/qstash/features/batch.mdx

LANGUAGE: cURL
CODE:
```
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

LANGUAGE: TypeScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: Example Curl Command to Delete a DLQ Message
DESCRIPTION: Demonstrates how to use curl to send a DELETE request to remove a specific message from the DLQ, including the authorization header.

SOURCE: https://upstash.com/docs/qstash/api/dlq/deleteMessage.mdx

LANGUAGE: sh
CODE:
```
curl -X DELETE https://qstash.upstash.io/v2/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Create Initial Next.js UI for Background Job Trigger
DESCRIPTION: Defines a basic Next.js `Home` component in `src/app/page.tsx` with a button. This initial UI is designed to trigger a background job, though the `handleClick` function is not yet implemented.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
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

TITLE: Enqueue LLM Chat Completion Request with QStash and Anthropic
DESCRIPTION: Shows how to enqueue an LLM chat completion request for asynchronous processing using QStash's `enqueueJSON` method. This example leverages a named queue and configures the request with the Anthropic provider for LLM interactions.

SOURCE: https://upstash.com/docs/qstash/integrations/anthropic.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Configure Parallelism for a QStash Queue
DESCRIPTION: This snippet shows how to configure the parallelism setting for a QStash queue. Parallelism controls how many messages can be processed concurrently, preventing endpoint overload. Examples are provided for cURL, TypeScript, and Python.

SOURCE: https://upstash.com/docs/qstash/features/queues.mdx

LANGUAGE: bash
CODE:
```
curl -XPOST https://qstash.upstash.io/v2/queues/ \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "queueName": "my-queue", 
    "parallelism": 5,
  }'
```

LANGUAGE: typescript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queue = client.queue({
  queueName: "my-queue"
})

await queue.upsert({
  parallelism: 1,
})
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.queue.upsert("my-queue", parallelism=5)
```

--------------------------------

TITLE: API Reference: Create Chat Completion Endpoint
DESCRIPTION: Documents the HTTP POST endpoint for generating textual responses from a large language model, specifying the URL and required authentication method.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/llm/v1/chat/completions
Description: Creates a chat completion that generates a textual response for one or more messages using a large language model.
Authentication: Bearer Token
```

--------------------------------

TITLE: Publish Message with Custom Headers to QStash
DESCRIPTION: Demonstrates how to publish a JSON message to a specific URL using QStash, including forwarding custom HTTP headers. This example shows how to set 'Upstash-Forward-My-Header' for custom header forwarding, which will be delivered to the destination API.

SOURCE: https://upstash.com/docs/qstash/howto/publishing.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://example.com",
  body: { "hello": "world" },
  headers: { "my-header": "my-value" }
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Example JWT Payload for Upstash-Signature
DESCRIPTION: Shows the structure and common claims (fields) present in the JSON Web Token (JWT) payload within the `Upstash-Signature` header, including issuer, subject URL, expiration, creation, not-before timestamps, unique ID, and a hash of the request body.

SOURCE: https://upstash.com/docs/qstash/features/security.mdx

LANGUAGE: JSON
CODE:
```
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

TITLE: Create an Upstash QStash Queue with Parallelism
DESCRIPTION: Demonstrates how to create or update an Upstash QStash queue using the `@upstash/qstash` client, setting its parallelism to 2. It also shows how to retrieve the queue details after creation to verify the settings.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/queues.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName }).upsert({ parallelism: 2 });

const queueDetails = await client.queue({ queueName }).get();
```

--------------------------------

TITLE: Handle Daily Rate Limit Error in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to catch and handle `QstashDailyRatelimitError` when the daily API rate limit is exceeded. It logs the reset time for the daily limit, allowing developers to implement appropriate retry logic or notify the user about the rate limit.

SOURCE: https://upstash.com/docs/qstash/api/api-ratelimiting.mdx

LANGUAGE: typescript
CODE:
```
import { QstashDailyRatelimitError } from "@upstash/qstash";

try {
  // Example of a publish request that could hit the daily rate limit
  const result = await client.publishJSON({
    url: "https://my-api...",
    // or urlGroup: "the name or id of a url group"
    body: {
      hello: "world",
    },
  });
} catch (error) {
  if (error instanceof QstashDailyRatelimitError) {
    console.log("Daily rate limit exceeded. Retry after:", error.reset);
    // Implement retry logic or notify the user
  } else {
    console.error("An unexpected error occurred:", error);
  }
}
```

--------------------------------

TITLE: Cancel Multiple QStash Messages
DESCRIPTION: This snippet provides examples for canceling multiple messages at once. You can either provide a list of specific message IDs to cancel or use a dedicated method to cancel all messages currently in the QStash database.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/messages.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

# cancel more than one message
client.message.cancel_many(["<msg-id-0>", "<msg-id-1>"])

# cancel all messages
client.message.cancel_all()
```

--------------------------------

TITLE: Deno Deploy QStash Webhook Receiver in TypeScript
DESCRIPTION: This TypeScript code defines an asynchronous HTTP server for Deno Deploy that acts as a QStash webhook receiver. It initializes a `Receiver` with signing keys from environment variables and verifies the incoming `Upstash-Signature` header against the request body. If the signature is invalid, it returns a 401 status; otherwise, it logs success and returns 200 OK.

SOURCE: https://upstash.com/docs/qstash/quickstarts/deno-deploy.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: Resume QStash Queue
DESCRIPTION: This snippet demonstrates how to resume a paused queue in Upstash QStash. It shows the API endpoint, required parameters, and examples in cURL, Node.js, Python, and Go. The operation resumes message delivery from the earliest undelivered message.

SOURCE: https://upstash.com/docs/qstash/api/queues/resume.mdx

LANGUAGE: APIDOC
CODE:
```
Method: POST
URL: https://qstash.upstash.io/v2/queues/{queueName}/resume
Authentication: Bearer Token

Path Parameters:
  queueName (string, required): The name of the queue to resume.

Response:
  200 OK: Queue resumed successfully.
```

LANGUAGE: sh
CODE:
```
curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/resume \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: js
CODE:
```
import { Client } from "@upstash/qstash";
/**
 * Import a fetch polyfill only if you are using node prior to v18.
 * This is not necessary for nextjs, deno or cloudflare workers.
 */
import "isomorphic-fetch";

const c = new Client({
  token: "<QSTASH_TOKEN>",
});

c.queue({ queueName: "<QUEUE_NAME>" }).resume()
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")

client.queue.resume("<QUEUE_NAME>")
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/qstash-go"
)

func main() {
	client := qstash.NewClient("<QSTASH_TOKEN>")

	// error checking is omitted for brevity
	err := client.Queues().Resume("<QUEUE_NAME>")
}
```

--------------------------------

TITLE: List All QStash Schedules
DESCRIPTION: Illustrates how to retrieve a list of all schedules associated with the QStash account using the Python SDK.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
all_schedules = client.schedule.list()

print(all_schedules)
```

--------------------------------

TITLE: QStash Batch Message API Response Example
DESCRIPTION: This JSON snippet illustrates the expected response structure after successfully sending a batch of messages to the QStash API. The response is an array where each element corresponds to a message in the original batch, providing its unique message ID and the resolved URL to which it was sent.

SOURCE: https://upstash.com/docs/qstash/features/batch.mdx

LANGUAGE: JSON
CODE:
```
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

TITLE: Remove URL Group using Python Requests
DESCRIPTION: Illustrates how to perform a DELETE operation to remove a URL group using the popular Python `requests` library. The example sets up the required Authorization header for the request.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove.mdx

LANGUAGE: python
CODE:
```
import requests

headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.delete(
  'https://qstash.upstash.io/v2/topics/my-url-group', 
  headers=headers
)
```

--------------------------------

TITLE: Configure Webhook with QStash Publish URL
DESCRIPTION: This example shows how to redirect a webhook call through QStash by constructing a special publish URL. The original webhook endpoint is embedded within the QStash URL, along with a QStash token for authentication. This allows QStash to receive the request and forward it with additional configurations.

SOURCE: https://upstash.com/docs/qstash/howto/webhook.mdx

LANGUAGE: HTTP
CODE:
```
https://qstash.upstash.io/v2/publish/https://example.com/api/webhook?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Create a QStash Schedule (5-minute interval)
DESCRIPTION: Demonstrates how to create a new schedule using the QStash Python SDK, setting a destination URL and a cron expression for a 5-minute interval. It prints the generated schedule ID.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule_id = client.schedule.create(
    destination="https://my-api...",
    cron="*/5 * * * *",
)

print(schedule_id)
```

--------------------------------

TITLE: Add Multiple Endpoints to a QStash URL Group via API
DESCRIPTION: This snippet demonstrates how to programmatically add multiple endpoints to a specified QStash URL Group using the REST API. It requires an authentication token and defines the URL group name along with a list of endpoint objects, each containing a name and a URL. This method is ideal for automating the setup and management of QStash endpoints.

SOURCE: https://upstash.com/docs/qstash/howto/url-group-endpoint.mdx

LANGUAGE: bash
CODE:
```
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

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.addEndpoints({
  name: "urlGroupName",
  endpoints: [
    { name: "endpoint1", url: "https://example.com" },
    { name: "endpoint2", url: "https://somewhere-else.com" }
  ]
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.url_group.upsert_endpoints(
    url_group="url-group-name",
    endpoints=[
        {"name": "endpoint1", "url": "https://example.com"},
        {"name": "endpoint2", "url": "https://somewhere-else.com"}
    ]
)
```

--------------------------------

TITLE: Send Batch Messages via cURL
DESCRIPTION: Example cURL command to send multiple messages in a single batch request to the QStash API. It demonstrates sending messages to a URL group, a queue, and direct URLs with various headers and delays.

SOURCE: https://upstash.com/docs/qstash/api/messages/batch.mdx

LANGUAGE: shell
CODE:
```
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

TITLE: Configure Pipedream Workflow with QStash Endpoint Trigger and Webhook Verification
DESCRIPTION: This guide outlines how to create a Pipedream workflow triggered by a QStash endpoint message. It includes configuring an HTTP trigger, setting a custom response for retry logic, and ensuring the event body is a raw request for proper QStash webhook verification.

SOURCE: https://upstash.com/docs/qstash/integrations/pipedream.mdx

LANGUAGE: APIDOC
CODE:
```
1. Create a new Pipedream workflow:
   - Sign into Pipedream and create a new workflow.

2. Configure the workflow with an HTTP trigger:
   - In the workflow Trigger, select the 'New HTTP / Webhook Requests' option.
   - Pipedream will create a unique HTTP endpoint for your workflow.
   - Configure the HTTP trigger to 'return a custom response' to allow non-200 responses for QStash retries.
   - Set the 'Event Body' to 'Raw request' to ensure the QStash verify webhook action receives data in the correct format.
```

--------------------------------

TITLE: Remove URL Group using Node.js Fetch API
DESCRIPTION: Demonstrates how to remove a URL group in a Node.js application using the native Fetch API. The example constructs a DELETE request with the necessary Authorization header.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove.mdx

LANGUAGE: js
CODE:
```
const response = await fetch('https://qstash.upstash.io/v2/topics/my-url-group', {
  method: 'DELETE',
  headers: {
    'Authorization': 'Bearer <token>'
  }
});
```

--------------------------------

TITLE: Delete a queue using QStash Python SDK
DESCRIPTION: This example illustrates how to remove an existing queue using the QStash Python SDK. After initializing the QStash client with an authentication token, it specifies the target queue name. The `client.queue.delete()` method is then called to permanently remove the queue from the QStash service.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/queues.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.delete(queue_name)
```

--------------------------------

TITLE: AWS CDK Stack for Lambda and API Gateway
DESCRIPTION: Defines an AWS CDK stack in TypeScript to create a Node.js Lambda function for video processing and expose it via an API Gateway REST API. This setup is suitable for integrating with QStash webhook logic.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Remove URL Group using cURL
DESCRIPTION: Example of how to remove a URL group using the cURL command-line tool. This command sends a DELETE request to the QStash API, requiring an Authorization Bearer token for authentication.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove.mdx

LANGUAGE: sh
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/topics/my-url-group \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: QStash Get Events API Response Schema (200 OK)
DESCRIPTION: This API documentation snippet illustrates the expected JSON structure for a successful (HTTP 200 OK) response from the QStash `/v2/events` API endpoint. It details the `cursor` for pagination and the `events` array, with each event object containing `time`, `messageId`, `state`, `url`, `header`, and `body` fields.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: APIDOC
CODE:
```
{
  "cursor": "1686652644442-12",
  "events":[
    {
      "time": "1686652644442",
      "messageId": "msg_123",
      "state": "delivered",
      "url": "https://example.com",
      "header": { "Content-Type": [ "application/x-www-form-urlencoded" ] },
      "body": "bWVyaGFiYSBiZW5pbSBhZGltIHNhbmNhcg=="
    }
  ] 
}
```

--------------------------------

TITLE: Define Server Action to Publish QStash Message
DESCRIPTION: Implements a Next.js server action (`startBackgroundJob`) in `src/app/actions.ts`. This function initializes the `@upstash/qstash` client and uses its `publishJSON` method to send a message to a temporary testing endpoint (Request Catcher).

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: Delete a URL Group (Python)
DESCRIPTION: This Python example shows how to completely delete a URL group by its name using the `delete` method of the QStash client's `url_group` module. This action permanently removes the specified URL group and all its associated endpoints.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/url-groups.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.url_group.delete("my-url-group")
```

--------------------------------

TITLE: Next.js Client Component for Background Job UI
DESCRIPTION: This React client component (`Home`) provides a user interface to trigger the background job. It manages loading states and displays messages based on the job's outcome. It interacts with the `startBackgroundJob` server action to initiate the QStash message publishing and provides visual feedback to the user.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
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

TITLE: QStash List Queues API Reference
DESCRIPTION: Detailed API documentation for listing all queues in QStash. Describes the HTTP method, endpoint, authentication, request parameters, and the structure of the successful response, including queue properties like creation time, name, parallelism, and message lag.

SOURCE: https://upstash.com/docs/qstash/api/queues/list.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://qstash.upstash.io/v2/queues
Authentication: Bearer Token

Request Parameters: None

Response (Array of Queue Objects):
  createdAt: int (required) - The creation time of the queue. UnixMilli
  updatedAt: int (required) - The update time of the queue. UnixMilli
  name: string (required) - The name of the queue.
  parallelism: int (required) - The number of parallel consumers consuming from the queue.
  lag: int (required) - The number of unprocessed messages that exist in the queue.
```

--------------------------------

TITLE: Handle Chat-based Rate Limit Error in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to catch and handle `QstashChatRatelimitError` specific to chat-related API endpoints. It logs the reset time for requests, indicating that chat-specific rate limiting might require specialized handling, such as queueing requests or adjusting the frequency of chat interactions.

SOURCE: https://upstash.com/docs/qstash/api/api-ratelimiting.mdx

LANGUAGE: typescript
CODE:
```
import { QstashChatRatelimitError, Client, openai } from "@upstash/qstash";

try {
  // Example of a chat-related request that could hit the chat rate limit
  const client = new Client({
    token: "<QSTASH_TOKEN>",
  });

  const result = await client.publishJSON({
    api: {
      name: "llm",
      provider: openai({ token: process.env.OPENAI_API_KEY! }),
    },
    body: {
      model: "gpt-3.5-turbo",
      messages: [
        {
          role: "user",
          content: "Where is the capital of Turkey?",
        },
      ],
    },
    callback: "https://oz.requestcatcher.com/",
  });
} catch (error) {
  if (error instanceof QstashChatRatelimitError) {
    console.log("Chat rate limit exceeded. Retry after:", error.resetRequests);
    // Handle chat-specific rate limiting, perhaps by queueing requests
  } else {
    console.error("An unexpected error occurred:", error);
  }
}
```

--------------------------------

TITLE: Handle Burst Rate Limit Error in TypeScript
DESCRIPTION: This TypeScript example illustrates how to catch and handle `QstashRatelimitError` when the burst API rate limit is exceeded. It logs the reset time for the burst limit, suggesting the implementation of exponential backoff or delays before retrying requests to avoid continuous rate limiting.

SOURCE: https://upstash.com/docs/qstash/api/api-ratelimiting.mdx

LANGUAGE: typescript
CODE:
```
import { QstashRatelimitError } from "@upstash/qstash";

try {
  // Example of a request that could hit the burst rate limit
  const result = await client.publishJSON({
    url: "https://my-api...",
    // or urlGroup: "the name or id of a url group"
    body: {
      hello: "world",
    },
  });
} catch (error) {
  if (error instanceof QstashRatelimitError) {
    console.log("Burst rate limit exceeded. Retry after:", error.reset);
    // Implement exponential backoff or delay before retrying
  } else {
    console.error("An unexpected error occurred:", error);
  }
}
```

--------------------------------

TITLE: Delete a QStash DLQ Message (Python)
DESCRIPTION: This Python example illustrates how to remove a specific message from the QStash Dead Letter Queue (DLQ) using its unique ID. The `client.dlq.delete()` method is employed to clear out processed or unwanted failed messages from the DLQ.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/dlq.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.dlq.delete("<dlq-id>")
```

--------------------------------

TITLE: Create a queue with parallelism using QStash Python SDK
DESCRIPTION: This snippet demonstrates how to create or update a queue using the QStash Python SDK, specifically setting its parallelism. It initializes the QStash client, defines a queue name, and then uses `client.queue.upsert()` to create or modify the queue with a specified parallelism level. Finally, it retrieves and prints the queue's details.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/queues.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=2)

print(client.queue.get(queue_name))
```

--------------------------------

TITLE: Remove an Endpoint from a URL Group (Python)
DESCRIPTION: This Python example illustrates how to remove specific endpoints from an existing URL group using the `remove_endpoints` method of the QStash client's `url_group` module. It targets a URL group by name and specifies the endpoints to be removed.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/url-groups.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.url_group.remove_endpoints(
    url_group="my-url-group",
    endpoints=[
        {"url": "https://my-endpoint-1"},
    ],
)
```

--------------------------------

TITLE: NPM Script for Lambda Build and Zip
DESCRIPTION: A `package.json` script that uses `esbuild` to bundle, minify, and sourcemap a TypeScript `index.ts` file, then zips the output for manual deployment to AWS Lambda.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: json
CODE:
```
{
  "scripts": {
    "build": "rm -rf ./dist; esbuild index.ts --bundle --minify --sourcemap --platform=node --target=es2020 --outfile=dist/index.js && cd dist && zip -r index.zip index.js*"
  }
}
```

--------------------------------

TITLE: Expose Python Cleanup Logic as Public HTTP Endpoint
DESCRIPTION: This Python script creates a simple HTTP server using 'http.server.BaseHTTPRequestHandler' that exposes the database cleanup logic as a POST endpoint. When a POST request is received, it triggers the 'delete_all_entries' function.

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Create a schedule that runs every 5 minutes
DESCRIPTION: Demonstrates how to create a new schedule using the `@upstash/qstash` client. This schedule is configured to execute its `destination` URL every 5 minutes, based on the provided cron expression.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://my-api...",
  cron: "*/5 * * * *"
});
```

--------------------------------

TITLE: Update Next.js UI to Invoke Background Job Server Action
DESCRIPTION: Modifies the `src/app/page.tsx` component to integrate the `startBackgroundJob` server action. The `handleClick` function is now defined to asynchronously call this action when the button is clicked, initiating the QStash message publication.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
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

TITLE: Publish HTML Content (TypeScript)
DESCRIPTION: This snippet shows how to publish raw HTML content instead of a JSON object. It requires setting the `Content-Type` header appropriately.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publish({
  url: "https://my-api...",
  body: "<html><body><h1>Hello World</h1></body></html>",
  headers: {
    "Content-Type": "text/html",
  },
});
```

--------------------------------

TITLE: Create a schedule that runs every hour with callback URLs
DESCRIPTION: Illustrates creating a schedule that runs hourly and includes optional callback URLs. A `callback` URL is invoked upon successful execution, while a `failureCallback` URL is triggered if the scheduled task encounters an error.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://my-api...",
  cron: "0 * * * *",
  callback: "https://my-callback...",
  failureCallback: "https://my-failure-callback..."
});
```

--------------------------------

TITLE: Deploy AWS CDK Application
DESCRIPTION: Executes the `cdk deploy` command in the terminal to deploy the defined AWS CDK stack, provisioning cloud resources like Lambda functions and API Gateways.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: bash
CODE:
```
cdk deploy
```

--------------------------------

TITLE: QStash Environment Variables Configuration
DESCRIPTION: This code block provides the necessary environment variables for configuring QStash in a Next.js project. It lists placeholders for the QSTASH_TOKEN, QSTASH_CURRENT_SIGNING_KEY, and QSTASH_NEXT_SIGNING_KEY, which must be obtained from the QStash dashboard.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: bash
CODE:
```
# Copy all three from your QStash dashboard
QSTASH_TOKEN=
QSTASH_CURRENT_SIGNING_KEY=
QSTASH_NEXT_SIGNING_KEY=
```

--------------------------------

TITLE: Next.js Client Component: Trigger QStash Background Job
DESCRIPTION: This Next.js client component provides a user interface to initiate a background job. It uses a button to call a server action (`startBackgroundJob`) and displays the job's status, including loading states and the message ID upon successful initiation.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
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

TITLE: Configure QStash Schedule via Dashboard
DESCRIPTION: This section outlines the parameters required to set up a scheduled job in the QStash dashboard. It specifies the target URL for the cron job, the type of job (Schedule), and the desired frequency (daily at midnight).

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: APIDOC
CODE:
```
URL: https://your-vercel-app.vercel.app/api
Type: Schedule
Every: every day at midnight (feel free to customize)
```

--------------------------------

TITLE: Chat Completion API Request Body Parameters
DESCRIPTION: Defines the structure and properties of the request body for a chat completion API call, detailing each parameter's purpose, type, and constraints.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: APIDOC
CODE:
```
Request Body Parameters:
  model: string (required)
    Name of the model.
  messages: Object[] (required)
    One or more chat messages.
    Sub-fields:
      role: string (required)
        The role of the message author. One of `system`, `assistant`, or `user`.
      content: string (required)
        The content of the message.
      name: string (optional)
        An optional name for the participant.
        Provides the model information to differentiate between participants of the same role.
  frequency_penalty: number (optional)
    Number between `-2.0` and `2.0`. Positive values penalize new tokens based on their existing
    frequency in the text so far, decreasing the model's likelihood to repeat the same line verbatim.
  logit_bias: Object (optional)
    Modify the likelihood of specified tokens appearing in the completion.

    Accepts a JSON object that maps tokens (specified by their token ID in the tokenizer)
    to an associated bias value from `-100` to `100`. Mathematically, the bias is added to
    the logits generated by the model prior to sampling. The exact effect will vary
    per model, but values between `-1` and `1` should decrease or increase likelihood
    of selection; values like `-100` or `100` should result in a ban or exclusive
    selection of the relevant token.
  logprobs: boolean (optional)
    Whether to return log probabilities of the output tokens or not. If true, returns
    the log probabilities of each output token returned in the content of message.
  top_logprobs: number (optional)
    An integer between `0` and `20` specifying the number of most likely tokens to return at
    each token position, each with an associated log probability. logprobs must be set
    to true if this parameter is used.
  max_tokens: number (optional)
    The maximum number of tokens that can be generated in the chat completion.
  n: number (optional)
    How many chat completion choices to generate for each input message.

    Note that you will be charged based on the number of generated tokens
    across all of the choices. Keep `n` as `1` to minimize costs.
  presence_penalty: number (optional)
    Number between `-2.0` and `2.0`. Positive values penalize new tokens
    based on whether they appear in the text so far, increasing the
    model's likelihood to talk about new topics.
  response_format: Object (optional)
    An object specifying the format that the model must output.

    Setting to `{ "type": "json_object" }` enables JSON mode,
    which guarantees the message the model generates is valid JSON.

    Important: when using JSON mode, you must also instruct the model
    to produce JSON yourself via a system or user message. Without this,
    the model may generate an unending stream of whitespace until the
    generation reaches the token limit, resulting in a long-running and
    seemingly "stuck" request. Also note that the message content may
    be partially cut off if `finish_reason="length"`, which indicates the
    generation exceeded max_tokens or the conversation exceeded the max context length.
    Sub-fields:
      type: string (required)
        Must be one of `text` or `json_object`.
  seed: number (optional)
    This feature is in Beta. If specified, our system will make
```

--------------------------------

TITLE: Publish LLM Request with QStash and Anthropic
DESCRIPTION: Demonstrates how to publish a single LLM chat completion request to Anthropic's API using QStash's `publishJSON` method. It shows how to specify the LLM API with the Anthropic provider and include an asynchronous callback URL for handling responses.

SOURCE: https://upstash.com/docs/qstash/integrations/anthropic.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Verify QStash Request Signature using SDK
DESCRIPTION: This snippet demonstrates how to verify incoming QStash request signatures using the official QStash SDKs. It shows the initialization of the `Receiver` with `currentSigningKey` and `nextSigningKey`, and then how to use the `verify` method. The method requires the raw request body, the signature from the `Upstash-Signature` header, and optionally the request URL. It's crucial to use the raw body string to avoid verification failures.

SOURCE: https://upstash.com/docs/qstash/howto/signature.mdx

LANGUAGE: typescript
CODE:
```
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

LANGUAGE: python
CODE:
```
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

LANGUAGE: go
CODE:
```
import "github.com/qstash/qstash-go"
import "io"

receiver := qstash.NewReceiver("<CURRENT_SIGNING_KEY>", "NEXT_SIGNING_KEY")

// ... in your request handler

signature := req.Header.Get("Upstash-Signature")
body, err := io.ReadAll(req.Body)
// handle err

err = receiver.Verify(qstash.VerifyOptions{
    Signature: signature,
    Body:      string(body),
    Url:       "YOUR-SITE-URL", // optional
})
// handle err
```

--------------------------------

TITLE: Create a schedule to a URL Group that runs every minute
DESCRIPTION: Shows how to create a schedule that targets a predefined URL Group instead of a single URL. This schedule is set to run every minute, enabling the delivery of messages to multiple endpoints simultaneously.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "my-url-group",
  cron: "* * * * *"
});
```

--------------------------------

TITLE: Publishing QStash Messages with Callback URL
DESCRIPTION: Demonstrates how to publish a message to QStash and specify a callback URL using the `Upstash-Callback` header (cURL) or the `callback` parameter (TypeScript/Python SDKs). The callback URL will receive the response once the original message processing is complete.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: bash
CODE:
```
curl -X POST \
  https://qstash.upstash.io/v2/publish/https://my-api... \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  callback: "https://my-callback...",
});
```

LANGUAGE: python
CODE:
```
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

TITLE: QStash Callback Configuration Headers
DESCRIPTION: Lists HTTP headers used to configure various aspects of both regular and failure callbacks, such as timeout, retries, delay, and method. These headers allow fine-grained control over callback behavior.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: APIDOC
CODE:
```
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

TITLE: Publishing a Single LLM Chat Completion Request with QStash
DESCRIPTION: Demonstrates how to publish a single OpenAI-compatible LLM chat completion request directly to QStash. This method uses the `publishJSON` function and requires specifying the `api` destination as `llm` with a provider, along with a `callback` URL for asynchronous response processing. Streaming chat completions are not supported with this method.

SOURCE: https://upstash.com/docs/qstash/integrations/llm.mdx

LANGUAGE: JavaScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: Set QStash Signing Keys on Fly.io
DESCRIPTION: Commands to set environment variables for QStash current and next signing keys on the Fly.io application using `flyctl secrets set`. These keys are crucial for webhook signature verification.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: bash
CODE:
```
flyctl secrets set QSTASH_CURRENT_SIGNING_KEY=...
flyctl secrets set QSTASH_NEXT_SIGNING_KEY=...
```

--------------------------------

TITLE: Import Necessary Libraries for QStash Webhook Handling
DESCRIPTION: This code imports all required Python libraries for handling and verifying QStash webhooks, including `json`, `os`, `hmac`, `hashlib`, `base64`, `time`, and `jwt`.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: python
CODE:
```
import json
import os
import hmac
import hashlib
import base64
import time
import jwt
```

--------------------------------

TITLE: Publish QStash Message from Next.js Server Action
DESCRIPTION: This server action (`startBackgroundJob`) uses the `@upstash/qstash` client to publish a JSON message to a specified URL. It includes robust error handling to catch potential issues during the publishing process and returns the `messageId` on success or `null` on failure, making it suitable for integration with client-side UIs.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
"use server"
import { Client } from "@upstash/qstash";

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!
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

TITLE: Rotate QStash Signing Keys (Python)
DESCRIPTION: This snippet shows how to rotate your QStash signing keys using the Python SDK. After initializing the QStash client with your token, it calls the `signing_key.rotate()` method, which generates new keys and returns them. The newly rotated keys (current and next) are then displayed.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/keys.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
new_signing_key = client.signing_key.rotate()

print(new_signing_key.current, new_signing_key.next)
```

--------------------------------

TITLE: Receive Streaming Chat Completions Response
DESCRIPTION: This snippet illustrates a streaming JSON response (HTTP 200 OK) from the Upstash QStash LLM API for a chat completions request. It shows how individual message chunks are delivered as `data:` prefixed lines, ending with a final usage summary and a `data: [DONE]` signal.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: json
CODE:
```
data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"role":"assistant"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":"The"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":" capital"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":" of"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":" Turkey"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":" is"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":" Ankara"},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":"."},"logprobs":null,"finish_reason":null}]}

data: {"id":"cmpl-dfc1ad80d0254c2aaf3e7775d1830c9d","object":"chat.completion.chunk","created":1717484084,"model":"meta-llama/Meta-Llama-3-8B-Instruct","choices":[{"index":0,"delta":{"content":""},"finish_reason":"stop"}],"usage":{"prompt_tokens":18,"total_tokens":26,"completion_tokens":8}}

data: [DONE]
```

--------------------------------

TITLE: Create QStash Schedule to URL
DESCRIPTION: Demonstrates how to create a recurring schedule that publishes messages to a specific URL using a cron expression. The message will be published every minute.

SOURCE: https://upstash.com/docs/qstash/features/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="https://example.com",
    cron="* * * * *",
)
```

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

TITLE: Publish Message to Deno Deploy QStash Endpoint using cURL
DESCRIPTION: This cURL command demonstrates how to publish a message to a QStash endpoint, targeting the public URL of a deployed Deno project. It sends a POST request with an authorization bearer token, sets the content type to JSON, and includes a simple JSON payload.

SOURCE: https://upstash.com/docs/qstash/quickstarts/deno-deploy.mdx

LANGUAGE: bash
CODE:
```
curl --request POST "https://qstash.upstash.io/v2/publish/https://early-frog-33.deno.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

TITLE: Create QStash Schedule to URL Group
DESCRIPTION: Shows how to create a recurring schedule that publishes messages to a predefined URL Group using its name or ID and a cron expression.

SOURCE: https://upstash.com/docs/qstash/features/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "urlGroupName",
  cron: "* * * * *",
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.create(
    destination="url-group-name",
    cron="* * * * *",
)
```

LANGUAGE: bash
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/<URL_GROUP_ID_OR_NAME>'
```

--------------------------------

TITLE: Create a URL Group and add 2 endpoints
DESCRIPTION: This snippet demonstrates how to create a new URL group and associate multiple endpoints with it using the `@upstash/qstash` client. It initializes the client with an API token and then calls the `addEndpoints` method on the `urlGroups` service, providing a name for the group and an array of endpoint URLs.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.addEndpoints({
  name: "url_group_name",
  endpoints: [
    { url: "https://my-endpoint-1" },
    { url: "https://my-endpoint-2" }
  ]
});
```

--------------------------------

TITLE: Batch LLM Chat Completion Requests with QStash and Anthropic
DESCRIPTION: Illustrates how to send multiple LLM chat completion requests to Anthropic's API in a single operation using QStash's `batchJSON` method. Each request within the batch specifies the Anthropic provider and includes its own callback URL for individual response handling.

SOURCE: https://upstash.com/docs/qstash/integrations/anthropic.mdx

LANGUAGE: typescript
CODE:
```
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
  }
]);

console.log(result);
```

--------------------------------

TITLE: Authenticate ngrok CLI
DESCRIPTION: Command to add an authentication token to the ngrok CLI, connecting it to your ngrok account. This is a prerequisite for using ngrok's tunneling services.

SOURCE: https://upstash.com/docs/qstash/howto/local-tunnel.mdx

LANGUAGE: bash
CODE:
```
ngrok config add-authtoken XXX
```

--------------------------------

TITLE: Next.js Server Action: Publish QStash Message
DESCRIPTION: This Next.js server action is responsible for publishing a message to QStash. It initializes the QStash client with an environment variable token and uses `publishJSON` to send a payload to a specified URL, returning the `messageId` or `null` on error.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: cURL Command to Test QStash Integration
DESCRIPTION: A cURL command demonstrating how to send a POST request to a QStash endpoint, which then forwards it to the deployed Lambda function, including authorization and content type headers.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: bash
CODE:
```
curl --request POST "https://qstash.upstash.io/v2/publish/<YOUR-LAMBDA-URL>" \
-H "Authorization: Bearer <QSTASH_TOKEN>" \
-H "Content-Type: application/json" \
-d "{ \"hello\": \"world\"}"
```

--------------------------------

TITLE: Retrieve QStash Logs API Call
DESCRIPTION: Demonstrates how to make an API call to retrieve logs from the QStash service using different programming languages. Requires an Authorization Bearer token for authentication.

SOURCE: https://upstash.com/docs/qstash/api/logs/list.mdx

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/logs \
  -H "Authorization: Bearer <token>"
```

LANGUAGE: javascript
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/logs", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

LANGUAGE: python
CODE:
```
import requests
headers = {
    'Authorization': 'Bearer <token>',
}
```

--------------------------------

TITLE: Publishing a QStash Message with a Failure Callback
DESCRIPTION: This snippet demonstrates how to publish a message to QStash while specifying a failure callback URL. The provided callback URL will be invoked by QStash if the message fails to be delivered, allowing for custom error handling such as logging or alerting. It requires a QStash token, a destination URL, and the callback URL.

SOURCE: https://upstash.com/docs/qstash/howto/handling-failures.mdx

LANGUAGE: bash
CODE:
```
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  failureCallback: "https://my-callback..."
});
```

LANGUAGE: python
CODE:
```
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

TITLE: QStash Events API Reference
DESCRIPTION: Detailed API documentation for the QStash Events endpoint. This API allows users to retrieve a list of events, which are being renamed to logs, with extensive filtering and pagination capabilities. Authentication is via a bearer token.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: GET https://qstash.upstash.io/v2/events
Authentication: Bearer Token

Request Parameters (Query):
  - cursor (string): By providing a cursor you can paginate through all of the events.
  - messageId (string): Filter events by message id.
  - state (string): Filter events by state.
    Possible Values:
      - CREATED: The message has been accepted and stored in QStash
      - ACTIVE: The task is currently being processed by a worker.
      - RETRY: The task has been scheduled to retry.
      - ERROR: The execution threw an error and the task is waiting to be retried or failed.
      - IN_PROGRESS: The task is in one of ACTIVE, RETRY or ERROR state.
      - DELIVERED: The message was successfully delivered.
      - FAILED: The task has errored too many times or encountered an error that it cannot recover from.
      - CANCEL_REQUESTED: The cancel request from the user is recorded.
      - CANCELLED: The cancel request from the user is honored.
  - url (string): Filter events by url.
  - topicName (string): Filter events by URL Group (topic) name.
  - scheduleId (string): Filter events by schedule id.
  - queueName (string): Filter events by queue name.
  - fromDate (number): Filter events by starting date, in milliseconds (Unix timestamp). This is inclusive.
  - toDate (number): Filter events by ending date, in milliseconds (Unix timestamp). This is inclusive.
  - count (number): The number of events to return. Default and max is 1000.
  - order (string): The sorting order of events by timestamp.
    Valid Values: "earliestFirst", "latestFirst". Default: "latestFirst".
```

--------------------------------

TITLE: Pause and Resume a queue using QStash Python SDK
DESCRIPTION: This snippet demonstrates how to control the operational state of a QStash queue by pausing and resuming it. It first ensures the queue exists (or creates it) with a specified parallelism. Then, it uses `client.queue.pause()` to halt message processing, verifies the paused state, and finally uses `client.queue.resume()` to restart message processing for the queue.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/queues.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")

queue_name = "upstash-queue"
client.queue.upsert(queue_name, parallelism=1)

client.queue.pause(queue_name)

queue = client.queue.get(queue_name)
print(queue.paused) # prints True

client.queue.resume(queue_name)
```

--------------------------------

TITLE: Verify QStash Message Signature with Typescript SDK
DESCRIPTION: This code snippet demonstrates how to initialize the `Receiver` class from the `@upstash/qstash` SDK and use its `verify` method to validate an incoming QStash message's signature. It requires providing your current and next signing keys, the message body, the signature extracted from the `Upstash-Signature` header, and your site's URL.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/receiver.mdx

LANGUAGE: typescript
CODE:
```
import { Receiver } from "@upstash/qstash";

const receiver = new Receiver({
  currentSigningKey: "YOUR_CURRENT_SIGNing_KEY",
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

--------------------------------

TITLE: Publish Message to QStash via cURL
DESCRIPTION: This cURL command sends a POST request to the QStash publish endpoint. It requires an Authorization header with a QStash token and a JSON payload in the request body. The destination URL for the message is appended to the QStash publish endpoint.

SOURCE: https://upstash.com/docs/qstash/quickstarts/fly-io/go.mdx

LANGUAGE: bash
CODE:
```
curl --request POST "https://qstash.upstash.io/v2/publish/https://winter-cherry-9545.fly.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

TITLE: API Reference: Rotate QStash Signing Keys
DESCRIPTION: Details the API endpoint for rotating QStash signing keys, including the HTTP method, URL, authentication, and expected response fields.

SOURCE: https://upstash.com/docs/qstash/api/signingKeys/rotate.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint:
  Method: POST
  URL: https://qstash.upstash.io/v2/keys/rotate
Authentication:
  Method: Bearer Token
Response Fields:
  current:
    Type: string
    Required: true
    Description: Your current signing key.
  next:
    Type: string
    Required: true
    Description: The next signing key.
```

--------------------------------

TITLE: Receive Standard Chat Completions Response
DESCRIPTION: This snippet shows a typical successful JSON response (HTTP 200 OK) from the Upstash QStash LLM API for a chat completions request. It includes the generated message, model details, and token usage statistics for the prompt and completion.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: json
CODE:
```
{
  "id": "cmpl-abefcf66fae945b384e334e36c7fdc97",
  "object": "chat.completion",
  "created": 1717483987,
  "model": "meta-llama/Meta-Llama-3-8B-Instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The capital of Turkey is Ankara."
      },
      "logprobs": null,
      "finish_reason": "stop",
      "stop_reason": null
    }
  ],
  "usage": {
    "prompt_tokens": 18,
    "total_tokens": 26,
    "completion_tokens": 8
  }
}
```

--------------------------------

TITLE: Publish to URL Group with Delay, Headers, and Body (TypeScript)
DESCRIPTION: You create URL group on the QStash console or using the [URL Group API](/qstash/sdks/ts/examples/url-groups#create-a-url-group-and-add-2-endpoints)

This snippet shows how to publish a JSON message to a predefined URL group. It also includes a 3-second delay, custom headers, and a JSON body. The response for URL group publishing is an array of messages.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Enqueueing a Single LLM Chat Completion Request to a QStash Queue
DESCRIPTION: Illustrates how to enqueue a single OpenAI-compatible LLM chat completion request to a named QStash queue. This approach uses `enqueueJSON` and is suitable for scenarios where messages need to be processed from a queue, leveraging QStash's queueing capabilities.

SOURCE: https://upstash.com/docs/qstash/integrations/llm.mdx

LANGUAGE: JavaScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: Conceptual Key Rolling Logic
DESCRIPTION: This pseudo-code snippet illustrates the conceptual process of how signing keys are updated when a key roll operation is performed. The 'currentKey' is replaced by the 'nextKey', and a new 'nextKey' is generated to prepare for the subsequent roll.

SOURCE: https://upstash.com/docs/qstash/howto/roll-signing-keys.mdx

LANGUAGE: pseudo-code
CODE:
```
currentKey = nextKey
nextKey = generateNewKey()
```

--------------------------------

TITLE: Create QStash Schedule to Queue
DESCRIPTION: Illustrates how to create a recurring schedule that adds messages to a specific QStash Queue at a given time using a cron expression.

SOURCE: https://upstash.com/docs/qstash/features/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
  queueName: "yourQueueName",
});
```

LANGUAGE: bash
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -H "Upstash-Queue-Name: yourQueueName" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

TITLE: Create a QStash Schedule with Custom Timeout
DESCRIPTION: Explains how to set a custom timeout for the destination URL call when creating a schedule using the QStash Python SDK, ensuring the operation respects a specified duration.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Publish HTML content instead of JSON
DESCRIPTION: This snippet demonstrates how to publish content other than JSON, specifically HTML. It sets the `body` to an HTML string and explicitly specifies the `content_type` as 'text/html', ensuring QStash handles the content appropriately.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.publish(
    url="https://my-api...",
    body="<html><body><h1>Hello World</h1></body></html>",
    content_type="text/html",
)
```

--------------------------------

TITLE: Next.js API Route for Bitcoin Price Scraping
DESCRIPTION: Implements a serverless Next.js API route (`/pages/api/cron.ts`) that periodically fetches the current Bitcoin price from `blockchain.info`, stores it in an Upstash Redis database with a timestamp, and is secured using `verifySignature` from `@upstash/qstash/nextjs` to ensure requests originate from Upstash. The `bodyParser` is disabled to allow raw request body access for signature verification.

SOURCE: https://upstash.com/docs/qstash/recipes/periodic-data-updates.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Send Batch Emails with QStash and Resend (TypeScript)
DESCRIPTION: Illustrates how to send multiple emails in a batch using the `qstash-js` SDK and Resend's Batch Email API. The `batch` option is set to `true` in the provider configuration. Each email's configuration is provided as an object within an array in the `body` field, allowing individual customization.

SOURCE: https://upstash.com/docs/qstash/integrations/resend.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Pause and Resume a QStash Schedule
DESCRIPTION: Demonstrates how to programmatically pause and then resume an existing QStash schedule using its ID with the Python SDK, and verify its paused status.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule_id = "scd_1234"

client.schedule.pause(schedule_id)

schedule = client.schedule.get(schedule_id)
print(schedule.paused) # prints True

client.schedule.resume(schedule_id)
```

--------------------------------

TITLE: Complete Cloudflare Worker for QStash Webhook Reception
DESCRIPTION: The full TypeScript code for a Cloudflare Worker that integrates QStash webhook reception. It includes importing the `Receiver`, defining environment variables, initializing the receiver, and verifying incoming webhook signatures, with error handling for invalid signatures.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: ts
CODE:
```
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
    const c = new Receiver({
      currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
      nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
    });

    const body = await request.text();

    const isValid = await c
      .verify({
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

TITLE: Order Query Parameter for Qstash Events and DLQ APIs
DESCRIPTION: The `/v2/events` and `/v2/dlq` endpoints now support an `order` query parameter for sorting results.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API Query Parameters:
  - Endpoint: /v2/events
    - Parameter: order (string, optional)
      - Description: Specifies the sorting order for events.
  - Endpoint: /v2/dlq
    - Parameter: order (string, optional)
      - Description: Specifies the sorting order for DLQ messages.
```

--------------------------------

TITLE: Create or overwrite a schedule with a user-chosen schedule ID
DESCRIPTION: Explains how to create a new schedule or update an existing one by providing a custom `scheduleId`. If a schedule with the specified ID already exists, its configuration will be completely replaced by the new definition.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  scheduleId: "USER_PROVIDED_SCHEDULE_ID",
  cron: "* * * * *"
});
```

--------------------------------

TITLE: Sending Multiple LLM Chat Completion Requests in Batches with QStash
DESCRIPTION: Shows how to send multiple OpenAI-compatible LLM chat completion requests as a single batch operation using QStash. This is efficient for processing several requests together, reducing overhead and improving throughput.

SOURCE: https://upstash.com/docs/qstash/integrations/llm.mdx

LANGUAGE: JavaScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

LANGUAGE: curl
CODE:
```
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

TITLE: Verify QStash Message Signature in Python
DESCRIPTION: This snippet demonstrates how to use the `Receiver` class from the QStash Python SDK to verify the signature of an incoming message. The `Receiver` is initialized with current and next signing keys. The `verify` method then validates the message's body and signature against a provided URL, ensuring the message's authenticity and integrity.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/receiver.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Verify QStash Request Signature in Next.js API Route
DESCRIPTION: This snippet demonstrates how to create a Next.js API route (`/api/long-task`) that simulates a long-running background task. It integrates `@upstash/qstash/nextjs` to verify the incoming request's signature, ensuring the request originates from QStash. The route processes JSON data and performs a series of `fetch` calls with a delay to simulate work.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
import { verifySignatureAppRouter } from "@upstash/qstash/nextjs"

async function handler(request: Request) {
  const data = await request.json()

  for (let i = 0; i < 10; i++) {
    await fetch("https://firstqstashmessage.requestcatcher.com/test", {
      method: "POST",
      body: JSON.stringify(data),
      headers: { "Content-Type": "application/json" }
    })
    await new Promise((resolve) => setTimeout(resolve, 500))
  }

  return Response.json({ success: true })
}

export const POST = verifySignatureAppRouter(handler)
```

--------------------------------

TITLE: Send Chat Completions Request with cURL
DESCRIPTION: This snippet demonstrates how to send a chat completions request to the Upstash QStash LLM API using cURL. It specifies the LLM model, user messages, and includes necessary authorization and content type headers for a successful API call.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: sh
CODE:
```
curl "https://qstash.upstash.io/llm/v1/chat/completions" \
    -X POST \
    -H "Authorization: Bearer QSTASH_TOKEN" \
    -H "Content-Type: application/json" \
    -d '{
        "model": "meta-llama/Meta-Llama-3-8B-Instruct",
        "messages": [
            {
                "role": "user",
                "content": "What is the capital of Turkey?"
            }
        ]
    }'
```

--------------------------------

TITLE: Stream Response Object Structure
DESCRIPTION: Defines the complete structure of the streamed chat completion response object, including all top-level and nested fields, their types, and detailed descriptions. This response is received when `stream` is set to `true` in the request.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: APIDOC
CODE:
```
Stream Response:
  id: string
    A unique identifier for the chat completion. Each chunk has the same ID.
  choices: Object[]
    A list of chat completion choices. Can be more than one if `n` is greater than `1`. Can also be empty for the last chunk.
    delta: Object
      A chat completion delta generated by streamed model responses.
      role: string
        The role of the author of this message.
      content: string
        The contents of the chunk message.
    finish_reason: string
      The reason the model stopped generating tokens. This will be `stop` if the model hit a natural stop point or a provided stop sequence, `length` if the maximum number of tokens specified in the request was reached.
    index: number
      The index of the choice in the list of choices.
    logprobs: Object
      Log probability information for the choice.
      content: Object[]
        A list of message content tokens with log probability information.
        token: string
          The token.
        logprob: number
          The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
        bytes: number[]
          A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
        top_logprobs: Object[]
          List of the most likely tokens and their log probability, at this token position. In rare cases, there may be fewer than the number of requested `top_logprobs` returned.
          token: string
            The token.
          logprob: number
            The log probability of this token, if it is within the top 20 most likely tokens. Otherwise, the value `-9999.0` is used to signify that the token is very unlikely.
          bytes: number[]
            A list of integers representing the UTF-8 bytes representation of the token. Useful in instances where characters are represented by multiple tokens and their byte representations must be combined to generate the correct text representation. Can be null if there is no bytes representation for the token.
  created: number
    The Unix timestamp (in seconds) of when the chat completion was created. Each chunk has the same timestamp.
  model: string
    The model used for the chat completion.
  system_fingerprint: string
    This fingerprint represents the backend configuration that the model runs with.
    Can be used in conjunction with the `seed` request parameter to understand when backend changes have been made that might impact determinism.
  object: string
    The object type, which is always `chat.completion.chunk`.
  usage: Object
    it contains a null value except for the last chunk which contains the token usage statistics for the entire request.
    completion_tokens: number
      Number of tokens in the generated completion.
    prompt_tokens: number
      Number of tokens in the prompt.
    total_tokens: number
```

--------------------------------

TITLE: Update QStash Publish Action with Public Endpoint
DESCRIPTION: Updates the `startBackgroundJob` server action in `src/app/actions.ts` to use the newly deployed public API endpoint instead of the temporary Request Catcher URL. This directs QStash messages to the application's own long-running task handler.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
"use server"
import { Client } from "@upstash/qstash"

const qstashClient = new Client({
  token: process.env.QSTASH_TOKEN!,
})

export async function startBackgroundJob() {
  await qstashClient.publishJSON({

```

--------------------------------

TITLE: Implement Python Database Cleanup Logic
DESCRIPTION: This Python code defines a function to connect to an Upstash Redis instance and delete all keys. It uses the 'upstash_redis' library for database interaction.

SOURCE: https://upstash.com/docs/qstash/quickstarts/python-vercel.mdx

LANGUAGE: python
CODE:
```
from upstash_redis import Redis

redis = Redis(url="https://YOUR_REDIS_URL", token="YOUR_TOKEN")

def delete_all_entries():
  keys = redis.keys("*") # Match all keys
  redis.delete(*keys)


delete_all_entries()
```

--------------------------------

TITLE: QStash Bulk Cancel Messages API Reference
DESCRIPTION: Detailed API documentation for the bulk message cancellation endpoint, including method, URL, authentication, request body parameters, and response structure.

SOURCE: https://upstash.com/docs/qstash/api/messages/bulk-cancel.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: DELETE https://qstash.upstash.io/v2/messages
Authentication: Bearer Token

Request Body Parameters:
- messageIds (Array): The list of message IDs to cancel.
- queueName (string): Filter messages to cancel by queue name.
- url (string): Filter messages to cancel by destination URL.
- topicName (string): Filter messages to cancel by URL Group (topic) name.
- fromDate (number): Filter messages to cancel by starting date, in milliseconds (Unix timestamp). This is inclusive.
- toDate (number): Filter messages to cancel by ending date, specified in milliseconds (Unix timestamp). This is inclusive.
- scheduleId (string): Filter messages to cancel by schedule ID.
- callerIP (string): Filter messages to cancel by IP address of publisher.

Response Body:
- cancelled (number): The number of cancelled messages.
```

--------------------------------

TITLE: QStash API Request Body Handling
DESCRIPTION: Explains how QStash handles the message body during delivery, ensuring it is passed to the destination API endpoint exactly as it was sent by the publisher, without any modifications to its content or format.

SOURCE: https://upstash.com/docs/qstash/howto/receiving.mdx

LANGUAGE: APIDOC
CODE:
```
Body:
  Description: The body is passed as is, we do not modify it at all. If you send a JSON body, you will receive a JSON body. If you send a string, you will receive a string.
```

--------------------------------

TITLE: QStash Enqueue Message API Reference
DESCRIPTION: Detailed API documentation for enqueuing messages to QStash. This endpoint allows sending messages to a specified queue or destination with options for deduplication and custom headers.

SOURCE: https://upstash.com/docs/qstash/api/enqueue.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/v2/enqueue/{queueName}/{destination}
Authentication: Bearer Token

Request Parameters:
- path:
    - queueName (string, required): The name of the queue that message will be enqueued on.
      If doesn't exist, it will be created automatically.
    - destination (string, required): Destination can either be a topic name or id that you configured in the
      Upstash console, a valid url where the message gets sent to, or a valid
      QStash API name like `api/llm`. If the destination is a URL, make sure
      the URL is prefixed with a valid protocol (`http://` or `https://`)
- header:
    - Upstash-Deduplication-Id (string, optional): Id to use while deduplicating messages, so that only one message with
      the given deduplication id is published.
    - Upstash-Content-Based-Deduplication (boolean, optional): When set to true, automatically deduplicates messages based on their content,
      so that only one message with the same content is published.

      Content based deduplication creates unique deduplication ids based on the
      following message fields:

      - Destination
      - Body
      - Headers

Response Examples:
- URL:
```json
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```
- URL Group:
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

TITLE: Cloudflare Worker Local Testing and Deployment
DESCRIPTION: Commands to test a Cloudflare Worker locally using `wrangler dev` and deploy it to the Cloudflare environment using `wrangler deploy`.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: bash
CODE:
```
npx wrangler dev
npx wrangler deploy
```

--------------------------------

TITLE: Send Single Email with QStash and Resend (TypeScript)
DESCRIPTION: Demonstrates how to send a single email using the `qstash-js` SDK's `publishJSON` method with the Resend provider. It requires `QSTASH_TOKEN` and `RESEND_TOKEN` for authentication. The `body` field accepts standard Resend Send Email API parameters like `from`, `to`, `subject`, and `html`.

SOURCE: https://upstash.com/docs/qstash/integrations/resend.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Chat Completion API Response Object Definition
DESCRIPTION: Defines the structure of the JSON response returned by the chat completion endpoint, including nested objects for choices, messages, log probabilities, and usage statistics. This structure is returned when the `stream` parameter is `false` or not set.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: APIDOC
CODE:
```
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
  object: string - The object type, which is always `chat.completion`.
  usage: Object - Usage statistics for the completion request.
    completion_tokens: number - Number of tokens in the generated completion.
    prompt_tokens: number - Number of tokens in the prompt.
```

--------------------------------

TITLE: Queue Image Processing Task in Next.js with QStash
DESCRIPTION: This code snippet demonstrates how to upload an image and then asynchronously queue an image processing task using QStash. It shows publishing a JSON message with a target URL and body containing the image ID, returning a response with the QStash message ID. The URL needs to be publicly available for QStash to call.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
import { Client } from "@upstash/qstash"
import { NextResponse } from "next/server"

const client = new Client({ token: process.env.QSTASH_TOKEN! })

export const POST = async (req: Request) => {
  // Image uploading logic

  // 👇 Once uploading is done, queue an image processing task
  const result = await client.publishJSON({
    url: "https://your-api-endpoint.com/process-image",
    body: { imageId: "123" }
  })

  return NextResponse.json({
    message: "Image queued for processing!",
    qstashMessageId: result.messageId
  })
}
```

--------------------------------

TITLE: QStash Publish Message Response Formats
DESCRIPTION: Illustrates the expected JSON response structures from the QStash publish endpoint for both single message and group message publications, including message ID, URL, and deduplication status.

SOURCE: https://upstash.com/docs/qstash/api/publish.mdx

LANGUAGE: json
CODE:
```
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}
```

LANGUAGE: json
CODE:
```
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

TITLE: Create Next.js API Route for Long-Running Background Task
DESCRIPTION: Defines a Next.js API route (`src/app/api/long-task/route.ts`) that handles POST requests. This endpoint simulates a long-running task by making multiple delayed `fetch` calls to an external service, demonstrating how QStash can invoke custom backend logic.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: Pause and Resume an Upstash QStash Queue
DESCRIPTION: Shows how to pause and then resume an Upstash QStash queue using the `@upstash/qstash` client. It demonstrates checking the queue's paused status after the operation. Note that these operations can take up to a minute to complete.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/queues.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Retrieve a QStash Schedule by ID
DESCRIPTION: Demonstrates how to fetch details of an existing schedule using its unique ID with the QStash Python SDK, and then access its properties like the cron expression.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
schedule = client.schedule.get("<schedule-id>")

print(schedule.cron)
```

--------------------------------

TITLE: Implement AWS Lambda Handler for QStash Webhook Verification
DESCRIPTION: This Python `lambda_handler` function processes incoming AWS Lambda events. It parses QStash signature and signing keys from environment variables and headers, then attempts to verify the webhook signature using both current and next signing keys. If verification fails, it returns a 400 error; otherwise, it proceeds with custom logic.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: python
CODE:
```
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

TITLE: QStash Queue API: Upsert Queue Endpoint
DESCRIPTION: Documents the API endpoint for creating or updating a queue in QStash, including request parameters, authentication, and response codes. Note the deprecation warning for the 'parallelism' parameter.

SOURCE: https://upstash.com/docs/qstash/api/queues/upsert.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: POST https://qstash.upstash.io/v2/queues/
Authentication: Bearer Token

Request Parameters (Body):
  queueName:
    Type: string
    Required: true
    Description: The name of the queue.
  parallelism:
    Type: int
    Required: true
    Description: The number of parallel consumers consuming from the queue.
      Warning: Setting parallelism with queues will be deprecated at some point. Please check the Flow Control page for detailed information.

Response Codes:
  200: If the queue is added successfully.
  412: If it fails because of the allowed number of queues limit.
```

--------------------------------

TITLE: Create a schedule with timeout
DESCRIPTION: Illustrates how to specify a custom timeout value for the HTTP request made to the schedule's destination URL. The `timeout` parameter, provided in seconds, limits how long QStash will wait for a response from the target endpoint.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  url: "https://my-api...",
  cron: "* * * * *",
  timeout: "30" // 30 seconds timeout
});
```

--------------------------------

TITLE: Qstash Retry Backoff Headers
DESCRIPTION: Qstash now supports additional HTTP headers for controlling retry backoff timing, enhancing rate limit handling.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Retry Backoff Headers:
  - Retry-After: string (standard)
  - X-RateLimit-Reset: string (custom)
  - X-RateLimit-Reset-Requests: string (custom)
  - X-RateLimit-Reset-Tokens: string (custom)
```

--------------------------------

TITLE: Receive and Verify QStash Message in Next.js
DESCRIPTION: This snippet shows how to create an endpoint to receive and process messages from QStash. It includes verifying the message signature using `verifySignatureAppRouter` to ensure the message originates from QStash, then parsing the request body to extract the image ID for processing.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: tsx
CODE:
```
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

TITLE: Publish to a QStash URL Group
DESCRIPTION: This URL demonstrates how to publish a message to a predefined QStash URL Group. URL Groups allow for server-side templating and can fan-out a single incoming webhook call to multiple target endpoints, simplifying configuration and enabling complex routing scenarios.

SOURCE: https://upstash.com/docs/qstash/howto/webhook.mdx

LANGUAGE: HTTP
CODE:
```
https://qstash.upstash.io/v2/publish/<URL_GROUP_NAME>?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Batching QStash Messages with Custom Headers and Body
DESCRIPTION: This snippet demonstrates how to send a batch of messages to the QStash API. Each message in the batch can specify its own destination (either a URL group or a direct URL), custom headers (e.g., Upstash-Delay for scheduling, Upstash-Forward-Hello for custom data), and a specific body. This allows for fine-grained control over individual messages within a single batch request, optimizing API calls.

SOURCE: https://upstash.com/docs/qstash/features/batch.mdx

LANGUAGE: cURL
CODE:
```
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

LANGUAGE: TypeScript
CODE:
```
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

LANGUAGE: Python
CODE:
```
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

TITLE: Combine Rate and Parallelism Limits in QStash Flow Control
DESCRIPTION: This snippet shows how to apply both rate and parallelism limits simultaneously using QStash Flow Control. It demonstrates setting a rate (e.g., 20 calls/sec) and a parallelism limit (e.g., 10 concurrent calls) with a single flow control key, allowing for fine-grained control over message delivery and concurrency.

SOURCE: https://upstash.com/docs/qstash/features/flowcontrol.mdx

LANGUAGE: TypeScript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 20, parallelism: 10 }
});
```

LANGUAGE: cURL
CODE:
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
            -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
            -H "Upstash-Flow-Control-Value:Rate=20,Parallelism=10" \
           'https://qstash.upstash.io/v2/publish/https://example.com' \
            -d '{"message":"Hello, World!"}'
```

--------------------------------

TITLE: QStash Callback Header Forwarding
DESCRIPTION: Illustrates how to configure QStash to forward custom headers to callback endpoints using specific `Upstash-Callback-Forward-` and `Upstash-Failure-Callback-Forward-` prefixes.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: APIDOC
CODE:
```
Upstash-Callback-Forward-MyCustomHeader
Upstash-Failure-Callback-Forward-MyCustomHeader
```

--------------------------------

TITLE: Integrate Helicone Analytics with QStash Anthropic LLM Requests
DESCRIPTION: Explains how to add Helicone analytics to QStash LLM requests by including the `analytics` configuration within the API object. This allows for monitoring usage when publishing requests to Anthropic, requiring a Helicone API key.

SOURCE: https://upstash.com/docs/qstash/integrations/anthropic.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Import QStash Receiver Class
DESCRIPTION: Imports the `Receiver` class from the `@upstash/qstash` library. This class is fundamental for handling and verifying incoming QStash webhook signatures within your Cloudflare Worker.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: ts
CODE:
```
import { Receiver } from "@upstash/qstash";
```

--------------------------------

TITLE: QStash API Rate Limit Headers
DESCRIPTION: This section documents the specific HTTP headers returned by the QStash API when various rate limits are exceeded. It categorizes headers by daily, burst, and chat-based limits, providing details on the maximum allowed requests/tokens, remaining counts, and reset times.

SOURCE: https://upstash.com/docs/qstash/api/api-ratelimiting.mdx

LANGUAGE: APIDOC
CODE:
```
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

TITLE: Authenticate QStash API with Query Parameter using cURL
DESCRIPTION: This snippet provides an alternative authentication method for the QStash API, suitable for environments where setting HTTP headers is not feasible. It shows how to pass the QSTASH_TOKEN as a 'qstash_token' query parameter in the URL for cURL requests.

SOURCE: https://upstash.com/docs/qstash/api/authentication.mdx

LANGUAGE: bash
CODE:
```
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>
```

--------------------------------

TITLE: QStash Publish Message API Endpoint Definition
DESCRIPTION: Documents the QStash API endpoint for publishing messages, including the HTTP method, URL structure, authentication requirements, path parameters, and various request headers for controlling message delivery and deduplication.

SOURCE: https://upstash.com/docs/qstash/api/publish.mdx

LANGUAGE: APIDOC
CODE:
```
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

TITLE: Publish a message with timeout
DESCRIPTION: This snippet demonstrates how to set a timeout for a QStash message. The `timeout` parameter specifies the maximum duration QStash will wait for a response when calling the target URL, preventing long-running requests from blocking the system.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/publish.mdx

LANGUAGE: python
CODE:
```
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

TITLE: Schedule ID Header for User Endpoints
DESCRIPTION: The `Schedule ID` is now passed as a header when Qstash calls a user's endpoint, allowing for better context.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Outgoing Message Header:
  - Header: X-Qstash-Schedule-ID
  - Type: string
  - Purpose: Identifies the schedule associated with the message.
```

--------------------------------

TITLE: Upstash-Signature JWT Claims Reference
DESCRIPTION: Detailed documentation of the standard and custom claims (fields) included in the JWT payload within the `Upstash-Signature` header, explaining their purpose, data types, and specific values.

SOURCE: https://upstash.com/docs/qstash/features/security.mdx

LANGUAGE: APIDOC
CODE:
```
Upstash-Signature JWT Claims:
  iss (string): The issuer field, always 'Upstash'.
  sub (string): The URL of your endpoint where the request is sent.
                Example: 'https://my-app.vercel.app/api/endpoint'
  exp (integer): A Unix timestamp (seconds) after which the request should no longer be accepted. JWTs have a default lifetime of 5 minutes.
  iat (integer): A Unix timestamp (seconds) when this JWT was created.
  nbf (integer): A Unix timestamp (seconds) before which this request should not be accepted.
  jti (string): A unique identifier for this token.
  body (string): A base64 encoded SHA256 hash of the request body, using URL encoding as specified in RFC 4648, section 5.
```

--------------------------------

TITLE: Publish Message to QStash via cURL
DESCRIPTION: This cURL command demonstrates how to publish a JSON message to a QStash endpoint, which in this context is the public URL of the deployed AWS Lambda function. It sends a POST request, includes the necessary Authorization Bearer token for authentication with QStash, sets the Content-Type header to application/json, and provides a simple JSON payload.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: bash
CODE:
```
curl --request POST "https://qstash.upstash.io/v2/publish/https://urzdbfn4et56vzeasu3fpcynym0zerme.lambda-url.eu-west-1.on.aws" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

--------------------------------

TITLE: Qstash Batch Publish Messages API
DESCRIPTION: New API endpoint for publishing multiple messages in a single batch.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API: Batch Publish Messages
  - Endpoint: /v2/messages/batch
  - Method: POST
  - Purpose: Publish an array of messages efficiently.
```

--------------------------------

TITLE: QStash Backoff Algorithm Formula
DESCRIPTION: Illustrates the mathematical formula used by QStash to calculate the delay between retries. The delay is an exponential function of the number of retries, capped at 1 day (86400 seconds).

SOURCE: https://upstash.com/docs/qstash/features/retry.mdx

LANGUAGE: text
CODE:
```
n = how many times this request has been retried
delay =  min(86400, e ** (2.5*n)) // in seconds
```

--------------------------------

TITLE: Failure Callback Support for Scheduled Messages API
DESCRIPTION: Scheduled messages now support a failure callback mechanism, configurable via the schedules creation API.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Schedules API: Failure Callback
  - Endpoint: /v2/schedules/create
  - Parameter: failureCallback (string, optional)
    - Description: URL to be called if the scheduled message fails.
  - Parameter: failureCallbackHeaders (object, optional)
    - Description: Headers to be sent with the failure callback.
```

--------------------------------

TITLE: Implement AWS Lambda handler for QStash verification
DESCRIPTION: This TypeScript code defines an AWS Lambda handler function (`handler`) that processes incoming API Gateway events. It attempts to verify the `upstash-signature` header using both current and next signing keys to allow for key rotation. If verification fails, it returns a 400 error; otherwise, it proceeds with business logic and returns a 200 success.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: List all messages from Upstash QStash DLQ with pagination in TypeScript
DESCRIPTION: This snippet demonstrates how to retrieve all messages from the Dead Letter Queue (DLQ) using pagination. It iterates through the results using a cursor until all messages are fetched.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/dlq.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: Upstash-Timeout Header for Publish API
DESCRIPTION: The `Upstash-Timeout` header can now be used with the publish API to specify a timeout for message processing.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Publish API Header:
  - Header: Upstash-Timeout
  - Type: int (milliseconds)
  - Purpose: Specifies the maximum time (in milliseconds) the message should be processed.
```

--------------------------------

TITLE: Overwrite Existing QStash Schedule
DESCRIPTION: Shows how to overwrite an existing schedule by explicitly providing a `scheduleId` when creating a new schedule. This allows updating an existing scheduled task.

SOURCE: https://upstash.com/docs/qstash/features/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  scheduleId: "existingScheduleId",
  cron: "* * * * *",
});
```

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Cron: * * * * *" \
    -H "Upstash-Schedule-Id: existingScheduleId" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'
```

--------------------------------

TITLE: QStash DLQ API: List Messages
DESCRIPTION: Documents the QStash API endpoint for listing and paginating messages in the Dead Letter Queue (DLQ). It details the HTTP method, URL, authentication, and all available query parameters for filtering and pagination, as well as the structure of the response.

SOURCE: https://upstash.com/docs/qstash/api/dlq/listMessages.mdx

LANGUAGE: APIDOC
CODE:
```
API: GET https://qstash.upstash.io/v2/dlq
Authentication: Bearer Token

Request Query Parameters:
- cursor (string): By providing a cursor you can paginate through all of the messages in the DLQ.
- messageId (string): Filter DLQ messages by message id.
- url (string): Filter DLQ messages by url.
- topicName (string): Filter DLQ messages by url group.
- scheduleId (string): Filter DLQ messages by schedule id.
- queueName (string): Filter DLQ messages by queue name.
- api (string): Filter DLQ messages by API name.
- fromDate (number): Filter DLQ messages by starting date, in milliseconds (Unix timestamp). This is inclusive.
- toDate (number): Filter DLQ messages by ending date, in milliseconds (Unix timestamp). This is inclusive.
- responseStatus (number): Filter DLQ messages by HTTP response status code.
- callerIp (string): Filter DLQ messages by IP address of the publisher.
- count (number): The number of messages to return. Default and maximum is 100.
- order (string): The sorting order of DLQ messages by timestamp. Valid values are "earliestFirst" and "latestFirst". The default is "earliestFirst".

Response Fields:
- cursor (string): A cursor which you can use in subsequent requests to paginate through all messages. If no cursor is returned, you have reached the end of the messages.
- messages (Array<Object>): An array of DLQ message objects.
  - messageId (string)
  - topicId (string)
  - url (string)
  - method (string)
  - header (Object)
  - body (string)
  - createdAt (number)
  - state (string)
```

--------------------------------

TITLE: Upstash-Failure-Callback Header
DESCRIPTION: The `Upstash-Failure-Callback` header can be used to specify a URL for failure callbacks.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Message Header:
  - Header: Upstash-Failure-Callback
  - Type: string (URL)
  - Purpose: Specifies a URL to be invoked upon message processing failure.
```

--------------------------------

TITLE: Publish Message with Content-Based Deduplication
DESCRIPTION: Shows how to enable automatic content-based deduplication for messages by setting the `Upstash-Content-Based-Deduplication` header to `true`. QStash will generate a unique deduplication ID based on the message's destination, body, and specific forwarded headers, preventing duplicates within a 10-minute window.

SOURCE: https://upstash.com/docs/qstash/features/deduplication.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Content-Based-Deduplication: true" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/...'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  contentBasedDeduplication: true,
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Publish QStash Message with Absolute Delay using Upstash-Not-Before
DESCRIPTION: This section illustrates how to delay a QStash message until a specific future point in time. The delay is configured using the `Upstash-Not-Before` header or a `notBefore` parameter, which accepts a Unix timestamp in seconds (UTC). This ensures the message is not delivered before the exact specified time.

SOURCE: https://upstash.com/docs/qstash/features/delay.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Not-Before: 1657104947" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  notBefore: 1657104947,
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Next.js API Route: Handle QStash Long-Running Task
DESCRIPTION: This Next.js API route serves as the endpoint for QStash messages, designed to simulate a long-running background task. It verifies the incoming request signature using `@upstash/qstash/nextjs` and performs a repetitive `fetch` operation with a delay, demonstrating a typical background processing pattern.

SOURCE: https://upstash.com/docs/qstash/quickstarts/vercel-nextjs.mdx

LANGUAGE: ts
CODE:
```
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

TITLE: QStash Log Retrieval API Response Structure
DESCRIPTION: Defines the complete structure of the response object when retrieving logs from the QStash API, including pagination cursor, an array of detailed log events, and top-level message header/body information.

SOURCE: https://upstash.com/docs/qstash/api/logs/list.mdx

LANGUAGE: APIDOC
CODE:
```
Response:
  cursor: string
    Description: A cursor which you can use in subsequent requests to paginate through all logs. If no cursor is returned, you have reached the end of the logs.
  events: Array<LogEntry>
    Description: An array of log entries.
    LogEntry:
      time: int (required)
        Description: Timestamp of this log entry, in milliseconds.
      messageId: string (required)
        Description: The associated message id.
      header: Record<string, string[]> (required)
        Description: The headers of the message.
      body: string (required)
        Description: Base64 encoded body of the message.
      state: string (required)
        Description: The current state of the message at this point in time.
        Possible Values:
          CREATED: The message has been accepted and stored in QStash.
          ACTIVE: The task is currently being processed by a worker.
          RETRY: The task has been scheduled to retry.
          ERROR: The execution threw an error and the task is waiting to be retried or failed.
          DELIVERED: The message was successfully delivered.
          FAILED: The task has errored too many times or encountered an error that it cannot recover from.
          CANCEL_REQUESTED: The cancel request from the user is recorded.
          CANCELLED: The cancel request from the user is honored.
      error: string (optional)
        Description: An explanation what went wrong.
      nextDeliveryTime: int
        Description: The next scheduled time of the message (Unix timestamp in milliseconds).
      url: string
        Description: The destination url.
      topicName: string
        Description: The name of the URL Group (topic) if this message was sent through a topic.
      endpointName: int
        Description: The name of the endpoint if this message was sent through a URL Group.
      scheduleId: string
        Description: The scheduleId of the message if the message is triggered by a schedule.
      queueName: string
        Description: The name of the queue if this message is enqueued on a queue.
      responseStatus: int
        Description: The status code of the response. Only set if the state is `ERROR`.
      responseBody: string
        Description: The base64 encoded body of the response. Only set if the state is `ERROR`.
      responseHeaders: Record<string, string[]>
        Description: The headers of the response. Only set if the state is `ERROR`.
      timeout: int
        Description: The timeout (in milliseconds) of the outgoing http requests, after which Qstash cancels the request.
      method: string
        Description: Method is the HTTP method of the message for outgoing request.
      callback: string
        Description: Callback is the URL address where QStash sends the response of a publish.
      callbackHeaders: Record<string, string[]>
        Description: The headers that are passed to the callback url.
      failureCallback: string
        Description: Failure Callback is the URL address where QStash sends the response of a publish.
      failureCallbackHeaders: Record<string, string[]>
        Description: The headers that are passed to the failure callback url.
      maxRetries: int
        Description: The number of retries that should be attempted in case of delivery failure.
  header: string
    Description: The headers that are forwarded to the users endpoint.
  body: string
    Description: Base64 encoded body of the message.
```

--------------------------------

TITLE: Qstash Queue Name Validation Rules
DESCRIPTION: Updated validation rules for Qstash queue names to ensure consistency across API resources.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Queue Name Validation:
  - Must be alphanumeric
  - May include hyphens (-), underscores (_), or periods (.)
```

--------------------------------

TITLE: Failure Callback JSON Body Structure
DESCRIPTION: Defines the JSON structure of the body sent to the failure callback URL. It includes details about the delivery status, headers, body, retry attempts, DLQ ID, source message details, and timestamps.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: json
CODE:
```
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

--------------------------------

TITLE: Configure QStash Credentials in wrangler.toml
DESCRIPTION: YAML configuration for `wrangler.toml` to manually set QStash environment variables. This includes `QSTASH_URL`, `QSTASH_TOKEN`, `QSTASH_CURRENT_SIGNING_KEY`, and `QSTASH_NEXT_SIGNING_KEY`, which are necessary for your Cloudflare Worker to interact with QStash.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: yaml
CODE:
```
[vars]
QSTASH_URL="REPLACE_HERE"
QSTASH_TOKEN="REPLACE_HERE"
QSTASH_CURRENT_SIGNING_KEY="REPLACE_HERE"
QSTASH_NEXT_SIGNING_KEY="REPLACE_HERE"
```

--------------------------------

TITLE: Publish Message to a QStash URL Group
DESCRIPTION: Shows how to publish a message to a predefined URL Group in QStash, allowing a single message to be delivered to multiple API endpoints simultaneously. This simplifies sending messages to a collection of destinations by referencing a group name instead of individual URLs.

SOURCE: https://upstash.com/docs/qstash/howto/publishing.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/my-url-group'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  urlGroup: "my-url-group",
  body: { "hello": "world" }
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url_group="my-url-group",
    body={
        "hello": "world"
    }
)
```

--------------------------------

TITLE: Publish with Message Timeout (TypeScript)
DESCRIPTION: This snippet shows how to set a timeout for a published message. The timeout value specifies the maximum duration in seconds for QStash to wait when calling the target URL.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/publish.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  timeout: "30s" // 30 seconds timeout
});
```

--------------------------------

TITLE: Publish Message with Explicit Deduplication ID
DESCRIPTION: Demonstrates how to publish a message to QStash using a specific `Upstash-Deduplication-Id` header to prevent duplicate messages. If a message with the same ID is received within the deduplication window (10 minutes), it will be accepted but not enqueued, and a 202 Accepted status will be returned.

SOURCE: https://upstash.com/docs/qstash/features/deduplication.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Deduplication-Id: abcdef" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api..."'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  deduplicationId: "abcdef",
});
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.message.publish_json(
    url="https://my-api...",
    body={
        "hello": "world",
    },
    deduplication_id="abcdef",
)
```

--------------------------------

TITLE: Qstash Event Filtering API
DESCRIPTION: The events API now supports filtering capabilities.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Events API: Filtering
  - Endpoint: /v2/events
  - Purpose: Filter events based on specified criteria.
```

--------------------------------

TITLE: Authorize QStash API Requests with Bearer Token
DESCRIPTION: Demonstrates the required format for including the QStash authorization token in the `Authorization` HTTP header for all API requests.

SOURCE: https://upstash.com/docs/qstash/features/security.mdx

LANGUAGE: HTTP
CODE:
```
"Authorization": "Bearer <QSTASH_TOKEN>"
```

--------------------------------

TITLE: QStash Cancel Message API Reference
DESCRIPTION: Detailed API specification for the QStash message cancellation endpoint, including HTTP method, URL, authentication, request parameters, and expected response.

SOURCE: https://upstash.com/docs/qstash/api/messages/cancel.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: DELETE https://qstash.upstash.io/v2/messages/{messageId}
Authentication: Bearer Token
Description: Cancelling a message will remove it from QStash and stop it from being delivered in the future. If a message is in flight to your API, it might be too late to cancel.

Request Parameters:
  messageId:
    Type: string
    Required: true
    Description: The id of the message to cancel.

Response:
  Status Code: 202 OK
  Body: OK (for 202 Accepted)
```

--------------------------------

TITLE: Verify QStash Webhook Signature
DESCRIPTION: Demonstrates how to verify the incoming QStash webhook signature using the `receiver.verify` method. It requires extracting the `Upstash-Signature` header and the raw request body for validation.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: ts
CODE:
```
const body = await request.text();

const isValid = receiver.verify({
  signature: request.headers.get("Upstash-Signature")!,
  body,
});
```

--------------------------------

TITLE: Qstash Bulk Cancel Messages API
DESCRIPTION: New API endpoint for bulk canceling messages.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API: Bulk Cancel Messages
  - Endpoint: /v2/messages/bulk-cancel
  - Method: POST
  - Purpose: Cancel multiple messages simultaneously.
```

--------------------------------

TITLE: QStash Events API Response Structure
DESCRIPTION: Defines the structure of the response object returned by the QStash Events API, including details for cursor, events, and nested event properties like time, messageId, header, body, state, and various error and delivery-related information.

SOURCE: https://upstash.com/docs/qstash/api/events/list.mdx

LANGUAGE: APIDOC
CODE:
```
Response:
  cursor: string
    A cursor which you can use in subsequent requests to paginate through all events.
    If no cursor is returned, you have reached the end of the events.
  events: Array
    time: int (required)
      Timestamp of this log entry, in milliseconds
    messageId: string (required)
      The associated message id
    header: Record<string, string[]> (required)
      The headers of the message.
    body: string (required)
      Base64 encoded body of the message.
    state: string (required)
      The current state of the message at this point in time.
      Possible Values:
        CREATED: The message has been accepted and stored in QStash
        ACTIVE: The task is currently being processed by a worker.
        RETRY: The task has been scheduled to retry.
        ERROR: The execution threw an error and the task is waiting to be retried or failed.
        DELIVERED: The message was successfully delivered.
        FAILED: The task has errored too many times or encountered an error that it cannot recover from.
        CANCEL_REQUESTED: The cancel request from the user is recorded.
        CANCELLED: The cancel request from the user is honored.
    error: string (optional)
      An explanation what went wrong
    nextDeliveryTime: int
      The next scheduled time of the message.
      (Unix timestamp in milliseconds)
    url: string
      The destination url
    topicName: string
      The name of the URL Group (topic) if this message was sent through a topic
    endpointName: int
      The name of the endpoint if this message was sent through a URL Group
    scheduleId: string
      The scheduleId of the message if the message is triggered by a schedule
    queueName: string
      The name of the queue if this message is enqueued on a queue
    header: string
      The headers that are forwarded to the users endpoint
    body: string
      Base64 encoded body of the message
    responseStatus: int
      The status code of the response. Only set if the state is `ERROR`
    responseBody: string
      The base64 encoded body of the response. Only set if the state is `ERROR`
    responseHeaders: Record<string, string[]>
      The headers of the response. Only set if the state is `ERROR`
    timeout: int
      The timeout(in milliseconds) of the outgoing http requests, after which Qstash cancels the request
    method: string
      Method is the HTTP method of the message for outgoing request
    callback: string
      Callback is the URL address where QStash sends the response of a publish
    callbackHeaders: Record<string, string[]>
      The headers that are passed to the callback url
    failureCallback: string
      Failure Callback is the URL address where QStash sends the response of a publish
    failureCallbackHeaders: Record<string, string[]>
      The headers that are passed to the failure callback url
    maxRetries: int
      The number of retries that should be attempted in case of delivery failure
```

--------------------------------

TITLE: QStash API Request Headers
DESCRIPTION: Details the standard and custom HTTP headers included by QStash when delivering a message to a destination API endpoint. It specifies the purpose and typical values for each header, including those related to message identification, retry attempts, and security signatures.

SOURCE: https://upstash.com/docs/qstash/howto/receiving.mdx

LANGUAGE: APIDOC
CODE:
```
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

TITLE: Configure Headers for a QStash URL Group using cURL
DESCRIPTION: This cURL command illustrates how to update a QStash URL Group to define default headers. These headers, such as 'Upstash-Header-Forward' and 'Upstash-Retries', will automatically apply to all messages published to this group, providing consistent behavior for webhook processing.

SOURCE: https://upstash.com/docs/qstash/howto/webhook.mdx

LANGUAGE: Shell
CODE:
```
curl -X PATCH https://qstash.upstash.io/v2/topics/<URL_GROUP_NAME> \n    -H "Authorizarion: Bearer <QSTASH_TOKEN>"
    -d '{
        "headers": {
            "Upstash-Header-Forward": ["true"],
            "Upstash-Retries": "3"
        }
    }'
```

--------------------------------

TITLE: Verify Upstash QStash Webhook Signature in AWS Lambda (TypeScript)
DESCRIPTION: This TypeScript code demonstrates how to verify incoming Upstash QStash webhook signatures within an AWS Lambda function. It utilizes the `@upstash/qstash` SDK's `Receiver` class, checking for the `upstash-signature` header, constructing the lambda function's URL, and using `receiver.verify` to validate the request body and signature. The function returns appropriate HTTP status codes (401 for missing/invalid signature, 200 for success) and handles potential errors during verification.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: typescript
CODE:
```
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

TITLE: QStash Callback Response Body Structure
DESCRIPTION: Defines the JSON structure of the payload sent by QStash to the specified callback URL. It includes details about the original message's status, headers, body (base64 encoded), retry information, and various metadata related to the source message.

SOURCE: https://upstash.com/docs/qstash/features/callbacks.mdx

LANGUAGE: APIDOC
CODE:
```
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
  "sourceBody": "YmFzZTY0kZWQgcm9keQ==",  // The base64 encoded body of the message that triggered the callback
  "notBefore": "1701198458025",           // The unix timestamp of the message that triggered the callback is/will be delivered in milliseconds
  "createdAt": "1701198447054",           // The unix timestamp of the message that triggered the callback is created in milliseconds
  "scheduleId": "scd_xxx",                // The scheduleId of the message if the message is triggered by a schedule
  "callerIP": "178.247.74.179"            // The IP address where the message that triggered the callback is published from
}
```

--------------------------------

TITLE: API Reference: Upsert URL Group and Endpoint
DESCRIPTION: Detailed API specification for adding or updating endpoints within a QStash URL Group. This endpoint creates the URL Group and/or endpoint if they do not exist, providing a flexible way to manage message routing.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/add-endpoint.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://qstash.upstash.io/v2/topics/{urlGroupName}/endpoints
Auth: Bearer Token

Path Parameters:
  urlGroupName (string, required):
    The name of your URL Group (topic). If it doesn't exist yet, it will be created.

Body Parameters:
  endpoints (Array, required):
    The endpoints to add to the URL Group.
    Array elements:
      name (string, optional):
        The name of the endpoint.
      url (string, required):
        The URL of the endpoint.

Response:
  200 OK:
    Returned if the endpoints are added successfully.
```

--------------------------------

TITLE: API Reference: Remove Endpoints
DESCRIPTION: Detailed API documentation for the DELETE /v2/topics/{urlGroupName}/endpoints endpoint, including request parameters, authentication method, and expected response.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove-endpoint.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint: DELETE https://qstash.upstash.io/v2/topics/{urlGroupName}/endpoints
Authentication: Bearer Token

Path Parameters:
  urlGroupName (string, required):
    Description: The name of your URL Group. If it doesn't exist, an error is returned.

Body Parameters:
  endpoints (Array, required):
    Description: The endpoints to be removed from the URL Group.
    Constraints: Either 'name' or 'url' must be provided for each endpoint.
    Properties:
      - name (string, optional):
          Description: The name of the endpoint.
      - url (string, optional):
          Description: The URL of the endpoint.

Response:
  200 OK: Indicates that the endpoints have been removed successfully.
```

--------------------------------

TITLE: API Response Field: total_tokens
DESCRIPTION: This API response field, `total_tokens`, provides the cumulative count of tokens consumed by a request, encompassing both prompt and completion tokens. It is typically found in responses from AI or messaging services to indicate resource usage.

SOURCE: https://upstash.com/docs/qstash/api/llm/create.mdx

LANGUAGE: APIDOC
CODE:
```
<ResponseField name="total_tokens" type="number">
  Total number of tokens used in the request (prompt + completion).
</ResponseField>
```

--------------------------------

TITLE: Monitor Cloudflare Worker Logs
DESCRIPTION: Output from `npx wrangler tail` demonstrating successful log retrieval and a QStash webhook processing event, including signature validation, after a message is published.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: bash
CODE:
```
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

TITLE: Set QStash Rate Limit for Message Delivery
DESCRIPTION: This snippet demonstrates how to configure a rate limit for messages sent to an endpoint using QStash Flow Control. It shows how to set a maximum number of calls per second (e.g., 10) using a specified flow control key. Messages exceeding this rate will be delayed by QStash.

SOURCE: https://upstash.com/docs/qstash/features/flowcontrol.mdx

LANGUAGE: TypeScript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10 }
});
```

LANGUAGE: cURL
CODE:
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
            -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
            -H "Upstash-Flow-Control-Value:Rate=10" \
           'https://qstash.upstash.io/v2/publish/https://example.com' \
            -d '{"message":"Hello, World!"}'
```

--------------------------------

TITLE: Retrieve a Specific QStash DLQ Message (Python)
DESCRIPTION: This Python snippet shows how to fetch a single message from the QStash Dead Letter Queue (DLQ) by its unique identifier. The `client.dlq.get()` method is used to directly access a specific failed message for inspection or re-processing.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/dlq.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
msg = client.dlq.get("<dlq-id>")
```

--------------------------------

TITLE: API Endpoint: Pause QStash Queue
DESCRIPTION: Defines the HTTP endpoint, authentication method, request parameters, and expected response for pausing an Upstash QStash queue.

SOURCE: https://upstash.com/docs/qstash/api/queues/pause.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/v2/queues/{queueName}/pause
Authentication: Bearer Token

Request:
  Path Parameters:
    queueName (string, required): The name of the queue to pause.

Response:
  Status: 200 OK
  Description: The queue was paused successfully.
```

--------------------------------

TITLE: Publish QStash Message with Relative Delay using Upstash-Delay
DESCRIPTION: This section demonstrates how to delay a QStash message by a specified duration relative to its publication time. The delay is set using the `Upstash-Delay` header or a `delay` parameter, accepting formats like '10s', '1m', '2h', or '7d'. This ensures the message is delivered only after the specified period.

SOURCE: https://upstash.com/docs/qstash/features/delay.mdx

LANGUAGE: shell
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 1m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  delay: 60,
});
```

LANGUAGE: python
CODE:
```
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

TITLE: Authenticate QStash API with Bearer Token using cURL
DESCRIPTION: This snippet demonstrates how to authenticate requests to the QStash API by including the QSTASH_TOKEN as a Bearer token in the 'Authorization' HTTP header when using cURL. The token is obtained from the Upstash console.

SOURCE: https://upstash.com/docs/qstash/api/authentication.mdx

LANGUAGE: bash
CODE:
```
curl https://qstash.upstash.io/v2/publish/... \
  -H "Authorization: Bearer <QSTASH_TOKEN>"
```

--------------------------------

TITLE: Remove URL Group using Go HTTP Client
DESCRIPTION: Shows how to remove a URL group in Go using the standard `net/http` package. The code constructs a DELETE request, sets the Authorization header, and executes the request.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove.mdx

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("DELETE", "https://qstash.upstash.io/v2/topics/my-url-group", nil)
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

--------------------------------

TITLE: API Reference: Pause Schedule Endpoint
DESCRIPTION: Details for the API endpoint to pause an active schedule. This endpoint requires bearer token authentication. The `scheduleId` path parameter is mandatory. A successful request returns a 200 OK status.

SOURCE: https://upstash.com/docs/qstash/api/schedules/pause.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/v2/schedules/{scheduleId}/pause
Authentication: Bearer Token

Path Parameters:
  scheduleId (string, required): The id of the schedule to pause.

Response:
  200 OK: Schedule paused successfully.
```

--------------------------------

TITLE: Define Cloudflare Worker Environment Variables for QStash
DESCRIPTION: Defines the `Env` interface in TypeScript to include `QSTASH_CURRENT_SIGNING_KEY` and `QSTASH_NEXT_SIGNING_KEY`. These environment variables are crucial for the `Receiver` to validate QStash webhook signatures.

SOURCE: https://upstash.com/docs/qstash/quickstarts/cloudflare-workers.mdx

LANGUAGE: ts
CODE:
```
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string;
  QSTASH_NEXT_SIGNING_KEY: string;
}
```

--------------------------------

TITLE: Python Function to Verify QStash Webhook Signature (JWT)
DESCRIPTION: This `verify` function handles the actual validation of the QStash webhook signature, which is a JWT. It decodes the JWT, verifies its structure, checks the signature using HMAC-SHA256, validates claims like issuer, subject (URL), expiration, and 'not before' time, and finally compares the body hash if a body is present. It raises exceptions for any verification failures.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/python.mdx

LANGUAGE: python
CODE:
```
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

TITLE: New Event Fields in Qstash REST API
DESCRIPTION: New fields added to the Qstash events REST API (`/qstash/api/events/list`) to provide more detailed information about message processing and callbacks.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Events REST API Fields:
  - Timeout: int
  - Method: string
  - Callback: string
  - CallbackHeaders: object
  - FailureCallback: string
  - FailureCallbackHeaders: object
  - MaxRetries: int
```

--------------------------------

TITLE: Resume Schedule API Endpoint
DESCRIPTION: Documentation for the API endpoint to resume a paused QStash schedule. This endpoint marks a paused schedule as active, ensuring upcoming messages are delivered. If the schedule is already active, this action has no effect.

SOURCE: https://upstash.com/docs/qstash/api/schedules/resume.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: POST https://qstash.upstash.io/v2/schedules/{scheduleId}/resume
Description: Resume a paused schedule.
Authentication: Bearer Token
Path Parameters:
  scheduleId (string, required): The ID of the schedule to resume.
Response:
  Status: 200 OK
  Description: Schedule resumed successfully.
```

--------------------------------

TITLE: Upstash-Caller-IP Header for Outgoing Messages
DESCRIPTION: Outgoing messages now include the `Upstash-Caller-IP` header, providing the IP address of the caller.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash Outgoing Message Header:
  - Header: Upstash-Caller-IP
  - Type: string (IP address)
  - Purpose: Provides the IP address of the message sender.
```

--------------------------------

TITLE: Access Trigger Event for QStash Webhook Verification
DESCRIPTION: This Pipedream expression is used to pass the entire incoming HTTP request event from the trigger step to the QStash 'Verify Webhook' action. It ensures the action processes the correct request body for verification, allowing Pipedream to validate the authenticity of QStash messages.

SOURCE: https://upstash.com/docs/qstash/integrations/pipedream.mdx

LANGUAGE: Pipedream Expression
CODE:
```
{{ steps.trigger.event }}
```

--------------------------------

TITLE: Delete a QStash Schedule by ID
DESCRIPTION: Shows how to remove an existing schedule from QStash using its unique ID via the Python SDK.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/schedules.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.schedule.delete("<schedule-id>")
```

--------------------------------

TITLE: Qstash DLQ Bulk Delete Messages API
DESCRIPTION: New API endpoint for bulk deleting messages from the Dead Letter Queue (DLQ).

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API: DLQ Bulk Delete Messages
  - Endpoint: /v2/dlq/deleteMessages
  - Method: POST
  - Purpose: Delete multiple messages from the DLQ simultaneously.
```

--------------------------------

TITLE: Remove an endpoint from a URL Group
DESCRIPTION: This code demonstrates how to remove one or more specific endpoints from an existing URL group. It initializes the `@upstash/qstash` client and then calls the `removeEndpoints` method on the `urlGroups` service. The method requires the name of the URL group and an array of endpoint URLs to be removed.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.removeEndpoints({
  name: "urlGroupName",
  endpoints: [{ url: "https://my-endpoint-1" }]
});
```

--------------------------------

TITLE: Implement QStash signature verification function
DESCRIPTION: This TypeScript function (`verify`) manually validates a QStash signature (JWT) against a provided signing key, request body, and URL. It checks the JWT structure, signature, issuer, subject (URL), expiration, and 'not before' times. It also verifies the body hash if a body is present, ensuring data integrity. This function is crucial for secure processing of QStash webhooks.

SOURCE: https://upstash.com/docs/qstash/quickstarts/aws-lambda/nodejs.mdx

LANGUAGE: ts
CODE:
```
/**
 * @param jwt - The content of the `upstash-signature` header (JWT)
 * @param signingKey - The signing key to use to verify the signature (Get it from Upstash Console)
 * @param body - The raw body of the request
 * @param url - The public URL of the lambda function
 */
async function verify(
  jwt: string,
  signingKey: string,
  body: string | null,
  url: string
): Promise<void> {
  const split = jwt.split(".")
  if (split.length != 3) {
    throw new Error("Invalid JWT")
  }
  const [header, payload, signature] = split

  if (
    signature !=
    createHmac("sha256", signingKey)
      .update(`${header}.${payload}`)
      .digest("base64url")
  ) {
    throw new Error("Invalid JWT signature")
  }

  // JWT is verified, start looking at payload claims
  const p: {
    sub: string
    iss: string
    exp: number
    nbf: number
    body: string
  } = JSON.parse(Buffer.from(payload, "base64url").toString())

  if (p.iss !== "Upstash") {
    throw new Error(`invalid issuer: ${p.iss}, expected "Upstash"`)
  }
  if (p.sub !== url) {
    throw new Error(`invalid subject: ${p.sub}, expected "${url}"`)
  }

  const now = Math.floor(Date.now() / 1000)
  if (now > p.exp) {
    throw new Error("token has expired")
  }
  if (now < p.nbf) {
    throw new Error("token is not yet valid")
  }

  if (body != null) {
    if (
      p.body.replace(/=+$/, "") !=
      createHash("sha256").update(body).digest("base64url")
    ) {
      throw new Error("body hash does not match")
    }
  }
}
```

--------------------------------

TITLE: API Reference: Remove Queue Endpoint
DESCRIPTION: Defines the HTTP DELETE endpoint for removing a queue from Upstash QStash, including authentication method, path parameters, and expected response status.

SOURCE: https://upstash.com/docs/qstash/api/queues/remove.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: DELETE https://qstash.upstash.io/v2/queues/{queueName}
Authentication: Bearer Token
Parameters:
  queueName (string, required): The name of the queue to remove.
Response:
  Status: 200 OK
  Description: The queue was removed successfully, or it doesn't exist.
```

--------------------------------

TITLE: Filter logs by state and count
DESCRIPTION: Shows how to filter Upstash QStash logs by a specific state (e.g., 'DELIVERED') and limit the number of returned results to a maximum count (e.g., 50). This allows for targeted retrieval of log subsets.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/logs.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.logs({
  filter: {
    state: "DELIVERED",
    count: 50
  }
});
```

--------------------------------

TITLE: QStash Batch API Request Body Structure
DESCRIPTION: Defines the structure of each message object within the array sent to the QStash batch API endpoint. Each message specifies a destination, optional headers, and an optional body.

SOURCE: https://upstash.com/docs/qstash/api/messages/batch.mdx

LANGUAGE: APIDOC
CODE:
```
destination: string
headers: headers object
body: string
```

--------------------------------

TITLE: Set QStash Parallelism Limit for Concurrent Calls
DESCRIPTION: This snippet illustrates how to set a parallelism limit for messages in QStash, controlling the number of active calls to an endpoint at any given time. It demonstrates setting a limit (e.g., 10 concurrent calls) using a flow control key. Active calls are defined as those for which a response has not yet been received.

SOURCE: https://upstash.com/docs/qstash/features/flowcontrol.mdx

LANGUAGE: TypeScript
CODE:
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", parallelism: 10 }
});
```

LANGUAGE: cURL
CODE:
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
            -H "Upstash-Flow-Control-Key:USER_GIVEN_KEY"  \
            -H "Upstash-Flow-Control-Value:Parallelism=10" \
           'https://qstash.upstash.io/v2/publish/https://example.com' \
            -d '{"message":"Hello, World!"}'
```

--------------------------------

TITLE: Delete a URL Group
DESCRIPTION: This snippet shows how to completely delete an entire URL group by its name. After initializing the `@upstash/qstash` client, it invokes the `delete` method on the `urlGroups` service, passing the name of the URL group to be removed. This action permanently removes the group and all its associated endpoints.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/url-groups.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const urlGroups = client.urlGroups;
await urlGroups.delete("urlGroupName");
```

--------------------------------

TITLE: API Reference: Remove Schedule Endpoint
DESCRIPTION: Details the HTTP DELETE endpoint for removing a schedule from QStash, specifying the path parameter and required bearer token authentication for successful operation.

SOURCE: https://upstash.com/docs/qstash/api/schedules/remove.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: DELETE https://qstash.upstash.io/v2/schedules/{scheduleId}
Authentication: Bearer Token

Path Parameters:
  scheduleId (string): The schedule id to remove.

Response:
  200 OK: If the schedule is removed successfully.
```

--------------------------------

TITLE: API Reference: Delete DLQ Messages
DESCRIPTION: Detailed documentation for the DELETE /v2/dlq endpoint, including authentication, request parameters, and response structure for deleting messages from the Dead Letter Queue.

SOURCE: https://upstash.com/docs/qstash/api/dlq/deleteMessages.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: DELETE https://qstash.upstash.io/v2/dlq
Description: Delete multiple messages from the DLQ.
Authentication: Bearer Token

Request:
  Body Parameters:
    dlqIds:
      Type: string[]
      Required: true
      Description: The list of DLQ message IDs to remove.

Response:
  Description: A deleted object with the number of deleted messages.
  Schema:
    {
      "deleted": number
    }
  Example (200 OK):
    {
      "deleted": 3
    }
```

--------------------------------

TITLE: Cancel multiple or all QStash messages in bulk
DESCRIPTION: Shows how to perform bulk operations to cancel messages. This includes deleting a specified list of messages by their IDs or deleting all messages currently managed by the QStash service.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/messages.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });

// deleting two messages at once
await client.messages.deleteMany([
  "message-id-1",
  "message-id-2",
])


// deleting all messages
await client.messages.deleteAll()
```

--------------------------------

TITLE: Retrieve a QStash Message
DESCRIPTION: This snippet demonstrates how to retrieve a specific message from the QStash database using its unique message ID. This operation is intended for messages that are currently in the process of being delivered or retried.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/messages.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
msg = client.message.get("<msg-id>")
```

--------------------------------

TITLE: Schedule ID Field in Qstash Events and Messages APIs
DESCRIPTION: The `Schedule ID` field is now included in the Qstash events and messages APIs for better tracking.

SOURCE: https://upstash.com/docs/qstash/overall/changelog.mdx

LANGUAGE: APIDOC
CODE:
```
Qstash API Fields:
  - Endpoint: /v2/events
    - Field: scheduleId: string
  - Endpoint: /v2/messages/get
    - Field: scheduleId: string
```

--------------------------------

TITLE: Cancel Message API Endpoint
DESCRIPTION: Describes the API endpoint used to cancel a message in Upstash QStash. When a cancellation request is received, the message is marked as 'CANCEL_REQUESTED' and subsequently 'CANCELLED' if retries are not exhausted, leading to its removal from the system.

SOURCE: https://upstash.com/docs/qstash/howto/debug-logs.mdx

LANGUAGE: APIDOC
CODE:
```
DELETE /v2/messages/:messageId
```

--------------------------------

TITLE: Retrieve a single QStash message by ID
DESCRIPTION: Demonstrates how to retrieve a specific message from the Upstash QStash service using its unique identifier. This is useful for inspecting messages currently in transit or retry queues.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/messages.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const messages = client.messages
const msg = await messages.get("msgId");
```

--------------------------------

TITLE: Delete an Upstash QStash Queue
DESCRIPTION: Illustrates how to delete an existing Upstash QStash queue using the `@upstash/qstash` client. This operation permanently removes the specified queue from your Upstash account.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/queues.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName: queueName }).delete();
```

--------------------------------

TITLE: Set Custom Retry Limit for QStash Messages
DESCRIPTION: Demonstrates how to specify a custom maximum number of retries for a message using the 'Upstash-Retries' header in cURL, and the 'retries' parameter in the TypeScript and Python SDKs. This allows overriding the default retry behavior.

SOURCE: https://upstash.com/docs/qstash/features/retry.mdx

LANGUAGE: cURL
CODE:
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Retries: 2" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'
```

LANGUAGE: TypeScript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const res = await client.publishJSON({
  url: "https://my-api...",
  body: { hello: "world" },
  retries: 2,
});
```

LANGUAGE: Python
CODE:
```
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

TITLE: API Reference: Remove URL Group Endpoint
DESCRIPTION: Comprehensive documentation for the DELETE /v2/topics/{urlGroupName} API endpoint, including authentication, parameters, and expected responses. This operation removes a URL group and all its associated endpoints.

SOURCE: https://upstash.com/docs/qstash/api/url-groups/remove.mdx

LANGUAGE: APIDOC
CODE:
```
API Endpoint:
  Method: DELETE
  Path: https://qstash.upstash.io/v2/topics/{urlGroupName}

Authentication:
  Method: bearer

Parameters:
  - Name: urlGroupName
    Type: string
    Required: true
    Description: The name of the URL Group to remove.

Response:
  - Status: 200 OK
    Description: The URL Group is removed successfully. In-flight messages are not removed, but new messages cannot be sent to the topic.
```

--------------------------------

TITLE: Delete a schedule
DESCRIPTION: Shows how to permanently remove a schedule from the QStash system. This operation requires the `scheduleId` of the task to be deleted, ensuring it will no longer execute.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/schedules.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.delete("scheduleId");
```

--------------------------------

TITLE: API Reference for Deleting a DLQ Message
DESCRIPTION: Details the REST API endpoint, authentication, parameters, and response behavior for deleting a message from the Dead Letter Queue.

SOURCE: https://upstash.com/docs/qstash/api/dlq/deleteMessage.mdx

LANGUAGE: APIDOC
CODE:
```
Endpoint: DELETE https://qstash.upstash.io/v2/dlq/{dlqId}
Authentication: Bearer Token

Parameters:
  dlqId (string, path): The dlq id of the message you want to remove. You will see this id when listing all messages in the dlq with the /v2/dlq endpoint.

Responses:
  200 OK: The endpoint doesn't return anything, a status code of 200 means the message is removed from the DLQ.
  404 Not Found: If the message is not found in the DLQ, (either is has been removed by you, or automatically), the endpoint returns a 404 status code.
```

--------------------------------

TITLE: Cancel a Single QStash Message
DESCRIPTION: This snippet shows how to cancel or delete a single message from the QStash system using its message ID. Once canceled, the message will no longer be delivered or retried.

SOURCE: https://upstash.com/docs/qstash/sdks/py/examples/messages.mdx

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH-TOKEN>")
client.message.cancel("<msg-id>")
```

--------------------------------

TITLE: Cancel or delete a single QStash message
DESCRIPTION: Illustrates how to delete an individual message from the Upstash QStash service using its ID. This action prevents the message from being delivered or retried further.

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/messages.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const messages = client.messages
const msg = await messages.delete("msgId");
```

--------------------------------

TITLE: Delete a message from Upstash QStash DLQ in TypeScript
DESCRIPTION: This snippet shows how to delete a specific message from the Dead Letter Queue (DLQ) by providing its unique identifier (dlqId).

SOURCE: https://upstash.com/docs/qstash/sdks/ts/examples/dlq.mdx

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const dlq = client.dlq;
await dlq.delete("dlqId");
```

--------------------------------

TITLE: Delete a QStash Schedule
DESCRIPTION: This snippet demonstrates how to remove an existing schedule from QStash. Deleting a schedule prevents it from creating new messages, but it does not affect messages that have already been scheduled or are in progress. The schedule ID is required for this operation.

SOURCE: https://upstash.com/docs/qstash/howto/delete-schedule.mdx

LANGUAGE: shell
CODE:
```
curl -XDELETE \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules/<schedule_id>'
```

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.delete("<scheduleId>");
```

LANGUAGE: python
CODE:
```
from qstash import QStash

client = QStash("<QSTASH_TOKEN>")
client.schedule.delete("<scheduleId>")
```
```

