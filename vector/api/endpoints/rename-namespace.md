curl
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/rename-namespace \
  -X POST \
  -d '{ "namespace": "ns", "newNamespace": "newNs" }' \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"

```

200 OK
Copy
Ask AI
```
{
    "result": { "renamed": true }
}

```

POST
/
rename-namespace
Try it
curl
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/rename-namespace \
  -X POST \
  -d '{ "namespace": "ns", "newNamespace": "newNs" }' \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"

```

200 OK
Copy
Ask AI
```
{
    "result": { "renamed": true }
}

```

The default namespace, which is the empty string `""`, cannot be renamed.
There should not be a namespace with the given new namespace name.
## 
​
Request
​
namespace
string
required
The name of the namespace to rename.
​
newNamespace
string
required
The new name of the namespace.
## 
​
Response
​
renamed
boolean
Whether the namespace is renamed or not.
Was this page helpful?
YesNo
Suggest editsRaise issue
Delete NamespaceGetting Started
Assistant
Responses are generated using AI and may contain mistakes.
