> ## Documentation Index
> Fetch the complete documentation index at: https://upstash.com/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Getting Started

## Install

### NPM

```bash  theme={"system"}
npm install @upstash/qstash
```

## Get QStash token

Follow the instructions [here](/qstash/overall/getstarted) to get your QStash token and signing keys.

## Usage

```typescript  theme={"system"}
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
});
```

#### RetryConfig

You can configure the retry policy of the client by passing the configuration to the client constructor.

Note: This is for sending the request to QStash, not for the retry policy of QStash.

The default number of attempts is **6** and the default backoff function is `(retry_count) => (Math.exp(retry_count) * 50)`.

You can also pass in `false` to disable retrying.

```typescript  theme={"system"}
import { Client } from "@upstash/qstash";

const client = new Client({
  token: "<QSTASH_TOKEN>",
  retry: {
    retries: 3,
    backoff: retry_count => 2 ** retry_count * 20,
  },
});
```

## Telemetry

This sdk sends anonymous telemetry headers to help us improve your experience.
We collect the following:

* SDK version
* Platform (Cloudflare, AWS or Vercel)
* Runtime version ([node@18.x](mailto:node@18.x))

You can opt out by setting the `UPSTASH_DISABLE_TELEMETRY` environment variable
to any truthy value. Or setting `enableTelemetry: false` in the client options.

```ts  theme={"system"}
const client = new Client({
  token: "<QSTASH_TOKEN>",
  enableTelemetry: false,
});
```
