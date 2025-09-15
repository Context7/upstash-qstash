curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/pause \
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
pause
Try it
curl
Node
Python
Go
Copy
Ask AI
```
curl -X POST https://qstash.upstash.io/v2/schedules/scd_1234/pause \
  -H "Authorization: Bearer <token>"

```

Pausing a schedule will not change the next delivery time, but the delivery will be ignored. If the schedule is already paused, this action has no effect.
## 
​
Request
​
scheduleId
string
required
The id of the schedule to pause.
## 
​
Response
This endpoint simply returns 200 OK if the schedule is paused successfully.
Was this page helpful?
YesNo
Suggest editsRaise issue
Remove ScheduleResume Schedule
Assistant
Responses are generated using AI and may contain mistakes.
