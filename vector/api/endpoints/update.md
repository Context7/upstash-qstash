curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/update \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-1", "metadata": { "link": "upstash.com" } }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "updated": 1
    }
}

```

POST
/
update
/
{namespace}
Try it
curl
curl (Namespace)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/update \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-1", "metadata": { "link": "upstash.com" } }'

```

200 OK
Copy
Ask AI
```
{
    "result": {
        "updated": 1
    }
}

```

The vector will be updated int the default namespace by default. You can use a different namespace by specifying it in the request path.
## 
​
Request
You can update a vector value, data, or metadata; or any combination of those.
​
id
string
required
The id of the vector.
​
vector
number[]
The dense vector value to update to for dense and hybrid indexes. 
The vector should have the same dimensions as your index.
​
sparseVector
Object[]
The sparse vector value to update to for sparse and hybrid indexes.
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
data
string
The raw text data to update to. 
If the index is created with an embedding model this will embed the data into a vector and will also update the vector, along with data.
​
metadata
Object
The metadata to update to.
​
metadataUpdateMode
string
Whether to overwrite the whole metadata while updating it, or patch the metadata (insert new fields or update or delete existing fields) according to the `RFC 7396 JSON Merge Patch` algorithm.`OVERWRITE` for overwrite, `PATCH` for patch.
For hybrid indexes either none or both of `vector` and `sparseVector` fields must be present. It is not allowed to update only `vector` or `sparseVector`.
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
updated
number
`1` if any vector is updated, `0` otherwise.
Was this page helpful?
YesNo
Suggest editsRaise issue
Delete VectorsReset Namespace(s)
Assistant
Responses are generated using AI and may contain mistakes.
