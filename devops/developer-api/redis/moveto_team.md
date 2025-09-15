Move To Team
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/move-to-team \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "team_id": "<string>",
  "database_id": "<string>"
}'
```

200
Copy
Ask AI
```
"OK"
```

POST
/
redis
/
move-to-team
Try it
Move To Team
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/move-to-team \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "team_id": "<string>",
  "database_id": "<string>"
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
#### Body
application/json
​
team_id
string
required
The ID of the target team
​
database_id
string
required
The ID of the database to be moved
#### Response
200 - application/json
Database moved successfully
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Update RegionsUpdate Database Budget
Assistant
Responses are generated using AI and may contain mistakes.
