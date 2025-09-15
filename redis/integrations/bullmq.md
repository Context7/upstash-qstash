On this page
You can use BullMQ and Bull with Upstash Redis. BullMQ is a Node.js queue library that is built on top of Bull. It is a Redis-based queue library so you can use Upstash Redis as its storage.
## 
​
Install
Copy
Ask AI
```
npm install bullmq upstash-redis

```

## 
​
Usage
Copy
Ask AI
```
import { Queue } from 'bullmq';

const myQueue = new Queue('foo', { connection: {
        host: "UPSTASH_REDIS_ENDPOINT",
        port: 6379,
        password: "UPSTASH_REDIS_PASSWORD",
        tls: {}
    }});

async function addJobs() {
    await myQueue.add('myJobName', { foo: 'bar' });
    await myQueue.add('myJobName', { qux: 'baz' });
}

await addJobs();

```

## 
​
Billing Optimization
BullMQ accesses Redis regularly, even when there is no queue activity. This can incur extra costs because Upstash charges per request on the Pay-As-You-Go plan. With the introduction of our Fixed plans, **we recommend switching to a Fixed plan to avoid increased command count and high costs in BullMQ use cases.**
Was this page helpful?
YesNo
Suggest editsRaise issue
PrometheusSidekiq
Assistant
Responses are generated using AI and may contain mistakes.
