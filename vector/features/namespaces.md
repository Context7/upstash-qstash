On this page
Upstash Vector allows you to partition a single index into multiple isolated namespaces. Each namespace acts as a self-contained subset of the index, and read and write requests are limited to one namespace. Each vector index has at least one default namespace and optionally many more. If no namespace is specified, the operations will use the default namespace, which has the name `""` (empty string).
Indexes created before the namespaces feature can still be used as they are, without modification. All operations are assumed to use the default namespace.
## 
​
Using a Namespace
Namespaces are created implicitly when an upsert operation is performed, so there is no specific endpoint for creating a namespace. For example, the code snippet below will create the namespace `ns` if it does not already exist, upsert and query the vector only on that namespace.
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
    [("id-0", [0.9215, 0.3897])],
    namespace="ns",
)

index.query(
    [0.9215, 0.3897],
    top_k=5,
    namespace="ns",
)

```

Under the hood, when using a namespace, your requests are sent to `<vector-url>/<command>/namespace-name` to only be executed only against that namespace.
## 
​
Deleting a Namespace
Namespaces can be deleted by using the Delete Namespace API.
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

index.delete_namespace("ns")

```

## 
​
Listing Namespaces
All active namespaces can be listed by using the List Namespaces API.
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

index.list_namespaces()

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Embedding ModelsResumable Query
Assistant
Responses are generated using AI and may contain mistakes.
