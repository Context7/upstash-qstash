On this page
### 
​
Use QStash via:
  * cURL
  * Typescript SDK
  * Python SDK

Below are some examples to get you started. You can also check the how to section for more technical details or the API reference to test the API.
### 
​
Publish a message to an endpoint
Simple example to publish a message to an endpoint.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

### 
​
Publish a message to a URL Group
The URL Group is a way to publish a message to multiple endpoints in a fan out pattern.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/myUrlGroup'

```

### 
​
Publish a message with 5 minutes delay
Add a delay to the message to be published. After QStash receives the message, it will wait for the specified time (5 minutes in this example) before sending the message to the endpoint.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Delay: 5m" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

### 
​
Send a custom header
Add a custom header to the message to be published.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H 'Upstash-Forward-My-Header: my-value' \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

### 
​
Schedule to run once a day
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Cron: 0 0 * * *" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/schedules/https://example.com'

```

### 
​
Publish messages to a FIFO queue
By default, messges are published concurrently. With a queue, you can enqueue messages in FIFO order.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST -H 'Authorization: Bearer XXX' \
            -H "Content-type: application/json" \
            'https://qstash.upstash.io/v2/enqueue/my-queue/https://example.com' 
            -d '{"message":"Hello, World!"}'

```

### 
​
Publish messages in a batch
Publish multiple messages in a single request.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
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

### 
​
Set max retry count to 3
Configure how many times QStash should retry to send the message to the endpoint before sending it to the dead letter queue.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

### 
​
Set custom retry delay
Configure the delay between retry attempts when message delivery fails. By default, QStash uses exponential backoff. You can customize this using mathematical expressions with the special variable `retried` (current retry attempt count starting from 0).
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Upstash-Retries: 3" \
    -H "Upstash-Retry-Delay: pow(2, retried) * 1000" \
    -H "Content-type: application/json" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

**Supported functions for retry delay expressions:**
  * `pow` - Power function
  * `sqrt` - Square root
  * `abs` - Absolute value
  * `exp` - Exponential
  * `floor` - Floor function
  * `ceil` - Ceiling function
  * `round` - Rounding function
  * `min` - Minimum of values
  * `max` - Maximum of values

**Examples:**
  * `1000` - Fixed 1 second delay
  * `1000 * (1 + retried)` - Linear backoff: 1s, 2s, 3s, 4s…
  * `pow(2, retried) * 1000` - Exponential backoff: 1s, 2s, 4s, 8s…
  * `max(1000, pow(2, retried) * 100)` - Exponential with minimum 1s delay


### 
​
Set callback url
Receive a response from the endpoint and send it to the specified callback URL. If the endpoint does not return a response, QStash will send it to the failure callback URL.
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Callback: https://example.com/callback" \
    -H "Upstash-Failure-Callback: https://example.com/failure" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://example.com'

```

### 
​
Get message logs
Retrieve logs for all messages that have been published (filtering is also available).
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl https://qstash.upstash.io/v2/logs \
    -H "Authorization: Bearer XXX"

```

### 
​
List all schedules
  * cURL
  * Typescript SDK
  * Python SDK


Copy
Ask AI
```
curl https://qstash.upstash.io/v2/schedules \
    -H "Authorization: Bearer XXX"

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Pricing & LimitsCompare
Assistant
Responses are generated using AI and may contain mistakes.
