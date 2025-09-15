On this page
This page covers the advanced configuration options available in the Upstash Search. These parameters allow you to fine-tune search behavior for your specific use case and requirements.
## 
​
Reranking
The `reranking` parameter enables enhanced search result reranking using advanced AI models. It’s disabled by default (`false`) and incurs additional costs when enabled.
TypeScript
Python
Copy
Ask AI
```
const results = await index.search({
  query: "complex technical documentation",
  reranking: true // Enable reranking
});

```

**Reranking Options:**
  * **Standard Reranking** (`reranking: false`, default): Uses a simpler, faster model with no additional cost
  * **Advanced Reranking** (`reranking: true`): Uses state-of-the-art models for highest quality results at $1 per 1K operations

Learn more about how reranking works in our Algorithm documentation.
## 
​
Semantic Weight
The `semanticWeight` parameter controls the balance between semantic search and full-text search in the hybrid search process. It accepts values from 0 to 1, with a default of 0.75 (75% semantic, 25% full-text).
TypeScript
Python
Copy
Ask AI
```
// More semantic matching (better for conceptual searches)
const semanticResults = await index.search({
  query: "artificial intelligence concepts",
  semanticWeight: 0.9 // 90% semantic, 10% full-text
});

// More keyword matching (better for exact terms)
const keywordResults = await index.search({
  query: "API documentation React hooks",
  semanticWeight: 0.3 // 30% semantic, 70% full-text
});

```

**Optimization Guidelines:**
  * **Higher semantic weight (0.7-1.0)** : Better for conceptual searches, finding related content, and handling synonyms
  * **Lower semantic weight (0.0-0.4)** : Better for exact keyword matching, technical queries, and specific terms

Read more about hybrid search in our Algorithm documentation.
## 
​
Input Enrichment
The `inputEnrichment` parameter controls whether queries are enhanced using AI before searching. It’s enabled by default (`true`) and significantly improves search quality at the cost of some additional latency.
TypeScript
Python
Copy
Ask AI
```
// Disable input enrichment for faster responses
const results = await index.search({
  query: "space opera",
  inputEnrichment: false // Faster but less enhanced results
});

// Default behavior (enrichment enabled)
const enrichedResults = await index.search({
  query: "space opera"
  // inputEnrichment: true is the default
});

```

**When to Disable Input Enrichment:**
  * When you need the fastest possible response times
  * When you want to preserve the exact user query for full-text search

**Benefits of Input Enrichment:**
  * Handles typos and alternative phrasings
  * Expands queries with related terms and context
  * Improves understanding of user intent
  * Adds semantic context to ambiguous queries

Learn more about input enrichment in our Algorithm documentation.
## 
​
Filter
The `filter` parameter allows you to restrict search results based on content criteria. It accepts either a string expression (SQL-like syntax) or a structured filter object (TypeScript SDK only).
TypeScript
Python
Copy
Ask AI
```
// String filter expression (SQL-like syntax)
const results = await index.search({
  query: "wireless headphones",
  filter: "category = 'Electronics' AND in_stock > 0"
});

// TypeSafe structured filter (TypeScript SDK only)
const results2 = await index.search({
  query: "wireless headphones",
  filter: {
    AND: [
      { category: { equals: 'Electronics' } },
      { in_stock: { greaterThan: 0 } }
    ]
  }
});

```

For detailed information about filter syntax, operators, and examples, see the Filtering documentation.
## 
​
Example: Complete Configuration
Here’s an example showing all parameters configured together:
TypeScript
Python
Copy
Ask AI
```
const results = await index.search({
  query: "machine learning algorithms for data analysis",
  limit: 15,
  filter: "category = 'data-science' AND difficulty_level <= 'intermediate'",
  reranking: true,
  semanticWeight: 0.8,
  inputEnrichment: true
});

```

This configuration:
  * Searches for ML content with enhanced query processing
  * Returns up to 15 results
  * Filters for data science content at beginner to intermediate levels
  * Uses premium reranking for best quality results
  * Emphasizes semantic matching (80%) over keyword matching (20%)
  * Enables input enrichment for better intent understanding


Was this page helpful?
YesNo
Suggest editsRaise issue
RerankingGetting Started
Assistant
Responses are generated using AI and may contain mistakes.
