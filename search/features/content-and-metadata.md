On this page
* * *
## 
​
Content
The `content` field contains the searchable data of your documents. This is what gets indexed and can be queried.
  * **Required** : You must provide `content` when upserting documents
  * **Format** : JSON object structure
  * **Searchable** : All fields within content are indexed for search
  * **Filterable** : Content fields can be used in filter queries


  * Python
  * TypeScript


Copy
Ask AI
```
index.upsert(
  documents=[
    {
      "id": "star-wars",
      "content": { "text": "Star Wars is a sci-fi space opera."}
    }
  ]
)

```

* * *
## 
​
Metadata
The `metadata` field stores additional context about your documents that won’t be indexed for search. This is useful for data you want to retrieve with your search results but don’t need to search through.
  * **Optional** : You can upsert documents without metadata
  * **Format** : JSON object structure
  * **Not Searchable** : Metadata fields are not indexed


  * Python
  * TypeScript


Copy
Ask AI
```
index.upsert(
  documents=[
    {
      "id": "star-wars",
      "content": { "text": "Star Wars is a sci-fi space opera."},
      "metadata": {
        "genre": "sci-fi",
      }
    }
  ]
)

```

* * *
## 
​
Best Practices
Use Content When| Use Metadata When  
---|---  
Users need to search for this information| Information is for display/reference only (e.g. IDs)  
The field is important for finding relevant documents| The field provides context after finding documents  
You want to filter results by this field| You need to track internal system information  
* * *
## 
​
Examples & Common Patterns
  1. E-commerce Products


Copy
Ask AI
```
{
  // 👇 searchable and filterable
  content: {
    name: "Wireless Headphones",
    description: "Noise-cancelling bluetooth headphones", 
    brand: "Sony",
    category: "Electronics"
  },
  // 👇 not searchable, for reference only
  metadata: {
    sku: "AT-WH-001",
    warehouse_location: "A3-15",
    supplier_id: "SUP-123"
  }
}

```

  2. Knowledge Base Articles


Copy
Ask AI
```
{
  // 👇 searchable and filterable
  content: {
    title: "How to Reset Your Password",
    body: "Follow these steps to reset your password...",
    tags: ["password", "security", "account"]
  },
  // 👇 not searchable, for reference only
  metadata: {
    author_id: "usr_123",
    version: 3,
    approved_by: "usr_456",
    view_count: 1523
  }
}

```

  3. News Articles


Copy
Ask AI
```
{
  // 👇 searchable and filterable
  content: {
    headline: "Tech Company Announces New Product",
    excerpt: "In a press conference today...",
    category: "Technology",
    keywords: ["innovation", "product launch"]
  },
  // 👇 not searchable, for reference only
  metadata: {
    source_url: "https://news.example.com/article/123",
    syndication_rights: true,
    word_count: 200
  }
}

```

Was this page helpful?
YesNo
Suggest editsRaise issue
IndexesFiltering
Assistant
Responses are generated using AI and may contain mistakes.
