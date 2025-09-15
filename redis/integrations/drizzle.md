On this page
### 
​
Quickstart
DrizzleORM provides an `upstashCache()` helper to easily connect with Upstash Redis. To prevent surprises, the cache is always opt-in by default. Nothing is cached until you opt-in for a specific query or enable global caching.
  1. **Install the package:**


Copy
Ask AI
```
npm install drizzle-orm@cache

```

  2. **Configure your Drizzle instance:**


Copy
Ask AI
```
import { upstashCache } from "drizzle-orm/cache/upstash"
import { drizzle } from "drizzle-orm/..."

const db = drizzle(process.env.DB_URL!, {
  cache: upstashCache(),
})

```

You can also explicitly define your Upstash credentials, enable global caching for all queries by default (opt-out) or pass custom caching options:
Copy
Ask AI
```
import { upstashCache } from "drizzle-orm/cache/upstash"
import { drizzle } from "drizzle-orm/..."

const db = drizzle(process.env.DB_URL!, {
  cache: upstashCache({
    // 👇 Redis credentials (optional — can also be pulled from env vars)
    url: "<UPSTASH_URL>",
    token: "<UPSTASH_TOKEN>",
    // 👇 Enable caching for all queries (optional, default false)
    global: true,
    // 👇 Default cache behavior (optional)
    config: { ex: 60 },
  }),
})

```

* * *
### 
​
Cache Behavior
  * **Per-query caching (opt-in, default):**  
No queries are cached unless you explicitly call `.$withCache()`.
Copy
Ask AI
```
await db.insert(users).value({ email: "cacheman@upstash.com" });

// 👇 reads from cache
await db.select().from(users).$withCache()

```

  * **Global caching:**  
When setting `global: true`, all queries will read from cache by default.
Copy
Ask AI
```
const db = drizzle(process.env.DB_URL!, {
  cache: upstashCache({ global: true }),
})

// 👇 reads from cache (no more explicit `$withCache()`)
await db.select().from(users)

```

You can always turn off caching for a specific query:
Copy
Ask AI
```
await db.select().from(users).$withCache(false)

```



* * *
### 
​
Manual Cache Invalidation
Cache invalidation is fully automatic by default. If you ever need to, you can manually invalidate cached queries by table name or custom tags:
Copy
Ask AI
```
// 👇 invalidate all queries that use the `users` table
await db.$cache?.invalidate({ tables: ["usersTable"] })

// 👇 invalidate all queries by custom tag (defined in previous queries)
await db.$cache?.invalidate({ tags: ["custom_key"] })

```

* * *
For more details on this integration, refer to the Drizzle ORM caching documentation.
Was this page helpful?
YesNo
Suggest editsRaise issue
Migrate Regional to Global DatabaseDatadog
Assistant
Responses are generated using AI and may contain mistakes.
