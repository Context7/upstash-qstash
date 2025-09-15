curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Method: POST" \
  -H "Upstash-Retries: 3" \
  -H "Upstash-Forward-Custom-Header: custom-value" \
  -d '{"message":"Hello, World!"}'

```

URL
URL Group
Copy
Ask AI
```
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}

```

POST
/
v2
/
enqueue
/
{queueName}
/
{destination}
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST "https://qstash.upstash.io/v2/enqueue/myQueue/https://www.example.com" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -H "Upstash-Method: POST" \
  -H "Upstash-Retries: 3" \
  -H "Upstash-Forward-Custom-Header: custom-value" \
  -d '{"message":"Hello, World!"}'

```

URL
URL Group
Copy
Ask AI
```
{
  "messageId": "msd_1234",
  "url": "https://www.example.com"
}

```

## 
​
Request
​
queueName
string
required
The name of the queue that message will be enqueued on. If doesn’t exist, it will be created automatically.
​
destination
string
required
Destination can either be a topic name or id that you configured in the Upstash console, a valid url where the message gets sent to, or a valid QStash API name like `api/llm`. If the destination is a URL, make sure the URL is prefixed with a valid protocol (`http://` or `https://`)
​
body
string
The raw request message passed to the endpoints as is
​
Content-Type
string
ContentType is the MIME type of the message.We highly recommend sending a `Content-Type` header along, as this will help your destination API to understand the content of the message.Set this to whatever data you are sending through QStash, if your message is json, then use `application/json`. Some frameworks like Next.js will not parse your body correctly if the content type is not correct.For example `application/json`, `application/xml`, `application/octet-stream`, `text/plain`
​
Upstash-Method
string
default:"POST"
The HTTP method to use when sending a webhook to your API.
​
Upstash-Timeout
string
Timeout value to set how long your endpoint is going to take. This parameter can be used to shorten the default allowed timeout value on your plan. Examples: 1 second = "1s", 5 minutes = "5m", 2 hours = "2h" See `Max HTTP Connection Timeout` on the pricing page for default values.
​
Upstash-Retries
int
default:3
How often should this message be retried in case the destination API is not available.The total number of deliveries is therefore capped at `1 + retries`Leave this empty to use the default value, (free tier: 3, paid tier: 5)The default backoff duration in seconds is calculated as follows: `n` is the number of times the task has been retried.`min(86400, e ** (2 * n))`You can use the `Upstash-Retry-Delay` header to customize the delay between retry attempts.
​
Upstash-Retry-Delay
string
Customize the delay between retry attempts when message delivery fails.By default, QStash uses exponential backoff. You can override this with mathematical expressions using the special variable `retried` (current retry attempt count starting from 0).**Supported functions:** `pow`, `sqrt`, `abs`, `exp`, `floor`, `ceil`, `round`, `min`, `max`**Examples:**
  * `1000` - Fixed 1 second delay
  * `1000 * (1 + retried)` - Linear backoff
  * `pow(2, retried) * 1000` - Exponential backoff
  * `max(1000, pow(2, retried) * 100)` - Exponential with minimum 1s delay


​
Upstash-Forward-*
string
You can send custom headers along with your message.To send a custom header, prefix the header name with `Upstash-Forward-`. We will strip efix and them to the destination API.example: "Upstash-Forward-My-Header: my-value" -> "My-Header: my-value"
​
Upstash-Callback
string
You can define a callback url that will be called after each attempt. See the content of what will be delivered to a callback here
  * The callback url must be prefixed with a valid protocol (`http://` or `https://`)
  * Callbacks are charged as a regular message.
  * Callbacks will use the retry setting from the original request.

For the `api/llm` destination, specifying a callback is required.
​
Upstash-Callback-*
string
Using the `Upstash-Callback-` prefix; you can set the timeout duration, number of retries, delay to apply or more for the callback request.See the Configuring Callbacks section to learn more.
​
Upstash-Callback-Forward-*
string
If you are using the `Upstash-Callback` header to define a callback url, you can specify the headers sent along with the callback request using the `Upstash-Callback-Forward-*` header.To include a header in the callback request, prefix the header name with `Upstash-Callback-Forward-`. We will strip this prefix and forward the header to the callback destination..example: "Upstash-Callback-Forward-My-Header: my-value" -> "My-Header: my-value"
​
Upstash-Failure-Callback
string
You can define a failure callback url that will be called when a delivery is failed. That is when all the defined retries are exhausted. See the content of what will be delivered to a failure callback here
  * The failure callback url must be prefixed with a valid protocol (`http://` or `https://`)
  * Callbacks are charged as a regular message.
  * Callbacks will use the retry setting from the original request.


​
Upstash-Failure-Callback-*
string
Using the `Upstash-Failure-Callback-` prefix; you can set the timeout duration, number of retries, delay to apply or more for the failure callback request.See the Configuring Callbacks section to learn more.
​
Upstash-Failure-Callback-Forward-*
string
If are you using the `Upstash-Failure-Callback` header to define a callback url when the delivery fails, you can specify the headers sent along with the failure callback request using the `Upstash-Failure-Callback-Forward-*` header.To include a header in the callback request, add `Upstash-Failure-Callback-Forward-` prefix to the header name. We will strip this prefix and forward the header to the callback destination.example: "Upstash-Failure-Callback-Forward-My-Header: my-value" -> "My-Header: my-value"
​
Upstash-Deduplication-Id
string
Id to use while deduplicating messages, so that only one message with the given deduplication id is published.
​
Upstash-Content-Based-Deduplication
boolean
When set to true, automatically deduplicates messages based on their content, so that only one message with the same content is published.Content based deduplication creates unique deduplication ids based on the following message fields:
  * Destination
  * Body
  * Headers


## 
​
Response
Either a single object or an array of objects is returned, depending on whether you have sent the message to a url, URL group, or an API.
### 
​
Single Object Response
This is returned when the destination is a url or an api.
​
messageId
string
required
The unique id of this message.
​
deduplicated
boolean
Whether this message is a duplicate and was not sent to the destination.
### 
​
Array of Objects Response
This is returned when the destination is a topic, and array contains one element for each url in the topic.
​
array
object[]
Hide child attributes
​
messageId
string
required
The unique id of this message.
​
url
string
required
The url where the message was sent to.
​
deduplicated
boolean
Whether this message is a duplicate and was not sent to the destination.
Was this page helpful?
YesNo
Suggest editsRaise issue
Publish a MessageBatch Messages
Assistant
Responses are generated using AI and may contain mistakes.
