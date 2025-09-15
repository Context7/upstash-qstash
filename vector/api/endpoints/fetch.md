curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/fetch \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": ["id-0"], "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": [
        {
            "id": "id-0",
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1"
        }
    ]
}

```

GET
/
fetch
/
{namespace}
Try it
curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/fetch \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": ["id-0"], "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": [
        {
            "id": "id-0",
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1"
        }
    ]
}

```

You can fetch vector values or metadata of one or more by providing their vector ids or id prefix.
Vectors will be fetched from the default namespace by default. You can use a different namespace by specifying it in the request path.
## 
​
Request
​
ids
string[]
Array of vector ids to fetch.
​
prefix
string
Prefix of vector ids to fetch.
When you fetch vectors with an id prefix, at most `1000` vectors will be returned. If there are more vectors, please use the range API with an id prefix.
​
includeMetadata
boolean
default:"false"
Whether to include the metadata of the vectors in the response, if any. It is recommended to set this to `true` to easily identify vectors.
​
includeVectors
boolean
default:"false"
Whether to include the vector values in the response. It is recommended to set this to `false` as the vector values can be quite big, and not needed most of the time.
​
includeData
boolean
default:"false"
Whether to include the data of the vectors in the response, if any.
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
Vectors
Object[]
Array of vectors in the same order they provided in the ids array. Array elements can be `null` if no such vector exists with the provided id.
Hide child attributes
​
id
string
required
The id of the vector.
​
vector
number[]
The dense vector value for dense and hybrid indexes.
​
sparseVector
Object[]
The sparse vector value for sparse and hybrid indexes.
Hide child attributes
​
indices
number[]
Indices of the non-zero valued dimensions.
​
values
number[]
Values of the non-zero valued dimensions.
​
metadata
Object
The metadata of the vector, if any.
​
data
string
The unstructured data of the vector, if any.
Was this page helpful?
YesNo
Suggest editsRaise issue
Stop Resumable QueryFetch Random Vector
Assistant
Responses are generated using AI and may contain mistakes.
