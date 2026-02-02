> ## Documentation Index
> Fetch the complete documentation index at: https://upstash.com/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Queues

#### Create a queue with parallelism 2

```typescript  theme={"system"}
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName }).upsert({ parallelism: 2 });

const queueDetails = await client.queue({ queueName }).get();
```

#### Delete Queue

```typescript  theme={"system"}
import { Client } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

const queueName = "upstash-queue";
await client.queue({ queueName: queueName }).delete();
```

<Warning>
  Resuming or creating a queue may take up to a minute.
  Therefore, it is not recommended to pause or delete a queue during critical operations.
</Warning>

#### Pause/Resume a queue

```typescript  theme={"system"}
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

<Warning>
  Resuming or creating a queue may take up to a minute.
  Therefore, it is not recommended to pause or delete a queue during critical operations.
</Warning>
