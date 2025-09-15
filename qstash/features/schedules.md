On this page
In addition to sending a message once, you can create a schedule, and we will publish the message in the given period. To create a schedule, you simply need to add the `Upstash-Cron` header to your `publish` request. Schedules can be configured using `cron` expressions. crontab.guru is a great tool for understanding and creating cron expressions. By default, we evaluate cron expressions in `UTC`.  
If you want to run your schedule in a specific timezone, see the section on Timezones. The following request would create a schedule that will automatically publish the message every minute:
Typescript
Python
cURL
Copy
Ask AI
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
});

```

All of the other config options can still be used.
It can take up to 60 seconds for the schedule to be loaded on an active node and triggered for the first time.
You can see and manage your schedules in the Upstash Console.
### 
​
Scheduling to a URL Group
Instead of scheduling a message to a specific URL, you can also create a schedule, that publishes to a URL Group. Simply use either the URL Group name or its id:
Typescript
Python
cURL
Copy
Ask AI
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "urlGroupName",
  cron: "* * * * *",
});

```

### 
​
Scheduling to a Queue
You can schedule an item to be added to a queue at a specified time.
typescript
cURL
Copy
Ask AI
```
curl -XPOST \
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "* * * * *",
  queueName: "yourQueueName",
});

```

### 
​
Overwriting an existing schedule
You can pass scheduleId explicitly to overwrite an existing schedule or just simply create the schedule with the given schedule id.
Typescript
cURL
Copy
Ask AI
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  scheduleId: "existingScheduleId",
  cron: "* * * * *",
});

```

### 
​
Timezones
By default, cron expressions are evaluated in `UTC`.  
You can specify a different timezone using the `CRON_TZ` prefix directly inside the cron expression. All IANA timezones are supported. For example, this schedule runs every day at `04:00 AM` in New York time:
Typescript
Python
cURL
Copy
Ask AI
```
import { Client } from "@upstash/qstash";

const client = new Client({ token: "<QSTASH_TOKEN>" });
await client.schedules.create({
  destination: "https://example.com",
  cron: "CRON_TZ=America/New_York 0 4 * * *",
});

```

Was this page helpful?
YesNo
Suggest editsRaise issue
RetryQueues
Assistant
Responses are generated using AI and may contain mistakes.
