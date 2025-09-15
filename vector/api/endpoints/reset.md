curl
curl (Namespace)
curl (All Namespaces)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/reset \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"

```

200 OK
Copy
Ask AI
```
{
    "result": "Success"
}

```

DELETE
/
reset
/
{namespace}
Try it
curl
curl (Namespace)
curl (All Namespaces)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/reset \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"

```

200 OK
Copy
Ask AI
```
{
    "result": "Success"
}

```

The namespace will be completely empty after `/reset` is called, but will not be deleted.
Reset operation will be performed against the default namespace by default. You can use a different namespace by specifying it in the request path.
## 
​
Request
This request doesn’t require any additional data.
## 
​
Query
​
all
string
When given, resets all namespaces of an index.
## 
​
Path
​
namespace
string
default:""
The namespace to use. When no namespace is specified, the default namespace will be used.
## 
​
Response
​
result
string
`"Success"` string.
Was this page helpful?
YesNo
Suggest editsRaise issue
Update VectorIndex Info
Assistant
Responses are generated using AI and may contain mistakes.
