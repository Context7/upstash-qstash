On this page
### 
​
Symptom
The client gets an exception similar to:
Copy
Ask AI
```
ReplyError: ERR XReadGroup is cancelled. Pending Entries List limit per consumer is about to be reached. Limit: 1000, Current PEL size: 90, Requested Read: 20, Key: mstream, Group: group1, Consumer: consumer1.

```

### 
​
Diagnosis
Pending Entries List of the stream for the consumer is full. For each consumer in a consumer group, there is a pending entries list. This list keeps the messages that are delivered to a consumer but not yet acknowledged via XACK. This list is populated via XREADGROUP.
### 
​
Solution
Acknowledge the consumed messages via XACK from the list of the associated group and consumer.
Was this page helpful?
YesNo
Suggest editsRaise issue
ERR max requests limit exceededFrequently Asked Questions
Assistant
Responses are generated using AI and may contain mistakes.
