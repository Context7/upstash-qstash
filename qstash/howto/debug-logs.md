On this page
To debug the logs, first you need to understand the different states a message can be in. Only the last 10.000 logs are kept and older logs are removed automatically.
## 
​
Lifecycle of a Message
To understand the lifecycle of each message, we’ll look at the following chart:
Either you or a previously setup schedule will create a message. When a message is ready for execution, it will be become `ACTIVE` and a delivery to your API is attempted. If you API responds with a status code between `200 - 299`, the task is considered successful and will be marked as `DELIVERED`. Otherwise the message is being retried if there are any retries left and moves to `RETRY`. If all retries are exhausted, the task has `FAILED` and the message will be moved to the DLQ. During all this a message can be cancelled via DELETE /v2/messages/:messageId. When the request is received, `CANCEL_REQUESTED` will be logged first. If retries are not exhausted yet, in the next deliver time, the message will be marked as `CANCELLED` and will be completely removed from the system.
## 
​
Console
Head over to the Upstash Console and go to the `Logs` tab, where you can see the latest status of your messages.
Was this page helpful?
YesNo
Suggest editsRaise issue
Roll Your Signing KeysPeriodic Data Updates
Assistant
Responses are generated using AI and may contain mistakes.
