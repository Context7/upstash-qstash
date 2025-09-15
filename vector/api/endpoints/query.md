curl
curl (Namespace)
curl (Batch Query)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "vector": [0.1, 0.2], "topK": 2, "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": [
        {
            "id": "id-0",
            "score": 1.0,
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1",
            "score": 0.99996454
        }
    ]
}

```

POST
/
query
/
{namespace}
Try it
curl
curl (Namespace)
curl (Batch Query)
Copy
Ask AI
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "vector": [0.1, 0.2], "topK": 2, "includeMetadata": true }'

```

200 OK
Copy
Ask AI
```
{
    "result": [
        {
            "id": "id-0",
            "score": 1.0,
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1",
            "score": 0.99996454
        }
    ]
}

```

Query will run against the default namespace by default. You can use a different namespace by specifying it in the request path.
## 
​
Request
It is also possible to send a batch query request by providing an array of fields below.
​
vector
number[]
required
The query vector 
The query vector should have the same dimensions as your index.
​
topK
number
default:"10"
The total number of the vectors that you want to receive as a query result. The response will be sorted based on the distance metric score, and at most `topK` many vectors will be returned.
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
​
filter
string
default:""
Metadata filter to apply.
​
weightingStrategy
string
For sparse vectors of sparse and hybrid indexes, specifies what kind of weighting strategy should be used while querying the matching non-zero dimension values of the query vector with the documents.If not provided, no weighting will be used.Only possible value is `IDF` (inverse document frequency).
​
fusionAlgorithm
string
Fusion algorithm to use while fusing scores from dense and sparse components of a hybrid index.If not provided, defaults to `RRF` (Reciprocal Rank Fusion).Other possible value is `DBSF` (Distribution-Based Score Fusion).
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
If the request was an array of a single element, or a JSON object, an object with the following fields is returned. If the request was an array of more than one items, an array of objects below is returned, one for each query item.
For dense indexes, the score is normalized to always be between 0 and 1. The closer the score is to 1, the more similar the vector is to the query vector. This does not depend on the distance metric you use.For sparse and hybrid indexes, scores can be arbitrary values, but the score will be higher for more similar vectors.
​
Scores
Object[]
Hide child attributes
​
id
string
required
The id of the vector.
​
score
number
required
The similarity score of the vector, calculated based on the distance metric of your index.
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
Upsert DataQuery Data
Assistant
Responses are generated using AI and may contain mistakes.
