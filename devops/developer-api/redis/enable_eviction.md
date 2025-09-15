Enable Eviction
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/enable-eviction/{id} \
  --header 'Authorization: Basic <encoded-value>'
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
enable-eviction
/
{id}
Try it
Enable Eviction
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/enable-eviction/{id} \
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
The ID of the database to enable eviction
#### Response
200 - application/json
Eviction enabled successfully
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Enable TLSDisable Eviction
Assistant
Responses are generated using AI and may contain mistakes.
