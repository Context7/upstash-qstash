curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/resume \
  -H "Authorization: Bearer <token>"

```

POST
/
v2
/
schedules
/
{scheduleId}
/
resume
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/resume \
  -H "Authorization: Bearer <token>"

```

Resuming a schedule marks the schedule as active. This means the upcoming messages will be delivered and will not be ignored. If the schedule is already active, this action has no effect.
## 
​
Request
​
scheduleId
string
required
The id of the schedule to resume.
## 
​
Response
This endpoint simply returns 200 OK if the schedule is resumed successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Pause ScheduleGet Signing Keys
Assistant
Responses are generated using AI and may contain mistakes.
