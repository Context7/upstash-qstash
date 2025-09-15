On this page
`@upstash/search` is a TypeScript SDK for Upstash AI Search. Using `@upstash/search` you can:
  * Perform AI-powered search queries
  * Upsert documents to an index
  * Fetch documents by their IDs
  * Delete documents from a database
  * Access database stats
  * Reset databases

You can find the GitHub Repository here.
* * *
## 
​
Installation
npm
yarn
pnpm
bun
Copy
Ask AI
```
npm install @upstash/search

```

* * *
## 
​
Usage
### 
​
Initializing the client
There are two pieces of configuration required to use the Upstash search client:
  * a REST token
  * a REST URL

These values can be passed using environment variables or through a configuration object. Find these connection details in the console dashboard.
* * *
#### 
​
Using environment variables (recommended)
You can follow this guide to retrieve the following credentials.
Copy
Ask AI
```
UPSTASH_SEARCH_REST_URL="your_rest_url"
UPSTASH_SEARCH_REST_TOKEN="your_rest_token"

```

When these environment variables are set, the client constructor does not require any additional arguments.
Copy
Ask AI
```
import { Search } from "@upstash/search";

const client = Search.fromEnv();
const index = client.index("movies")

```

* * *
#### 
​
Using a configuration object
The `Search` class accepts a config object containing the `url` and `token` values. This could be useful if your application needs to interact with multiple databases, each with a different configuration.
Copy
Ask AI
```
import { Search } from "@upstash/search";

const client = new Search({
  url: "<SEARCH_INDEX_REST_URL>",
  token: "<SEARCH_INDEX_REST_TOKEN>",
});

const index = client.index("movies")

```

* * *
#### 
​
Typescript
The Search SDK supports defining your content and metadata types at the index level for complete type-safety.
Copy
Ask AI
```
import { Search } from "@upstash/search";
const client = new Search();

type Content = { title: string, genre: string };
type Metadata = { year: number };
const index = client.index<Content, Metadata>("movies");

await index.upsert({
  id: "document-id",
  content: { title: "Star Wars", genre: "sci-fi" },
  metadata: { year: 1977 }
})

```

Passing a `Content` type at the index level will provide type safety for the content coming back from or required for the following commands:
  * `search`
  * `upsert`
  * `fetch`
  * `range`

In cases you don’t want to define a content type at the index level, you can override the index level type definition for a specific command:
Copy
Ask AI
```
const results = await index.upsert<Content>({
  id: "id",
  content: { title: "Movie title", ... }
});

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Advanced SettingsContributing
Assistant
Responses are generated using AI and may contain mistakes.
