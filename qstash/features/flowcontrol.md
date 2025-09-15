On this page
FlowControl enables you to limit the number of messages sent to your endpoint via delaying the delivery. There are two limits that you can set with the FlowControl feature: Rate and Parallelism. And if needed both parameters can be combined. For the `FlowControl`, you need to choose a key first. This key is used to count the number of calls made to your endpoint. There are not limits to number of keys you can use.
The rate/parallelism limits are not applied per `url`, they are applied per `Flow-Control-Key`.
Keep in mind that rate/period and parallelism info are kept on each publish separately. That means if you change the rate/period or parallelism on a new publish, the old fired ones will not be affected. They will keep their flowControl config. During the period that old `publishes` has not delivered but there are also the `publishes` with the new rates, QStash will effectively allow the highest rate/period or highest parallelism. Eventually(after the old publishes are delivered), the new rate/period and parallelism will be used.
## 
​
Rate and Period Parameters
The `rate` parameter specifies the maximum number of calls allowed within a given period. The `period` parameter allows you to specify the time window over which the rate limit is enforced. By default, the period is set to 1 second, but you can adjust it to control how frequently calls are allowed. For example, you can set a rate of 10 calls per minute as follows:
TypeScript
cURL
Copy
Ask AI
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, period: "1m" },
});

```

## 
​
Parallelism Limit
The parallelism limit is the number of calls that can be active at the same time. Active means that the call is made to your endpoint and the response is not received yet. You can set the parallelism limit to 10 calls active at the same time as follows:
TypeScript
cURL
Copy
Ask AI
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", parallelism: 10 },
});

```

You can also use the Rest API to get information how many messages waiting for parallelism limit. See the API documentation for more details.
### 
​
Rate, Parallelism, and Period Together
All three parameters can be combined. For example, with a rate of 10 per minute, parallelism of 20, and a period of 1 minute, QStash will trigger 10 calls in the first minute and another 10 in the next. Since none of them will have finished, the system will wait until one completes before triggering another.
TypeScript
cURL
Copy
Ask AI
```
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
    url: "https://example.com",
    body: { hello: "world" },
    flowControl: { key: "USER_GIVEN_KEY", rate: 10, parallelism: 20, period: "1m" },
});

```

Was this page helpful?
YesNo
Suggest editsRaise issue
QueuesDelay
Assistant
Responses are generated using AI and may contain mistakes.
