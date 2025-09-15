On this page
QStash requires a publicly available API to send messages to. During development when applications are not yet deployed, developers typically need to expose their local API by creating a public tunnel. While local tunneling works seamlessly, it requires code changes between development and production environments and increase friction for developers. To simplify the development process, Upstash provides QStash CLI, which allows you to run a development server locally for testing and development.
The development server fully supports all QStash features including Schedules, URL Groups, Workflows, and Event Logs.
Since the development server operates entirely in-memory, all data is reset when the server restarts.
You can download and run the QStash CLI executable binary in several ways:
## 
​
NPX (Node Package Executable)
Install the binary via the `@upstash/qstash-cli` NPM package:
Copy
Ask AI
```
npx @upstash/qstash-cli dev

// Start on a different port
npx @upstash/qstash-cli dev -port=8081

```

Once you start the local server, you can go to the QStash tab on Upstash Console and enable local mode, which will allow you to publish requests and monitor messages with the local server.
## 
​
Docker
QStash CLI is available as a Docker image through our public AWS ECR repository:
Copy
Ask AI
```
// Pull the image
docker pull public.ecr.aws/upstash/qstash:latest

// Run the image
docker run -p 8080:8080 public.ecr.aws/upstash/qstash:latest qstash dev

```

## 
​
Artifact Repository
You can download the binary directly from our artifact repository without using a package manager: https://artifacts.upstash.com/#qstash/versions/ Select the appropriate version, architecture, and operating system for your platform. After extracting the archive file, run the executable:
Copy
Ask AI
```
$ ./qstash dev

```

## 
​
QStash CLI
Currently, the only available command for QStash CLI is `dev`, which starts a development server instance.
Copy
Ask AI
```
$ ./qstash dev --help
Usage of dev:
  -port int
        The port to start HTTP server at [env QSTASH_DEV_PORT] (default 8080)
  -quota string
        The quota of users [env QSTASH_DEV_QUOTA] (default "payg")

```

There are predefined test users available. You can configure the quota type of users using the `-quota` option, with available options being `payg` and `pro`. These quotas don’t affect performance but allow you to simulate different server limits based on the subscription tier. After starting the development server using any of the methods above, it will display the necessary environment variables. Select and copy the credentials from one of the following test users:
User 1
User 2
User 3
User 4
Copy
Ask AI
```
QSTASH_URL=http://localhost:8080
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7kYjw48mhY7kAjqNGcy6cr29RJ6r
QSTASH_NEXT_SIGNING_KEY=sig_5ZB6DVzB1wjE8S6rZ7eenA8Pdnhs

```

Currently, there is no GUI client available for the development server. You can use QStash SDKs to fetch resources like event logs.
## 
​
License
The QStash development server is licensed under the Development Server License, which restricts its use to development and testing purposes only. It is not permitted to use it in production environments. Please refer to the full license text for details.
Was this page helpful?
YesNo
Suggest editsRaise issue
Use as Webhook ReceiverLocal Tunnel
Assistant
Responses are generated using AI and may contain mistakes.
