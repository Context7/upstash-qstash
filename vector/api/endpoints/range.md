curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/range \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "cursor": "0", "limit": 2, "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "nextCursor": "2",
        "vectors": [
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
}

```

GET
/
range
/
{namespace}
Try it
curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/range \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "cursor": "0", "limit": 2, "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "nextCursor": "2",
        "vectors": [
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
}

```

By default vectors from the default namespace will be iterated. You can use a different namespace by specifying it in the request path.
## 
​
Request
​
cursor
string
required
The offset to the last retrieved vector. Should be set to `"0"` in the initial range.
​
prefix
string
Prefix of the vector ids to range over.
​
limit
number
required
The number of maximum vectors that you want in the response of range. (page size)
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
nextCursor
string
required
The offset for the next range. You should place this in the `cursor` field for the next range. It will be equal to empty string if there are no other vectors to range.
​
vectors
Object[]
required
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
Fetch Random VectorDelete Vectors
Assistant
Responses are generated using AI and may contain mistakes.
