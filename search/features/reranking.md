Upstash Search combines semantic and full text search results for maximum relevancy. Optionally, you can re-rank the returned documents using a state of the art model to further improve relevancy. We provide this additional re-ranking as an opt-in setting because it requires more computational resources and is charged at $1 per 1K re-ranked documents.
  * Python
  * TypeScript


Copy
Ask AI
```
scores = index.search(
    query="space opera",
    limit=2,
    reranking=True,
)

```

Was this page helpful?
YesNo
Suggest editsRaise issue
FilteringAdvanced Settings
Assistant
Responses are generated using AI and may contain mistakes.
