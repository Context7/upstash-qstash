On this page
* * *
* * *
## 
​
Quickstart
Check out our Next.js quickstart guide if you’re working in Next.js.
## Next.js
Use Upstash Search in your Next.js app
* * *
## 
​
Create a Database
Create a Search Database by navigating to the `Search` tab and clicking on the `Create Database` button.
A dialog with the following options will open:
  * **Name:** Type a name for your database (e.g. “product-search”).
  * **Region:** Choose the region for your database. For best performance, select the region closest to your application. _We plan to support additional regions and cloud providers. Feel free to send your requests tosupport@upstash.com._

Once you’re done, click `Next`, choose a plan, and your Database is ready:
* * *
## 
​
Add Documents
Add documents to your database using our REST API, our SDKs, or directly in the dashboard.
### 
​
1. Add Documents via Dashboard
Navigate to the `Data Browser` section of your Database and click `Upsert Documents`:
A dialog with the following options will open:
  * **Index:** An index to group your data. _If you plan to query all documents in one place, you only need one index (e.g. “product-search”). If you plan to add multi-tenancy, so that each user can only search their own data, for example, you can create one index per user (“user-1”, “user-2”, etc.)._
  * **ID:** An automatically generated ID.
  * **Content:** The searchable data in JSON format.
  * **Metadata:** Optional information attached to this document.

More information about content and metadata can be found here.
* * *
### 
​
2. Add Documents via SDKs
  * Python
  * TypeScript


Copy
Ask AI
```
from upstash_search import Search

client = Search(
    url="<UPSTASH_SEARCH_REST_URL>",
    token="<UPSTASH_SEARCH_REST_TOKEN>",
)

index = client.index("movies")

index.upsert(
    documents=[
        {
            "id": "movie-0",
            "content": {
                "title": "Star Wars",
                "overview": "Sci-fi space opera",
                "genre": "sci-fi",
                "category": "classic",
            },
            "metadata": {
                "poster": "https://poster.link/starwars.jpg",
            },
        },
    ],
)

```

* * *
## 
​
Search Your Database
You can search across your Database the same way: using our REST API, our SDKs or directly in your dashboard.
### 
​
1. Searching via Dashboard
To search your documents, enter a search term and click `Search`:
### 
​
2. Searching Data via SDKs
  * Python
  * TypeScript


Copy
Ask AI
```
scores = index.search( query="space opera", limit=2, )

```

* * *
**That’s it!** 🎉 You’ve just created your first serverless search database with Upstash Search! But this is just the beginning. Upstash Search also supports:
  * Advanced reranking
  * Fine-grained control over search results
  * Metadata-based filtering

We’ll get into those features in the next sections of this documentation. For now, you’ve already mastered the basics!
Was this page helpful?
YesNo
Suggest editsRaise issue
What is Upstash Search?
Assistant
Responses are generated using AI and may contain mistakes.
