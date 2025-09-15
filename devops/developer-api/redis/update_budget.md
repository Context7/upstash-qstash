Update Database Budget
cURL
Copy
Ask AI
```
curl --request PATCH \
  --url https://api.upstash.com/v2/redis/update-budget/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "budget": 123
}'
```

200
Copy
Ask AI
```
"OK"
```

PATCH
/
redis
/
update-budget
/
{id}
Try it
Update Database Budget
cURL
Copy
Ask AI
```
curl --request PATCH \
  --url https://api.upstash.com/v2/redis/update-budget/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "budget": 123
}'
```

200
Copy
Ask AI
```
"OK"
```

#### Authorizations
​
Authorization
string
header
required
Basic authentication header of the form `Basic <encoded-value>`, where `<encoded-value>` is the base64-encoded string `username:password`.
#### Path Parameters
​
id
string
required
The ID of the database whose budget will be updated
#### Body
application/json
​
budget
integer
required
The new monthly budget for the database
#### Response
200 - application/json
Budget updated successfully
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Move To TeamDelete Database
Assistant
Responses are generated using AI and may contain mistakes.
