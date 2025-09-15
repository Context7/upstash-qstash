curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/delete \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": [ "id-0", "id-1" ] }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "deleted": 2
    }
}

```

DELETE
/
delete
/
{namespace}
Try it
curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/delete \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": [ "id-0", "id-1" ] }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "deleted": 2
    }
}

```

You can delete one or more vectors by providing their vector ids, vector id prefix, or metadata filter.
Vectors will be deleted from the default namespace by default. You can use a different namespace by specifying it in the request path.
## 
​
Request
​
ids
string[]
Array of vector ids to delete.
​
prefix
string
Prefix of vector ids to delete.
​
filter
string
Metadata filter for the vectors to delete. 
Deleting vectors with metadata filter is a O(N) operation that performs a full scan. Therefore, it might be slow for large indexes.
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
deleted
number
The number of the successfully deleted vectors.
Was this page helpful?
YesNo
Suggest editsRaise issue
Range VectorsUpdate Vector
Assistant
Responses are generated using AI and may contain mistakes.
