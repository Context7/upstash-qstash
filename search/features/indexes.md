On this page
Upstash Search allows you to partition a single database into multiple isolated indexes. Each index acts as a self-contained subset of the database, search and upsert requests are limited to one index.
* * *
## 
​
Using an Index
Indexes are created implicitly when an upsert operation is performed, so there is no specific endpoint for creating an index. For example, the code snippet below will create the index `foo` if it does not already exist, upsert and search the document only on that index.
  * Python
  * TypeScript


Copy
Ask AI
```
index = client.index("foo")
index.upsert( ... )

```

* * *
## 
​
Listing Indexes
Names of all the active indexes of a database can be listed as follows:
  * Python
  * TypeScript


Copy
Ask AI
```
client.list_indexes()

```

* * *
## 
​
Deleting an Index
Leftover indexes can be deleted as follows:
  * Python
  * TypeScript


Copy
Ask AI
```
client.delete_index("foo")

```

Was this page helpful?
YesNo
Suggest editsRaise issue
AlgorithmContent and Metadata
Assistant
Responses are generated using AI and may contain mistakes.
