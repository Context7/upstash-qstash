Example
Copy
Ask AI
```
const monitor = await redis.monitor()

monitor.on("monitor", (time, args, source, database) => {
  console.log(time, args, source, database)
})

```

Example
Copy
Ask AI
```
const monitor = await redis.monitor()

monitor.on("monitor", (time, args, source, database) => {
  console.log(time, args, source, database)
})

```

We support the Redis `MONITOR` command, a debugging command that allows you to see all requests processed by your Redis instance in real-time.
## 
​
Monitoring Your Usage - Video Guide
In this video, we’ll walk through setting up a monitor instance step-by-step.
The `MONITOR`command expects a persistent connection and, therefore, does not work over HTTP.
In this video, we use `ioredis` to connect to our Upstash Redis database. Using an event handler, we can define what should happen for each executed command against on Redis instance. For example, logging all data to the console.
Was this page helpful?
YesNo
Suggest editsRaise issue
Metrics and ChartsImport/Export Data
Assistant
Responses are generated using AI and may contain mistakes.
