On this page
`upstash/vector` is a PHP SDK for Upstash Vector, enabling easier operations on Vector Store. Using `upstash/vector` you can:
  * Upsert a vector with metadata to an index.
  * Fetching the vectors with specified IDs.
  * Querying a vector over pre-defined embeddings.
  * Remove vectors from an index.
  * Access index stats.
  * Reset everything related to an index.

You can find the Github Repository here.
## 
​
Install
To install the SDK, you can use composer:
composer
Copy
Ask AI
```
composer require upstash/vector

```

We also built a Laravel package that you can use to integrate the SDK with your Laravel application. Learn more about our Laravel SDK
## 
​
Usage
### 
​
Initializing the client
There are two pieces of configuration required to use the Upstash vector client: a REST token and REST URL. These values can be passed using environment variables or in code through the initialization of the Index. Find your configuration values in the console dashboard at https://console.upstash.com/.
#### 
​
Using environment variables
The environment variables used to configure the client are the following. You can follow this guide to retrieve credentials.
Copy
Ask AI
```
UPSTASH_VECTOR_REST_URL="your_rest_url"
UPSTASH_VECTOR_REST_TOKEN="your_rest_token"

```

When these environment variables are set, you can initialize the client from the environment.
Copy
Ask AI
```
use Upstash\Vector\Index;

$index = Index::fromEnv();

```

#### 
​
Manual Initialization
If you prefer to pass these values in code, the constructor accepts as parameters the `url` and `token` values. This could be useful if your application needs to interact with multiple projects, each with a different configuration.
Copy
Ask AI
```
use Upstash\Vector\Index;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

```

Was this page helpful?
YesNo
Suggest editsRaise issue
InfoGetting Started with Laravel
Assistant
Responses are generated using AI and may contain mistakes.
