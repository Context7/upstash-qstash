On this page
To store text in a vector database, it must first be converted into a vector, also known as an embedding. Typically, this vectorization is done by a third party. By selecting an embedding model when you create your Upstash Vector database, you can now upsert and query raw string data when using your database instead of converting your text to a vector first. The vectorization is done automatically by your selected model.
## 
​
Upstash Embedding Models - Video Guide
Let’s look at how Upstash embeddings work, how the models we offer compare, and which model is best for your use case.
## 
​
Models
Upstash Vector comes with a variety of embedding models that score well in the MTEB leaderboard, a benchmark for measuring the performance of embedding models. They support use cases such as classification, clustering, or retrieval. You can choose the following general purpose models for dense and hybrid indexes: Name| Dimension| Sequence Length| MTEB  
---|---|---|---  
mixedbread-ai/mxbai-embed-large-v1| 1024| 512| 64.68  
WhereIsAI/UAE-Large-V1| 1024| 512| 64.64  
BAAI/bge-large-en-v1.5| 1024| 512| 64.23  
BAAI/bge-base-en-v1.5| 768| 512| 63.55  
BAAI/bge-small-en-v1.5| 384| 512| 62.17  
sentence-transformers/all-MiniLM-L6-v2| 384| 256| 56.26  
BAAI/bge-m3| 1024| 8192| *  
google-bert/bert-base-uncased| 768| 512| 38.33  
The sequence length is not a hard limit. Models truncate the input appropriately when given a raw text data that would result in more tokens than the given sequence length. However, we recommend using appropriate models and not exceeding their sequence length to have more accurate results.
MTEB score for the `BAAI/bge-m3` is not fully measured.
For sparse and hybrid indexes, on the following models can be selected: Name  
---  
BAAI/bge-m3  
BM25  
See Creating Sparse Vectors for the details of the above models.
## 
​
Using a Model
To start using embedding models, create the index with a model of your choice.
Then, you can start upserting and querying raw text data without any extra setup.
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
    [("id-0", "Upstash is a serverless data platform.", {"field": "value"})],
)

```

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
    data="What is Upstash?",
    top_k=1,
    include_metadata=True,
)

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Metadata FilteringNamespaces
Assistant
Responses are generated using AI and may contain mistakes.
