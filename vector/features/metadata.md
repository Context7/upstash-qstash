On this page
## 
​
Metadata
Metadata feature allows you to store context with your vectors to make a connection. There can be a couple of uses of this:
  1. You can put the source of the vector in the metadata to use in your application from the query response.
  2. You can put some metadata to further filter the results upon the query.

You can set metadata with your vector as follows:
  * Python
  * JavaScript
  * Go
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [("id-0", [0.9215, 0.3897]), {"url": "https://imgur.com/z9AVZLb"}],
)

```

When you do a query or fetch, you can opt-in to retrieve the metadata as follows:
  * **Query Example**


  * Python
  * JavaScript
  * Go
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    [0.9215, 0.3897],
    top_k=5,
    include_metadata=True,
)

```

Copy
Ask AI
```
{
  "result": [
    {
      "id": "id-0",
      "score": 1,
      "metadata": {
        "url": "https://imgur.com/z9AVZLb"
      }
    },
    {
      "id": "id-3",
      "score": 0.99961007,
      "metadata": {
        "url": "https://imgur.com/zfOPmnI"
      }
    }
  ]
}

```

Also, you can filter the results further by providing a metadata filter:
  * Python
  * JavaScript
  * Go
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    [0.9215, 0.3897],
    top_k=5,
    include_metadata=True,
    filter="url GLOB '*imgur.com*'",
)

```

See Metadata Filtering documentation for more details.
  * **Range Example**


  * Python
  * JavaScript
  * Go
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.range(
    cursor="0",
    limit=3,
    include_metadata=True,
)

```

Copy
Ask AI
```
{
  "result": {
    "nextCursor": "4",
    "vectors": [
      { "id": "id-0", "metadata": { "url": "https://imgur.com/z9AVZLb" } },
      { "id": "id-1", "metadata": { "url": "https://imgur.com/a2nCEIt" } },
      { "id": "id-2", "metadata": { "url": "https://imgur.com/zfOPmnI" } }
    ]
  }
}

```

## 
​
Data
Data is another kind of information you can store per vector to attribute some context to it. Compared to metadata, it is not structured, and it can only be fetched in queries, not used to further filter them. It is especially useful when you upsert raw text data, so that you would have access to the textual form of vector along with the embedded vector values. It can save you from storing contextual information per vector in a separate database. You can set both the metadata and data, or only one of them while upserting your vectors as follows:
  * Python
  * JavaScript
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [
        {
            "id": "id-0",
            "vector": [0.9215, 0.3897],
            "metadata": {"url": "https://imgur.com/z9AVZLb"},
            "data": "data-0",
        },
        {
            "id": "id-1",
            "vector": [0.3897, 0.9215],
            "data": "data-1",
        },
    ],
)

```

When a raw text data is upserted, the data will be set to the raw text data automatically:
  * Python
  * JavaScript
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [
        {
            "id": "id-2",
            "data": "Upstash is a serverless data platform.",
        },
    ],
)

```

  * Python
  * JavaScript
  * PHP
  * curl


Copy
Ask AI
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

result = index.query(
    data="What is Upstash?",
    include_data=True,
)

for res in result:
    print(f"{res.id}: {res.data}")

```

Similar to metadata, the data field can be requested in queries, range iterator, and fetch requests, by setting the `includeData` to `true` as shown above.
Was this page helpful?
YesNo
Suggest editsRaise issue
Sparse IndexesMetadata Filtering
Assistant
Responses are generated using AI and may contain mistakes.
