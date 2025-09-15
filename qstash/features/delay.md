On this page
When publishing a message, you can delay it for a certain amount of time before it will be delivered to your API. See the pricing table for more information
For free: The maximum allowed delay is **7 days**.For pay-as-you-go: The maximum allowed delay is **1 year**.For fixed pricing: The maximum allowed delay is **Custom(you may delay as much as needed)**.
## 
​
Relative Delay
Delay a message by a certain amount of time relative to the time the message was published. The format for the duration is `<number><unit>`. Here are some examples:
  * `10s` = 10 seconds
  * `1m` = 1 minute
  * `30m` = half an hour
  * `2h` = 2 hours
  * `7d` = 7 days

You can send this duration inside the `Upstash-Delay` header.
cURL
Typescript
Python
Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 1m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'

```

`Upstash-Delay` will get overridden by `Upstash-Not-Before` header when both are used together.
## 
​
Absolute Delay
Delay a message until a certain time in the future. The format is a unix timestamp in seconds, based on the UTC timezone. You can send the timestamp inside the `Upstash-Not-Before` header.
cURL
Typescript
Python
Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Not-Before: 1657104947" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api...'

```

`Upstash-Not-Before` will override the `Upstash-Delay` header when both are used together.
## 
​
Delays in Schedules
Adding a delay in schedules is only possible via `Upstash-Delay`. The delay will affect the messages that will be created by the schedule and not the schedule itself. For example when you create a new schedule with a delay of `30s`, the messages will be created when the schedule triggers but only delivered after 30 seconds.
Was this page helpful?
YesNo
Suggest editsRaise issue
Flow ControlURL Groups
Assistant
Responses are generated using AI and may contain mistakes.
