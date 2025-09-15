Change Database Plan
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/change-plan/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "database_id": "6gcefvfd-9627-2tz5-4l71-c5679g19d2g4",
  "plan_name": "fixed_1gb",
  "auto_upgrade": true,
  "prod_pack_enabled": false
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
change-plan
/
{id}
Try it
Change Database Plan
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/change-plan/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "database_id": "6gcefvfd-9627-2tz5-4l71-c5679g19d2g4",
  "plan_name": "fixed_1gb",
  "auto_upgrade": true,
  "prod_pack_enabled": false
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
The ID of the database whose plan will be changed
#### Body
application/json
#### Response
200 - application/json
Plan changed successfully
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Disable Auto UpgradeUpdate Regions
Assistant
Responses are generated using AI and may contain mistakes.
