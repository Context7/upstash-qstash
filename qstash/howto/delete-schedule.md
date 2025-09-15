On this page
Deleting schedules can be done using the schedules api.
cURL
Typescript
Python
Copy
Ask AI
```
curl -XDELETE \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules/<schedule_id>'

```

Deleting a schedule does not stop existing messages from being delivered. It only stops the schedule from creating new messages.
## 
​
Schedule ID
If you don’t know the schedule ID, you can get a list of all of your schedules from here.
cURL
Typescript
Python
Copy
Ask AI
```
curl \
    -H 'Authorization: Bearer XXX' \
    'https://qstash.upstash.io/v2/schedules'

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Verify SignaturesReset Token
Assistant
Responses are generated using AI and may contain mistakes.
