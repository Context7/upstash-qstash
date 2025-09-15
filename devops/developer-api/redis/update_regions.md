Update Regions
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/update-regions/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "read_regions": [
    "us-west-1",
    "us-west-2"
  ]
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
update-regions
/
{id}
Try it
Update Regions
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/update-regions/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "read_regions": [
    "us-west-1",
    "us-west-2"
  ]
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
The ID of your database
#### Body
application/json
​
read_regions
enum<string>[]
required
Array of Read Regions of the Database
Show child attributes
​
enum<string>
Available options: 
`us-east-1`, 
`us-east-2`, 
`us-west-1`, 
`us-west-2`, 
`ca-central-1`, 
`eu-central-1`, 
`eu-west-1`, 
`eu-west-2`, 
`sa-east-1`, 
`ap-south-1`, 
`ap-northeast-1`, 
`ap-southeast-1`, 
`ap-southeast-2`
Example:
```
["us-west-1", "us-west-2"]
```

#### Response
200 - application/json
Regions updated successfully
The response is of type `string`.
Example:
`"OK"`
Was this page helpful?
YesNo
Suggest editsRaise issue
Change Database PlanMove To Team
Assistant
Responses are generated using AI and may contain mistakes.
