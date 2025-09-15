On this page
Sometimes, endpoints fail due to various reasons such as network issues or server issues. In such cases, QStash offers a few options to handle these failures.
## 
​
Failure Callbacks
When publishing a message, you can provide a failure callback that will be called if the message fails to be published. You can read more about callbacks here. With the failure callback, you can add custom logic such as logging the failure or sending an alert to the team. Once you handle the failure, you can delete it from the dead letter queue.
cURL
Typescript
Python
Copy
Ask AI
```
curl -X POST \
  https://qstash.upstash.io/v2/publish/<DESTINATION_URL> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <QSTASH_TOKEN>' \
  -H 'Upstash-Failure-Callback: <CALLBACK_URL>' \
  -d '{ "hello": "world" }'

```

## 
​
Dead Letter Queue
If you don’t want to handle the failure immediately, you can use the dead letter queue (DLQ) to store the failed messages. You can read more about the dead letter queue here. Failed messages are automatically moved to the dead letter queue upon failure, and can be retried from the console or the API by retrieving the message then publishing it.
Was this page helpful?
YesNo
Suggest editsRaise issue
Create URL Groups and EndpointsReceiving Messages
Assistant
Responses are generated using AI and may contain mistakes.
