Delete Database
cURL
Copy
Ask AI
```
curl --request DELETE \
  --url https://api.upstash.com/v2/redis/database/{id} \
  --header 'Authorization: Basic <encoded-value>'
```

200
Copy
Ask AI
```
"OK"
```

DELETE
/
redis
/
database
/
{id}
Try it
Delete Database
cURL
Copy
Ask AI
```
curl --request DELETE \
  --url https://api.upstash.com/v2/redis/database/{id} \
  --header 'Authorization: Basic <encoded-value>'
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
The ID of the database to be deleted
#### Response
200 - application/json
OK
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Update Database BudgetList Backup
Assistant
Responses are generated using AI and may contain mistakes.
