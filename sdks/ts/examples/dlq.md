> ## Documentation Index
> Fetch the complete documentation index at: https://upstash.com/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# DLQ

#### Get all messages with pagination using cursor

Since the DLQ can have a large number of messages, they are paginated.
You can go through the results using the `cursor`.

```typescript  theme={"system"}
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

#### Delete a message from the DLQ

```typescript  theme={"system"}
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
const dlq = client.dlq;
await dlq.delete("dlqId");
```
