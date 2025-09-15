On this page
Messages can be deduplicated to prevent duplicate messages from being sent. When a duplicate message is detected, it is accepted by QStash but not enqueued. This can be useful when the connection between your service and QStash fails, and you never receive the acknowledgement. You can simply retry publishing and can be sure that the message will enqueued only once. In case a message is a duplicate, we will accept the request and return the messageID of the existing message. The only difference will be the response status code. We’ll send HTTP `202 Accepted` code in case of a duplicate message.
## 
​
Deduplication ID
To deduplicate a message, you can send the `Upstash-Deduplication-Id` header when publishing the message.
cURL
TypeScript
Python
Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Deduplication-Id: abcdef" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/https://my-api..."'

```

## 
​
Content Based Deduplication
If you want to deduplicate messages automatically, you can set the `Upstash-Content-Based-Deduplication` header to `true`.
cURL
TypeScript
Python
Copy
Ask AI
```
curl -XPOST \
    -H 'Authorization: Bearer XXX' \
    -H "Content-type: application/json" \
    -H "Upstash-Content-Based-Deduplication: true" \
    -d '{ "hello": "world" }' \
    'https://qstash.upstash.io/v2/publish/...'

```

Content based deduplication creates a unique deduplication ID for the message based on the following fields:
  * **Destination** : The URL Group or endpoint you are publishing the message to.
  * **Body** : The body of the message.
  * **Header** : This includes the `Content-Type` header and all headers, that you forwarded with the `Upstash-Forward-` prefix. See custom HTTP headers section.


The deduplication window is 10 minutes. After that, messages with the same ID or content can be sent again.
Was this page helpful?
YesNo
Suggest editsRaise issue
Dead Letter QueuesSecurity
Assistant
Responses are generated using AI and may contain mistakes.
