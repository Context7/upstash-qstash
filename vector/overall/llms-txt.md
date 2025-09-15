```
================
CODE SNIPPETS
================
TITLE: Install Upstash Vector Python SDK
DESCRIPTION: This command installs the `upstash-vector` SDK from PyPI. It is the first step to begin using the SDK in your Python projects.

SOURCE: https://upstash.com/docs/vector/sdks/py/gettingstarted.mdx

LANGUAGE: bash
CODE:
```
pip install upstash-vector
```

--------------------------------

TITLE: Install Upstash Vector SDK
DESCRIPTION: This snippet demonstrates how to install the @upstash/vector SDK using npm or pnpm. This is the first step to integrate the SDK into your project.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: npm
CODE:
```
npm install @upstash/vector
```

LANGUAGE: pnpm
CODE:
```
pnpm add @upstash/vector
```

--------------------------------

TITLE: Install Upstash Vector PHP SDK with Composer
DESCRIPTION: This snippet demonstrates how to install the `upstash/vector` PHP SDK using Composer, the dependency manager for PHP. This command adds the SDK to your project's dependencies.

SOURCE: https://upstash.com/docs/vector/sdks/php/getting-started.mdx

LANGUAGE: shell
CODE:
```
composer require upstash/vector
```

--------------------------------

TITLE: Configure Upstash Vector Client with Environment Variables
DESCRIPTION: This snippet shows how to set the necessary environment variables (UPSTASH_VECTOR_REST_URL and UPSTASH_VECTOR_REST_TOKEN) for the Upstash Vector client. These variables allow the client to be initialized from the environment.

SOURCE: https://upstash.com/docs/vector/sdks/php/getting-started.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL="your_rest_url"
UPSTASH_VECTOR_REST_TOKEN="your_rest_token"
```

--------------------------------

TITLE: Upsert a Vector with Metadata using Python SDK
DESCRIPTION: This example demonstrates how to upsert a vector along with associated metadata into your Upstash Vector index. It initializes the client from environment variables, generates a random vector, and then performs the upsert operation.

SOURCE: https://upstash.com/docs/vector/sdks/py/gettingstarted.mdx

LANGUAGE: python
CODE:
```
import random
from upstash_vector import Index

# Initialize the index client using environment variables
index = Index.from_env()

def main():
    # Define the dimension based on the index configuration
    dimension = 128
    # Generate a random vector for upsert
    vector_to_upsert = [random.random() for _ in range(dimension)]
    # Additional metadata associated with the vector
    metadata = {"text": "example test for metadata"}

    # Upsert the vector into the index
    index.upsert(vectors=[
        ("id-for-vector", vector_to_upsert, metadata)
    ])
```

--------------------------------

TITLE: Initialize Upstash Vector Client from Environment Variables (PHP)
DESCRIPTION: This PHP snippet demonstrates how to initialize the Upstash Vector client by reading configuration from environment variables. Ensure 'UPSTASH_VECTOR_REST_URL' and 'UPSTASH_VECTOR_REST_TOKEN' are set before calling this method.

SOURCE: https://upstash.com/docs/vector/sdks/php/getting-started.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = Index::fromEnv();
```

--------------------------------

TITLE: Initialize Upstash Vector Client Using Environment Variables
DESCRIPTION: This TypeScript snippet demonstrates initializing the Upstash Vector client when REST URL and Token are provided via environment variables. No arguments are needed for the constructor in this case.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index();
```

--------------------------------

TITLE: Start Flowise Application Locally
DESCRIPTION: This command starts the Flowise application locally, making it accessible via a web browser. Ensure Flowise is installed globally before executing this command.

SOURCE: https://upstash.com/docs/vector/integrations/flowise.mdx

LANGUAGE: bash
CODE:
```
npx flowise start
```

--------------------------------

TITLE: Initialize Upstash Vector Client with Configuration Object
DESCRIPTION: This TypeScript snippet shows how to initialize the Upstash Vector client by passing a configuration object directly to the constructor. This method is useful for managing multiple projects or configurations within a single application.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index({
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>"
});
```

--------------------------------

TITLE: Initialize Upstash Vector Index Client in Python
DESCRIPTION: This code snippet demonstrates how to initialize the Upstash Vector Index client in Python. You can either provide the URL and token directly or load them automatically from environment variables for convenience and security.

SOURCE: https://upstash.com/docs/vector/sdks/py/gettingstarted.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
index = Index(url="UPSTASH_VECTOR_REST_URL", token="UPSTASH_VECTOR_REST_TOKEN")
```

LANGUAGE: python
CODE:
```
from upstash_vector import Index
index = Index.from_env()
```

--------------------------------

TITLE: Manually Initialize Upstash Vector Client (PHP)
DESCRIPTION: This PHP snippet illustrates how to manually initialize the Upstash Vector client by directly passing the REST URL and token. This method is useful for applications interacting with multiple projects or when environment variables are not preferred.

SOURCE: https://upstash.com/docs/vector/sdks/php/getting-started.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);
```

--------------------------------

TITLE: Install Upstash Vector Laravel SDK with Composer
DESCRIPTION: This command installs the `upstash/vector-laravel` SDK into your Laravel project using Composer. It adds the necessary dependencies to interact with Upstash Vector.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: Shell
CODE:
```
composer require upstash/vector-laravel
```

--------------------------------

TITLE: Default Upstash Vector Configuration File Example
DESCRIPTION: This is the default structure of the `config/vector.php` file after publishing. It defines a 'default' connection using environment variables, which can be extended for multiple index configurations.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: PHP
CODE:
```
return [
    'default' => env('UPSTASH_VECTOR_CONNECTION', 'default'),

    'connections' => [
        'default' => [
            'url' => env('UPSTASH_VECTOR_REST_URL'),
            'token' => env('UPSTASH_VECTOR_REST_TOKEN'),
        ],
    ],
];
```

--------------------------------

TITLE: Install Bun for Upstash Vector Development
DESCRIPTION: This command installs Bun, which is used for packaging and dependency management in the Upstash Vector project. Ensure you have a working internet connection to download the installer.

SOURCE: https://upstash.com/docs/vector/sdks/ts/contributing.mdx

LANGUAGE: commandline
CODE:
```
curl -fsSL https://bun.sh/install | bash
```

--------------------------------

TITLE: Configure Upstash Vector Client with Environment Variables
DESCRIPTION: This snippet shows how to set environment variables for the Upstash Vector REST URL and Token. These variables are used by the SDK to authenticate and connect to your Upstash Vector index.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL="your_rest_url"
UPSTASH_VECTOR_REST_TOKEN="your_rest_token"
```

--------------------------------

TITLE: Perform a Resumable Query with cURL
DESCRIPTION: This cURL example demonstrates how to send a POST request to the resumable-query endpoint. It includes the necessary authorization header and a JSON body specifying the query vector, topK results, metadata inclusion, and maximum idle time.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/start-with-vector.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "vector": [0.1, 0.2],
    "topK": 2,
    "includeMetadata": true,
    "maxIdle": 3600
  }'
```

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "vector": [0.1, 0.2],
    "topK": 2,
    "includeMetadata": true,
    "maxIdle": 3600
  }'
```

--------------------------------

TITLE: JSON: Error Upstash Vector Response
DESCRIPTION: This JSON snippet shows an example of an error response from the Upstash Vector REST API. When command execution fails, the response will include an 'error' field with a descriptive message and a 'status' field with the corresponding HTTP status code.

SOURCE: https://upstash.com/docs/vector/api/get-started.mdx

LANGUAGE: json
CODE:
```
{
  "error": "Unauthorized: Invalid auth token",
  "status": 401
}
```

--------------------------------

TITLE: Example Resumable Query Response in JSON
DESCRIPTION: This JSON example illustrates a successful response (HTTP 200 OK) from the resumable-query endpoint. It includes a unique query identifier (uuid) and an array of scores, each containing the vector ID, similarity score, and optionally metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/start-with-vector.mdx

LANGUAGE: json
CODE:
```
{
  "uuid": "550e8400-e29b-41d4-a716-446655440000",
  "scores": [
    {
      "id": "id-0",
      "score": 1.0,
      "metadata": {
        "link": "upstash.com"
      }
    },
    {
      "id": "id-1",
      "score": 0.99996454
    }
  ]
}
```

--------------------------------

TITLE: Define Command-Level Metadata Types in TypeScript
DESCRIPTION: This TypeScript snippet demonstrates how to define or override metadata types at the command level, specifically using the `upsert` operation as an example. This allows for flexible type definitions when an index-level type is not desired or needs to be overridden.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

type Metadata = { genre: string, year: number };

const index = new Index();

index.upsert<Metadata>({ id: 1, vector: [...], metadata: { 
  genre: "comedy",
  year: 1990
}});
```

--------------------------------

TITLE: Insert Data into Upstash Vector Index
DESCRIPTION: This code snippet demonstrates how to insert a vector into an Upstash Vector index. It requires an Upstash account and an existing vector index. The example inserts a vector with ID '1', a 2-dimensional vector, and associated metadata. Replace 'UPSTASH_VECTOR_REST_URL' and 'UPSTASH_VECTOR_REST_TOKEN' with your actual index credentials.

SOURCE: https://upstash.com/docs/vector/overall/getstarted.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(url="UPSTASH_VECTOR_REST_URL", token="UPSTASH_VECTOR_REST_TOKEN")

index.upsert(
  vectors=[
    ("1", [0.6, 0.8], {"field": "value"}),
  ]
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index({
    url: "UPSTASH_VECTOR_REST_URL",
    token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.upsert({ id: "1", vector: [0.6, 0.8], metadata: {field: "value"} })
```

LANGUAGE: go
CODE:
```
import "github.com/upstash/vector-go"

func main() {
  index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

  index.Upsert(vector.Upsert{
	  Id:       "1",
	  Vector:   []float32{0.6, 0.8},
	  Metadata: map[string]any{"field": "value"},
  })
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->upsert(new VectorUpsert(
  id: '1',
  vector: [0.6, 0.8],
  metadata: ['field' => 'value'],
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"id": "1", "vector": [0.6, 0.8], "metadata": {"field": "value"}}'
```

--------------------------------

TITLE: Install LlamaIndex, Upstash Vector, and Dotenv
DESCRIPTION: Install the necessary Python libraries for document parsing and vector database interaction. This includes LlamaIndex for data indexing, Upstash Vector for vector storage, and python-dotenv for environment variable management.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: bash
CODE:
```
pip install llama-index upstash-vector llama-index-vector-stores-upstash python-dotenv
```

--------------------------------

TITLE: Install Required Packages for AI SDK and Upstash Vector
DESCRIPTION: These commands install the necessary npm packages for the AI SDK, OpenAI integration, Zod for schema validation, and the Upstash Vector client. Choose the command corresponding to your preferred package manager (npm, pnpm, or bun).

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: npm
CODE:
```
npm install @ai-sdk/openai ai zod @upstash/vector
```

LANGUAGE: pnpm
CODE:
```
pnpm install @ai-sdk/openai ai zod @upstash/vector
```

LANGUAGE: bun
CODE:
```
bun install @ai-sdk/openai ai zod @upstash/vector
```

--------------------------------

TITLE: Install Upstash Vector Node.js Client
DESCRIPTION: Install the Upstash Vector Node.js client using npm or pnpm. This client is written in TypeScript and provides an interface to interact with Upstash Vector indexes.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: bash
CODE:
```
npm install @upstash/vector
```

LANGUAGE: bash
CODE:
```
pnpm add @upstash/vector
```

--------------------------------

TITLE: Inject Upstash Vector IndexInterface into Laravel Controller
DESCRIPTION: This PHP example shows how to use dependency injection to access the `IndexInterface` in your Laravel controllers. This method provides a more testable and explicit way to interact with the Upstash Vector index compared to using the facade.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: PHP
CODE:
```
namespace App\Http\Controllers;

use Upstash\Vector\Contracts\IndexInterface;

class Controller
{
    public function index(IndexInterface $index)
    {
        $namespaces = $index->listNamespaces();
        
        return response()->json(['namespaces' => $namespaces]);
    }
}
```

--------------------------------

TITLE: Publish Upstash Vector Configuration File in Laravel
DESCRIPTION: Run this Artisan command to publish the Upstash Vector configuration file to your `config` directory. This allows you to customize and manage multiple index connections within your Laravel application.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: Shell
CODE:
```
php artisan vendor:publish --tag="vector-config"
```

--------------------------------

TITLE: Install Dependencies for Gradio RAG App
DESCRIPTION: Install the necessary Python libraries for building the Gradio-based RAG application. This includes Gradio for the UI, LangChain for orchestration, sentence-transformers for embeddings, Upstash Vector for vector storage, python-dotenv for environment variables, transformers for models, and langchain-community/huggingface for integrations.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: bash
CODE:
```
pip install gradio langchain sentence_transformers upstash-vector python-dotenv transformers langchain-community langchain-huggingface
```

--------------------------------

TITLE: Python: Get Upstash Vector Index Info
DESCRIPTION: This Python example demonstrates how to use the `info` method on an Upstash Vector index to retrieve and display statistical information. It shows how to access the total vector count, pending vector count, index size, dimension, similarity function, and iterate through namespace statistics.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/info.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index.from_env()

# Get statistical information about the index
info_result = index.info()

# Display the info result
print("Vector Count:", info_result.vector_count)
print("Pending Vector Count:", info_result.pending_vector_count)
print("Index Size:", info_result.index_size)
print("Dimension:", info_result.dimension)
print("Similarity Function:", info_result.similarity_function)

for ns, ns_info in info_result.namespaces.items():
    print("Namespace:", ns, "Vector Count:", ns_info.vector_count)
    print("Namespace:", ns, "Pending Vector Count:", ns_info.pending_vector_count)
```

--------------------------------

TITLE: Python: Full Resumable Query Example
DESCRIPTION: A complete example demonstrating the end-to-end usage of a synchronous resumable query. It includes creating an index, upserting sample vectors, initiating a resumable query, fetching and printing initial results, and finally stopping the query to release resources.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

# Create an index instance
index = Index()

# Upsert vectors into the index
index.upsert(
    vectors=[
        ("id1", [0.1, 0.2], {"field": "value1"}),
        ("id2", [0.3, 0.4], {"field": "value2"}),
        ("id3", [0.5, 0.6], {"field": "value3"}),
    ],
    namespace="example-namespace"
)

# Start a resumable query
query = index.resumable_query(
    vector=[0.1, 0.2],
    top_k=2,
    include_metadata=True,
    include_vectors=True,
    namespace="example-namespace"
)

# Fetch initial results
results = query.start()

# Access result data
for result in results:
    print(f"ID: {result.id}, Metadata: {result.metadata}")

# Stop the query when done
query.stop()
```

--------------------------------

TITLE: API Reference for Resumable Query
DESCRIPTION: This section details the API for performing resumable queries. It covers the request method, endpoint, authentication, request body parameters, path parameters, and the structure of the successful response.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/start-with-vector.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/resumable-query/{namespace}
Auth Method: bearer

Request Body:
- vector: number[] (required)
  - Description: The query vector. (Note: The query vector should have the same dimensions as your index.)
- topK: number (default: 10)
  - Description: The total number of the vectors that you want to receive as a query result. The response will be sorted based on the distance metric score, and at most `topK` many vectors will be returned.
- includeMetadata: boolean (default: false)
  - Description: Whether to include the metadata of the vectors in the response, if any. It is recommended to set this to `true` to easily identify vectors.
- includeVectors: boolean (default: false)
  - Description: Whether to include the vector values in the response. It is recommended to set this to `false` as the vector values can be quite big, and not needed most of the time.
- includeData: boolean (default: false)
  - Description: Whether to include the data of the vectors in the response, if any.
- filter: string (default: "")
  - Description: [Metadata filter](/vector/features/filtering) to apply.
- maxIdle: number
  - Description: Maximum idle time for the resumable query in seconds.
- weightingStrategy: string
  - Description: For sparse vectors of sparse and hybrid indexes, specifies what kind of weighting strategy should be used while querying the matching non-zero dimension values of the query vector with the documents. If not provided, no weighting will be used. Only possible value is `IDF` (inverse document frequency).
- fusionAlgorithm: string
  - Description: Fusion algorithm to use while fusing scores from dense and sparse components of a hybrid index. If not provided, defaults to `RRF` (Reciprocal Rank Fusion). Other possible value is `DBSF` (Distribution-Based Score Fusion).

Path Parameters:
- namespace: string (default: "")
  - Description: The namespace to use. When no namespace is specified, the default namespace will be used.

Response (200 OK):
- uuid: string (required)
  - Description: A unique identifier for the resumable query.
- scores: Object[]
  - Description: Array of score objects.
  - Properties of scores[]:
    - id: string (required)
      - Description: The id of the vector.
    - score: number (required)
      - Description: The similarity score of the vector, calculated based on the distance metric of your index.
    - vector: number[]
      - Description: The dense vector value for dense and hybrid indexes.
    - sparseVector: Object[]
      - Description: The sparse vector value for sparse and hybrid indexes.
      - Properties of sparseVector[]:
        - indices: number[]
          - Description: Indices of the non-zero valued dimensions.
        - values: number[]
          - Description: Values of the non-zero valued dimensions.
    - metadata: Object
      - Description: The metadata of the vector, if any.
    - data: string
      - Description: The unstructured data of the vector, if any.
```

--------------------------------

TITLE: Install Upstash Vector and Dotenv in Python
DESCRIPTION: This command installs the necessary Python libraries: `upstash-vector` for interacting with the Upstash Vector database and `python-dotenv` for loading environment variables from a `.env` file. These libraries are essential for setting up and running the semantic search application.

SOURCE: https://upstash.com/docs/vector/tutorials/semantic_search.mdx

LANGUAGE: Bash
CODE:
```
pip install upstash-vector python-dotenv
```

--------------------------------

TITLE: Install Python Libraries for LangChain and Upstash Vector
DESCRIPTION: Install the necessary Python libraries using pip. These include 'upstash-vector' for Upstash integration, 'python-dotenv' for environment variable management, and 'langchain' and 'langchain-community' for LangChain functionalities.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: bash
CODE:
```
pip install upstash-vector python-dotenv langchain langchain-community
```

--------------------------------

TITLE: Perform a Resumable Query with cURL
DESCRIPTION: This cURL example demonstrates how to send a POST request to the resumable-query-data endpoint. It includes setting the Authorization header with a bearer token and a JSON request body specifying the text data, desired number of results (topK), inclusion of metadata, and maximum idle time for the query.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/start-with-data.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "data": "Hello world",
    "topK": 2,
    "includeMetadata": true,
    "maxIdle": 3600
  }'
```

--------------------------------

TITLE: Configure Upstash Vector Environment Variables
DESCRIPTION: Set these environment variables in your `.env` file to provide the necessary REST URL and Token for connecting to your Upstash Vector index. These values are crucial for the SDK to authenticate and communicate with the database.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: Bash
CODE:
```
UPSTASH_VECTOR_REST_URL="your_rest_url"
UPSTASH_VECTOR_REST_TOKEN="your_rest_token"
```

--------------------------------

TITLE: Example Output of Document Query
DESCRIPTION: This is an example of the response received from the LLM after querying the parsed document. It summarizes the main points discussed in the 'global_warming.txt' document.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: plaintext
CODE:
```
The main points discussed in the document include the impact of global warming on agriculture 
and food production systems, the importance of adopting sustainable food practices to mitigate 
these effects, the role of agriculture in contributing to global warming through GHG emissions, 
deforestation, and the use of synthetic fertilizers, and the need for sustainable food systems 
to address environmental challenges and ensure food security for future generations.
```

--------------------------------

TITLE: Curl Example for Upstash Vector Index Info
DESCRIPTION: This curl command demonstrates how to make a GET request to the Upstash Vector /info endpoint to retrieve index information. It requires setting the Authorization header with a Bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/info.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/info \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: JSON: Successful Upstash Vector Response
DESCRIPTION: This JSON snippet illustrates a successful response from the Upstash Vector REST API. Upon successful command execution, the response will contain a 'result' field with a value indicating success, typically 'Success'.

SOURCE: https://upstash.com/docs/vector/api/get-started.mdx

LANGUAGE: json
CODE:
```
{ "result": "Success" }
```

--------------------------------

TITLE: Configure Multiple Upstash Vector Connections in Laravel
DESCRIPTION: This PHP configuration demonstrates how to set up multiple Upstash Vector connections within your `config/vector.php` file. Each connection can have its own URL and token, allowing you to manage different indexes in your application.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: PHP
CODE:
```
return [
    'default' => env('UPSTASH_VECTOR_CONNECTION', 'default'),

    'connections' => [
        'default' => [
            'url' => env('UPSTASH_VECTOR_REST_URL'),
            'token' => env('UPSTASH_VECTOR_REST_TOKEN'),
        ],
        'another' => [
            'url' => env('SECOND_UPSTASH_VECTOR_REST_URL'),
            'token' => env('SECOND_UPSTASH_VECTOR_REST_TOKEN'),
        ],
    ],
];
```

--------------------------------

TITLE: APIDOC: Upstash Vector HTTP Response Codes
DESCRIPTION: This section documents the standard HTTP response codes returned by the Upstash Vector REST API. It provides a description for each status code, indicating the nature of the response (success, client error, authentication error, or method not allowed).

SOURCE: https://upstash.com/docs/vector/api/get-started.mdx

LANGUAGE: APIDOC
CODE:
```
HTTP Response Codes:
- `200 OK`: When request is accepted and successfully executed.
- `400 Bad Request`: When there's a syntax error, an invalid/unsupported command is sent or command execution fails.
- `401 Unauthorized`: When authentication fails; auth token is missing or invalid.
- `405 Method Not Allowed`: When an unsupported HTTP method is used. Only `HEAD`, `GET`, `POST`, and `PUT` methods are allowed.
```

--------------------------------

TITLE: Use Upstash Vector Facade in Laravel
DESCRIPTION: This PHP code snippet demonstrates how to interact with your Upstash Vector index using the `Vector` facade provided by the Laravel SDK. Ensure your environment variables are set up correctly for this to work.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Laravel\Facades\Vector;

Vector::getInfo(); // Fetches the index info.
```

--------------------------------

TITLE: Python: Initialize UpstashVectorStore with Namespace
DESCRIPTION: This example demonstrates how to initialize the UpstashVectorStore with a specific namespace. Using namespaces allows for the separation and organization of different types of documents within your Upstash Vector index.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaindex.mdx

LANGUAGE: python
CODE:
```
vector_store = UpstashVectorStore(
    url=your_upstash_url, 
    token=your_upstash_token, 
    namespace=your_namespace,
    )
```

--------------------------------

TITLE: Python Example to Perform Batch Queries on Upstash Vector Index
DESCRIPTION: This Python example illustrates how to use the `index.query_many` method to execute multiple queries in a single API call, reducing round trips. It demonstrates constructing a list of query dictionaries, each with its own parameters, and then processing the results for each individual query in the batch.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/query.mdx

LANGUAGE: python
CODE:
```
import random

from upstash_vector import Index

index = Index.from_env()

# Generate a random vector for similarity comparison
dimension = 128  # Adjust based on your index's dimension
query_vectors = [[random.random() for _ in range(dimension)] for _ in range(2)]

# Execute the query
query_results = index.query_many(
    queries=[
        {
            "vector": query_vectors[0],
            "include_metadata": True,
            "include_data": True,
            "include_vectors": False,
            "top_k": 5,
            "filter": "genre = 'fantasy' and title = 'Lord of the Rings'",
        },
        {
            "vector": query_vectors[1],
            "include_metadata": False,
            "include_data": False,
            "include_vectors": True,
            "top_k": 3,
            "filter": "genre = 'drama'",
        },
    ]
)

for i, query_result in enumerate(query_results):
    print(f"Query-{i} result:")

    # Print the query result
    for result in query_result:
        print("Score:", result.score)
        print("ID:", result.id)
        print("Vector:", result.vector)
        print("Metadata:", result.metadata)
        print("Data:", result.data)
```

--------------------------------

TITLE: Upstash Vector Embedding Models Overview
DESCRIPTION: This video guide provides an overview of how Upstash embeddings work, compares the different models offered, and helps users determine which model is best suited for their specific use case. It covers the automatic vectorization process and the benefits of using integrated embedding models.

SOURCE: https://upstash.com/docs/vector/features/embeddingmodels.mdx

LANGUAGE: HTML
CODE:
```
<iframe
  id="intro-video"
  width='560'
  height='315'
  src='https://www.youtube.com/embed/aImBIYwn5Ew?rel=0&disablekb=1'
  title='YouTube video player'
  frameBorder='0'
  allow='accelerometer; fullscreen; clipboard-write; encrypted-media; gyroscope'
  allowFullScreen></iframe>
```

--------------------------------

TITLE: Install Python Libraries for LlamaParse and Upstash Vector
DESCRIPTION: This command installs the necessary Python libraries: 'llama-index' for core functionalities, 'upstash-vector' for the vector store client, 'llama-index-vector-stores-upstash' for the Upstash integration, and 'python-dotenv' for environment variable management. These are required to set up and run the document parsing and querying system.

SOURCE: https://upstash.com/docs/vector/integrations/llamaparse.mdx

LANGUAGE: bash
CODE:
```
pip install llama-index upstash-vector llama-index-vector-stores-upstash python-dotenv
```

--------------------------------

TITLE: cURL: Upsert Data into Upstash Vector
DESCRIPTION: This cURL command sends an upsert request to the Upstash Vector database. It requires the `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` environment variables to be set. The command sends a JSON payload containing an 'id' and a 'vector' array.

SOURCE: https://upstash.com/docs/vector/api/get-started.mdx

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"id": "id-0", "vector": [0.87, 0.99]}'
```

--------------------------------

TITLE: Install Python Dependencies for Hugging Face and Upstash
DESCRIPTION: Install the necessary Python libraries including LangChain, sentence-transformers, upstash-vector, python-dotenv, langchain-community, and langchain-huggingface. This command ensures all required packages are available for the project.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: bash
CODE:
```
pip install langchain sentence_transformers upstash-vector python-dotenv langchain-community langchain-huggingface
```

--------------------------------

TITLE: Install Flowise Globally using npm
DESCRIPTION: This command installs Flowise globally on your system using npm. It is a prerequisite for running Flowise locally and developing LLM orchestration flows.

SOURCE: https://upstash.com/docs/vector/integrations/flowise.mdx

LANGUAGE: bash
CODE:
```
npm install -g flowise
```

--------------------------------

TITLE: TypeScript: Get Upstash Vector Index Info
DESCRIPTION: This TypeScript code snippet demonstrates how to retrieve information about an Upstash Vector index using the `index.info()` method. It shows the basic API call and an example of the expected JSON response structure, including details for both the default and a named namespace.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/info.mdx

LANGUAGE: TypeScript
CODE:
```
const infoResponse = await index.info();
/*
{
  vectorCount: 17,
  pendingVectorCount: 0,
  indexSize: 551158,
  dimension: 1536,
  similarityFunction: "COSINE",
  namespaces: {
    "": { // default namespace
      vectorCount: 10,
      pendingVectorCount: 0,
    },
    "my-namespace": {
      vectorCount: 7,
      pendingVectorCount: 0,
    }
  }
}
*/
```

--------------------------------

TITLE: Bash: Install Python Libraries for LlamaIndex and Upstash
DESCRIPTION: Install necessary Python libraries including LlamaIndex, Upstash Vector, and dotenv using pip. These libraries are essential for setting up the RAG system and managing environment variables.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaindex.mdx

LANGUAGE: bash
CODE:
```
pip install llama-index upstash-vector llama-index-vector-stores-upstash python-dotenv
```

--------------------------------

TITLE: Perform Similarity Search on Upstash Vector Index
DESCRIPTION: This code snippet demonstrates how to perform a similarity search on an Upstash Vector index. You must provide a query vector whose dimension matches the index's dimension. Metadata filtering is also supported. Note that Upstash is eventually consistent, so new or updated vectors may have a slight delay before being queryable.

SOURCE: https://upstash.com/docs/vector/overall/getstarted.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import Index

index = Index(url="UPSTASH_VECTOR_REST_URL", token="UPSTASH_VECTOR_REST_TOKEN")

index.query(
    vector=[0.6, 0.8],
    top_k=3,
    include_metadata=True,
)
```

LANGUAGE: JavaScript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({ vector: [0.6, 0.8], topK: 3, includeMetadata: true })
```

LANGUAGE: Go
CODE:
```
import "github.com/upstash/vector-go"

func main() {
  index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

  index.Query(vector.Query{
	  Vector:          []float32{0.6, 0.8},
	  TopK:            3,
	  IncludeMetadata: true,
  })
}
```

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: '<UPSTASH_VECTOR_REST_URL>',
  token: '<UPSTASH_VECTOR_REST_TOKEN>',
);

$index->query(new VectorQuery(
  vector: [0.6, 0.8],
  topK: 3,
  includeMetadata: true,
));
```

LANGUAGE: cURL
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector": [0.6, 0.8], "topK": 3, "includeMetadata": "true"}'
```

--------------------------------

TITLE: Initialize Embeddings and Upstash Vector Store
DESCRIPTION: Import required libraries and initialize the Hugging Face embeddings model and the Upstash Vector store. This setup prepares the application to generate embeddings from text and store them in the Upstash Vector database for semantic search.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: python
CODE:
```
# Import libraries
import gradio as gr
from dotenv import load_dotenv
from langchain_huggingface.embeddings import HuggingFaceEmbeddings
from langchain_community.vectorstores.upstash import UpstashVectorStore
from transformers import pipeline
from langchain.schema import Document

# Load environment variables
load_dotenv()

# Set up embeddings and Upstash Vector store
embeddings = HuggingFaceEmbeddings(model_name="sentence-transformers/all-mpnet-base-v2")
vector_store = UpstashVectorStore(embedding=embeddings)
```

--------------------------------

TITLE: Install Python Libraries for LangChain and Upstash Vector
DESCRIPTION: This command installs the necessary Python packages for integrating LangChain with Upstash Vector. It includes 'upstash-vector' for database interaction, 'langchain' and 'langchain-community' for the framework, and 'python-dotenv' for environment variable management.

SOURCE: https://upstash.com/docs/vector/integrations/langchain.mdx

LANGUAGE: bash
CODE:
```
pip install upstash-vector langchain langchain-community python-dotenv
```

--------------------------------

TITLE: Example JSON Response for List Namespaces
DESCRIPTION: This JSON example shows a successful response (HTTP 200 OK) from the /list-namespaces endpoint. The 'result' field contains an array of strings, where each string is the name of a namespace. The empty string "" represents the default namespace.

SOURCE: https://upstash.com/docs/vector/api/endpoints/list-namespaces.mdx

LANGUAGE: json
CODE:
```
{
    "result": ["", "ns0", "ns1"]
}
```

--------------------------------

TITLE: Python: Start a Synchronous Resumable Query
DESCRIPTION: Initiate the resumable query to fetch the initial set of results. The `start()` method returns a list of result objects, each containing properties like ID and metadata, depending on the query configuration.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
initial_results = query.start()
```

--------------------------------

TITLE: Install Langflow and Upstash Vector via pip
DESCRIPTION: This command installs the necessary Python packages for Langflow and Upstash Vector. Ensure you have pip installed and a compatible Python environment. This step is required to run Langflow and interact with Upstash Vector locally.

SOURCE: https://upstash.com/docs/vector/integrations/langflow.mdx

LANGUAGE: bash
CODE:
```
pip install langflow upstash-vector
```

--------------------------------

TITLE: Access Specific Upstash Vector Connection with Facade
DESCRIPTION: This PHP code shows how to access a specific Upstash Vector connection when multiple connections are configured. Use the `connection()` method on the `Vector` facade, passing the name of the desired connection.

SOURCE: https://upstash.com/docs/vector/sdks/php/laravel.mdx

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Laravel\Facades\Vector;

Vector::connection('another')->getInfo();
```

--------------------------------

TITLE: Example Response for Upstash Vector Index Info
DESCRIPTION: This JSON object illustrates a typical successful response (HTTP 200 OK) from the Upstash Vector /info endpoint. It provides a comprehensive overview of the index's current state, including vector counts, size, dimensions, similarity function, index type, and detailed configurations for dense and sparse indexes, along with namespace-specific data.

SOURCE: https://upstash.com/docs/vector/api/endpoints/info.mdx

LANGUAGE: json
CODE:
```
{
  "result": {
    "vectorCount": 7,
    "pendingVectorCount": 0,
    "indexSize": 43501,
    "dimension": 1024,
    "similarityFunction": "COSINE",
    "indexType": "HYBRID",
    "denseIndex": {
      "dimension": 1024,
      "similarityFunction": "COSINE",
      "embeddingModel": "BGE_M3"
    },
    "sparseIndex": {
      "embeddingModel": "BM25"
    },
    "namespaces": {
      "": {
        "vectorCount": 6,
        "pendingVectorCount": 0
      },
      "ns": {
        "vectorCount": 1,
        "pendingVectorCount": 0
      }
    }
  }
}
```

--------------------------------

TITLE: Define Index-Level Metadata Types in TypeScript
DESCRIPTION: This TypeScript snippet illustrates how to define a metadata type at the index level for the Upstash Vector SDK. This provides strong type safety for metadata across various index operations like query, upsert, fetch, and range.

SOURCE: https://upstash.com/docs/vector/sdks/ts/getting-started.mdx

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

type Metadata = { genre: string, year: number };

const index = new Index<Metadata>();
```

--------------------------------

TITLE: API Reference: Resumable Query Data Endpoint
DESCRIPTION: This section provides the API documentation for the resumable query data endpoint. It details the HTTP method, URL structure, authentication, and all available request body and path parameters, along with their types, descriptions, and default values. The response structure is noted to be the same as a standard resumable query.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/start-with-data.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/resumable-query-data/{namespace}
Auth Method: bearer

Request Body Parameters:
- "data": string (required)
  Description: The text data to be embedded and used for querying.
- "topK": number (default: 10)
  Description: The total number of the vectors that you want to receive as a query result. The response will be sorted based on the distance metric score, and at most `topK` many vectors will be returned.
- "includeMetadata": boolean (default: false)
  Description: Whether to include the metadata of the vectors in the response, if any. It is recommended to set this to `true` to easily identify vectors.
- "includeVectors": boolean (default: false)
  Description: Whether to include the vector values in the response. It is recommended to set this to `false` as the vector values can be quite big, and not needed most of the time.
- "includeData": boolean (default: false)
  Description: Whether to include the data of the vectors in the response, if any.
- "filter": string (default: "")
  Description: [Metadata filter](/vector/features/filtering) to apply.
- "maxIdle": number
  Description: Maximum idle time for the resumable query in seconds.
- "weightingStrategy": string
  Description: For sparse vectors of sparse and hybrid indexes, specifies what kind of weighting strategy should be used while querying the matching non-zero dimension values of the query vector with the documents. If not provided, no weighting will be used. Only possible value is `IDF` (inverse document frequency).
- "fusionAlgorithm": string
  Description: Fusion algorithm to use while fusing scores from dense and sparse components of a hybrid index. If not provided, defaults to `RRF` (Reciprocal Rank Fusion). Other possible value is `DBSF` (Distribution-Based Score Fusion).
- "queryMode": string
  Description: Query mode for hybrid indexes with Upstash-hosted embedding models. Specifies whether to run the query in only the dense index, only the sparse index, or in both. If not provided, defaults to `HYBRID`. Possible values are `HYBRID`, `DENSE`, and `SPARSE`.

Path Parameters:
- "namespace": string (default: "")
  Description: The namespace to use. When no namespace is specified, the default namespace will be used.

Response:
  Same as Resumable Query.
```

--------------------------------

TITLE: Python: Initialize Upstash Vector Store with Namespace
DESCRIPTION: This example demonstrates how to initialize the UpstashVectorStore with a specific namespace. Namespaces allow you to logically separate different types of documents within the same Upstash Vector instance, improving organization and query efficiency. Replace 'my_namespace' with your desired namespace.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
store = UpstashVectorStore(embedding=True, namespace="my_namespace")
```

--------------------------------

TITLE: TypeScript: Basic Upstash Vector Range Query
DESCRIPTION: This example demonstrates a basic usage of the Upstash Vector 'range' method in TypeScript. It retrieves vectors with a limit of 2, starting from cursor 0, and includes metadata. The expected response structure with 'nextCursor' and 'vectors' is also shown.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/range.mdx

LANGUAGE: TypeScript
CODE:
```
const responseRange = await index.range(
  {
    cursor: 0,
    limit: 2,
    includeMetadata: true,
  },
  { namespace: "my-namespace" }
);

/*
{
  nextCursor: '2',
  vectors: [
    { 
      id: '0',
      metadata: {
        keyword: "Vector"
      } 
    },
    { 
      id: '19',
      metadata: {
        keyword: "Redis"
      } 
    }
  ]
}*/
```

--------------------------------

TITLE: Install Upstash Vector Python Client
DESCRIPTION: Install the Upstash Vector Python client library using pip. This library is essential for interacting with the Upstash Vector database to perform vector operations for the semantic cache.

SOURCE: https://upstash.com/docs/vector/sdk/semantic-cache-py.mdx

LANGUAGE: Python
CODE:
```
pip install upstash-vector
```

--------------------------------

TITLE: JSON Response Examples for Delete Namespace
DESCRIPTION: These JSON examples illustrate the possible responses from the delete namespace API endpoint. A 200 OK response indicates success, while a 404 Not Found response indicates the specified namespace does not exist.

SOURCE: https://upstash.com/docs/vector/api/endpoints/delete-namespace.mdx

LANGUAGE: json
CODE:
```
200 OK
{
    "result": "Success"
}
```

LANGUAGE: json
CODE:
```
404 Not Found
{
    "error": "Namespace ns for the index $NAME does not exist",
    "status": 404
}
```

--------------------------------

TITLE: TypeScript: Upstash Vector Range Query with ID Prefix
DESCRIPTION: This TypeScript example illustrates how to use the 'range' method with an ID prefix. It retrieves vectors whose IDs start with 'test-', demonstrating how to filter results based on a common ID pattern. The output shows the 'nextCursor' and the filtered vector IDs.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/range.mdx

LANGUAGE: TypeScript
CODE:
```
const responseRange = await index.range({
  cursor: 0,
  limit: 2,
  prefix: "test-",
});

/*
{
  nextCursor: '2',
  vectors: [
    { id: 'test-1' },
    { id: 'test-2' },
  ]
}*/
```

--------------------------------

TITLE: Curl Example for Ranging Vectors
DESCRIPTION: This example demonstrates how to use curl to perform a range operation on vectors in Upstash Vector. It shows how to specify the cursor, limit, and include metadata, both for the default namespace and a specific namespace.

SOURCE: https://upstash.com/docs/vector/api/endpoints/range.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/range \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "cursor": "0", "limit": 2, "includeMetadata": true }'
```

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/range/ns \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "cursor": "0", "limit": 2, "includeMetadata": true }'
```

--------------------------------

TITLE: Curl Example: Fetch Vectors from a Specific Namespace
DESCRIPTION: This cURL example shows how to fetch multiple vectors by their IDs, including metadata, from a specified namespace (e.g., 'ns'). Replace `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` with your actual Upstash Vector credentials.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/fetch/ns \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": ["id-0", "id-1"], "includeMetadata": true }'
```

--------------------------------

TITLE: Python Example to Query Upstash Vector Index with Namespace
DESCRIPTION: This Python snippet demonstrates how to specify a particular namespace when performing a query on the Upstash Vector index. By providing the `namespace` parameter, you can direct the query to operate within a specific data partition, rather than the default namespace.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/query.mdx

LANGUAGE: python
CODE:
```
index.query(..., namespace="ns")
```

--------------------------------

TITLE: Curl Example: Fetch Vectors by ID
DESCRIPTION: This cURL example demonstrates how to fetch a vector by its ID, including its metadata, from the default namespace. Replace `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` with your actual Upstash Vector credentials.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/fetch \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": ["id-0"], "includeMetadata": true }'
```

--------------------------------

TITLE: Python Example to Query Upstash Vector Index
DESCRIPTION: This Python code demonstrates how to use the `index.query` method to retrieve vectors from an Upstash Vector index. It shows how to generate a random query vector, specify parameters like `include_metadata`, `include_data`, `top_k`, and apply a metadata filter, then iterates and prints the results.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/query.mdx

LANGUAGE: python
CODE:
```
import random

from upstash_vector import Index

index = Index.from_env()

# Generate a random vector for similarity comparison
dimension = 128  # Adjust based on your index's dimension
query_vector = [random.random() for _ in range(dimension)]

# Execute the query
query_result = index.query(
    vector=query_vector,
    include_metadata=True,
    include_data=True,
    include_vectors=False,
    top_k=5,
    filter="genre = 'fantasy' and title = 'Lord of the Rings'",
)

# Print the query result
for result in query_result:
    print("Score:", result.score)
    print("ID:", result.id)
    print("Vector:", result.vector)
    print("Metadata:", result.metadata)
    print("Data:", result.data)
```

--------------------------------

TITLE: Install LlamaIndex and Upstash Vector Dependencies
DESCRIPTION: This snippet provides the command to install necessary Python packages for integrating LlamaIndex with Upstash Vector. It includes LlamaIndex core, the Upstash Vector store connector, and dotenv for environment variable management.

SOURCE: https://upstash.com/docs/vector/integrations/llamaindex.mdx

LANGUAGE: bash
CODE:
```
pip install llama-index upstash-vector llama-index-vector-stores-upstash python-dotenv
```

--------------------------------

TITLE: JSON Response Example: Successful Reset
DESCRIPTION: This JSON snippet shows an example of a successful response after a reset operation on an Upstash Vector index. A 200 OK status is returned with a 'result' field indicating 'Success'.

SOURCE: https://upstash.com/docs/vector/api/endpoints/reset.mdx

LANGUAGE: json
CODE:
```
{
    "result": "Success"
}
```

--------------------------------

TITLE: JSON Response Example for Range Vectors
DESCRIPTION: This example provides a sample JSON response for a successful range operation on vectors. It illustrates the structure of the 'nextCursor' and 'vectors' fields, including vector IDs and metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/range.mdx

LANGUAGE: json
CODE:
```
{
    "result": {
        "nextCursor": "2",
        "vectors": [
            {
                "id": "id-0",
                "metadata": {
                    "link": "upstash.com"
                }
            },
            {
                "id": "id-1"
            }
        ]
    }
}
```

--------------------------------

TITLE: Successful Random Vector Response Example
DESCRIPTION: This JSON snippet shows an example of a successful response when fetching a random vector. It includes the 'id' of the vector and its 'vector' (dense) values.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch-random.mdx

LANGUAGE: json
CODE:
```
{
    "result": {
        "id": "id-0",
        "vector": [0.1, 0.2]
    }
}
```

--------------------------------

TITLE: Format Code in Upstash Vector Project with Bun
DESCRIPTION: This command runs the code formatter for the Upstash Vector project using Bun. It helps maintain consistent code style across the codebase. Ensure all dependencies are installed before running.

SOURCE: https://upstash.com/docs/vector/sdks/ts/contributing.mdx

LANGUAGE: bash
CODE:
```
bun run fmt
```

--------------------------------

TITLE: Fetch Random Vector with Curl
DESCRIPTION: These examples demonstrate how to fetch a random vector using curl. The first example fetches from the default namespace, while the second specifies a custom namespace 'ns'. Both require an Authorization header with a Bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch-random.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/random \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/random/ns \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Bootstrap Next.js Application for RAG Chatbot
DESCRIPTION: This command initializes a new Next.js project named 'rag-chatbot' with TypeScript support and navigates into the project directory. It's the first step in setting up the development environment for the RAG chatbot.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: Bash
CODE:
```
npx create-next-app rag-chatbot --typescript
cd rag-chatbot
```

--------------------------------

TITLE: Python: Start an Asynchronous Resumable Query
DESCRIPTION: Initiate an asynchronous resumable query to fetch its initial results. The `async_start()` method returns a list of result objects, similar to its synchronous counterpart, but designed for `await` operations.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
initial_results = await query.async_start()
```

--------------------------------

TITLE: Upstash Semantic Cache GitHub Repository
DESCRIPTION: This link directs to the official GitHub repository for the Upstash Semantic Cache project. It contains the source code, detailed documentation, and examples for the library. Developers can use this resource to explore the implementation details, contribute, or report issues.

SOURCE: https://upstash.com/docs/vector/sdk/semantic-cache-js.mdx

LANGUAGE: APIDOC
CODE:
```
URL: https://github.com/upstash/semantic-cache
Description: Official GitHub repository for the Upstash Semantic Cache library.
```

--------------------------------

TITLE: Upstash Vector Feature Request and Upgrade Process
DESCRIPTION: This section details the methods for requesting new features during the beta release and the process for upgrading from the free tier to the pay-as-you-go tier. Feature requests can be submitted via email or chatbot, and upgrades are initiated by providing credit card information.

SOURCE: https://upstash.com/docs/vector/help/faq.mdx

LANGUAGE: APIDOC
CODE:
```
Feature Request:
  - Method 1: Email support@upstash.com
  - Method 2: Use the chatbot on the Upstash page

Upgrade from Free Tier to Pay-as-you-go:
  - Process: Enter credit card information
  - Billing: Charges apply only after exceeding free tier limits
```

--------------------------------

TITLE: JSON Response Example: Successful Vector Fetch
DESCRIPTION: This JSON example illustrates a successful response when fetching vectors. It shows an array of vector objects, including their IDs and optionally metadata, matching the order of the requested IDs. A `null` entry indicates a vector not found.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch.mdx

LANGUAGE: json
CODE:
```
{
    "result": [
        {
            "id": "id-0",
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1"
        }
    ]
}
```

--------------------------------

TITLE: Run the Chatbot Application
DESCRIPTION: This command initiates the development server for the chatbot application. Executing this command will make the chatbot accessible in your local environment, allowing you to interact with the implemented UI and API routes.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: Bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Successful Vector Deletion Response Example
DESCRIPTION: This JSON example illustrates a successful response after deleting vectors from an Upstash Vector index. The 'deleted' field indicates the number of vectors that were successfully removed.

SOURCE: https://upstash.com/docs/vector/api/endpoints/delete.mdx

LANGUAGE: json
CODE:
```
{
    "result": {
        "deleted": 2
    }
}
```

--------------------------------

TITLE: Set Up Gradio Interface for Question Answering
DESCRIPTION: Configure a Hugging Face Question Answering model and integrate it with a Gradio interface. The `answer_question` function retrieves relevant documents from Upstash Vector based on a query, uses the most relevant context to answer the question, and then displays the answer and context.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: python
CODE:
```
# Set up a Hugging Face Question Answering model
qa_pipeline = pipeline("question-answering", model="distilbert-base-cased-distilled-squad")

# Gradio interface function
def answer_question(query):
    # Retrieve relevant documents from Upstash Vector
    results = vector_store.similarity_search(query, k=3)
    
    # Use the most relevant document for QA
    if results:
        context = results[0].page_content
        qa_input = {"question": query, "context": context}
        answer = qa_pipeline(qa_input)["answer"]
        return f"Answer: {answer}\n\nContext: {context}"
    else:
        return "No relevant context found."

# Set up Gradio interface
iface = gr.Interface(
    fn=answer_question,
    inputs="text",
    outputs="text",
    title="RAG Application",
    description="Ask a question, and the app will retrieve relevant information and provide an answer."
)

# Launch the Gradio app
iface.launch()
```

--------------------------------

TITLE: cURL Example: Reset All Namespaces
DESCRIPTION: This cURL command illustrates how to reset all namespaces of an Upstash Vector index. The 'all' query parameter is used to indicate a global reset, and the request is authenticated with a bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/reset.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/reset?all \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Query Vectors with JavaScript
DESCRIPTION: This JavaScript example shows how to query your Upstash Vector index for similar vectors. It uses the `fetch` API to send a POST request to the `/query` endpoint, specifying the query vector, `topK` results, and options to include metadata or the vectors themselves. Remember to set your Upstash Vector URL and token.

SOURCE: https://upstash.com/docs/vector/overall/llms-txt.mdx

LANGUAGE: JavaScript
CODE:
```
const UPSTASH_VECTOR_URL = process.env.UPSTASH_VECTOR_URL;
const UPSTASH_VECTOR_TOKEN = process.env.UPSTASH_VECTOR_TOKEN;

async function queryVectors() {
  const queryVector = [0.1, 0.2, 0.3, 0.4];
  const topK = 3;

  try {
    const response = await fetch(`${UPSTASH_VECTOR_URL}/query`, {
      method: 'POST',
      headers: {
        'Authorization': `Bearer ${UPSTASH_VECTOR_TOKEN}`,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        vector: queryVector,
        topK: topK,
        includeMetadata: true,
        includeVectors: false
      })
    });

    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }

    const data = await response.json();
    console.log('Query results:', data);
  } catch (error) {
    console.error('Error querying vectors:', error);
  }
}

queryVectors();
```

--------------------------------

TITLE: Deploy Gradio App with Public Link
DESCRIPTION: To make your Gradio application publicly accessible, set the `share` parameter to `True` when calling the `launch()` method. This generates a temporary public URL that expires after 72 hours. For permanent hosting and GPU upgrades, consider deploying to Hugging Face Spaces using `gradio deploy`.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: Python
CODE:
```
import gradio as gr

def greet(name):
    return "Hello " + name + "!"

if __name__ == "__main__":
    demo = gr.Interface(fn=greet, inputs="text", outputs="text")
    demo.launch(share=True)
```

--------------------------------

TITLE: Python: Range Query with ID Prefix
DESCRIPTION: Illustrates how to use the `prefix` parameter in the `range` method to retrieve vectors whose IDs start with a specific string. This is useful for filtering vectors based on a naming convention.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/range.mdx

LANGUAGE: python
CODE:
```
index.range(prefix="id-")
```

--------------------------------

TITLE: Python: Scan Entire Upstash Vector Index
DESCRIPTION: Provides a Python example for iterating through and scanning the entire Upstash Vector index using the `range` method with cursor pagination. It continuously fetches batches of vectors until no more results are available.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/range.mdx

LANGUAGE: python
CODE:
```
res = index.range(cursor="", limit=5)
print(res.vectors)

while res.next_cursor != "":
    res = index.range(cursor=res.next_cursor, limit=10)
    print(res.vectors)
```

--------------------------------

TITLE: Update Data and Metadata in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to update an existing entry by providing new data for re-embedding or by updating only its metadata. The first example shows updating the data string, while the second shows updating only the metadata for an existing ID.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert({
	id: "1234",
	data: "Upstash product",
	metadata: {
		title: "Redis"
	}
})

await index.upsert({
	id: "1234",
	metadata: {
		title: "QStash"
	}
})
```

--------------------------------

TITLE: Python: Initialize Upstash Vector Store with OpenAI Embeddings
DESCRIPTION: This snippet shows how to configure the UpstashVectorStore to use OpenAI's embeddings instead of the default. By setting 'embedding=OpenAIEmbeddings()', you leverage OpenAI's powerful language models for generating vector representations of your documents, potentially enhancing search accuracy. Ensure 'langchain_openai' is installed.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
from langchain_openai import OpenAIEmbeddings
store = UpstashVectorStore(embedding=OpenAIEmbeddings())
```

--------------------------------

TITLE: Example Upstash Vector Query API Response (JSON)
DESCRIPTION: This JSON snippet provides an example of a successful response (HTTP 200 OK) from the Upstash Vector query API. It shows the 'result' array containing objects for each matched vector, including their 'id', 'score', and optionally 'metadata'. The score indicates similarity, with higher values meaning more similarity.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query.mdx

LANGUAGE: json
CODE:
```
{
    "result": [
        {
            "id": "id-0",
            "score": 1.0,
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1",
            "score": 0.99996454
        }
    ]
}
```

--------------------------------

TITLE: Delete Vectors with cURL
DESCRIPTION: This cURL example demonstrates how to delete vectors from an Upstash Vector index by providing an array of vector IDs. It uses the DELETE HTTP method and requires a Bearer token for authorization. The example targets the default namespace.

SOURCE: https://upstash.com/docs/vector/api/endpoints/delete.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/delete \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": [ "id-0", "id-1" ] }'
```

--------------------------------

TITLE: Upsert Vectors with Upstash Vector Go SDK
DESCRIPTION: This example shows how to upsert (insert or update) multiple vectors into the Upstash Vector database using the Go SDK. Each vector requires an ID, a slice of float32 for its data, and optional metadata. This operation is asynchronous and returns a response indicating success or failure.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: Go
CODE:
```
package main

import (
	"context"
	"fmt"
	"os"

	vector "github.com/upstash/vector-go/sdk"
)

func main() {
	client, err := vector.NewClient(
		vector.WithUrl(os.Getenv("UPSTASH_VECTOR_REST_URL")),
		vector.WithToken(os.Getenv("UPSTASH_VECTOR_REST_TOKEN")),
	)
		if err != nil {
			fmt.Printf("Error creating client: %v\n", err)
			return
		}

	resp, err := client.Upsert(context.Background(), []vector.Vector{
		{
			ID:    "1",
			Vector: []float32{0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8},
			Metadata: map[string]string{"genre": "science-fiction"},
		},
		{
			ID:    "2",
			Vector: []float32{0.8, 0.7, 0.6, 0.5, 0.4, 0.3, 0.2, 0.1},
			Metadata: map[string]string{"genre": "fantasy"},
		},
	})
		if err != nil {
			fmt.Printf("Error upserting vectors: %v\n", err)
			return
		}
	
	fmt.Printf("Upsert response: %+v\n", resp)
}
```

--------------------------------

TITLE: PHP: Fetch Upstash Vector Namespace Information
DESCRIPTION: This snippet demonstrates how to retrieve information about default or specific namespaces within your Upstash Vector index. It shows how to use the `getNamespaceInfo()` method directly on the index client or on a specific namespace instance to get an `Upstash\Vector\NamespaceInfo` object.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/info.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

// Fetch the information of the default namespace.
$defaultNamespaceInfo = $index->getNamespaceInfo();

// Fetch the information on a specific namespace.
$myNamespaceInfo = $index->namespace('my-namespace')->getNamespaceInfo();
```

--------------------------------

TITLE: Query Upstash Vector Using Data String in TypeScript
DESCRIPTION: This TypeScript example illustrates how to perform a query on an Upstash Vector index by providing a data string. It demonstrates how to configure the query to include vectors and metadata, set the topK limit, and apply a filter. The expected output format of the query results is also shown.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/query.mdx

LANGUAGE: typescript
CODE:
```
const results = await index.query({
  data: "Movie about an adventure of a hobbit in a fantasy world.",
  includeVectors: true,
  includeMetadata: true,
  topK: 1,
  filter: "genre = 'fantasy' and title = 'Lord of the Rings'",
});
/*
[
  {
    id: "1234",
    vector: [0.1, 0.2, 0.3, 0.4, 0.5],
    score: 0.9999999,
    metadata: {
      title: "Lord of The Rings",
      genre: "fantasy",
      category: "classic",
    },
  }
]
*/
```

--------------------------------

TITLE: JSON Response: Successful Resumable Query End
DESCRIPTION: This JSON snippet shows an example of a successful response after ending a resumable query. A '200 OK' status indicates that the query was successfully terminated.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/stop.mdx

LANGUAGE: json
CODE:
```
{
  "result": "Success"
}
```

--------------------------------

TITLE: Run Tests for Upstash Vector Project with Bun
DESCRIPTION: This command executes all tests for the Upstash Vector project. Before running, ensure all necessary environment variables are set up, especially those related to the Upstash Vector database. Tests validate the functionality and prevent regressions.

SOURCE: https://upstash.com/docs/vector/sdks/ts/contributing.mdx

LANGUAGE: bash
CODE:
```
bun run test
```

--------------------------------

TITLE: Execute Upstash Vector Namespaced Data Query with cURL
DESCRIPTION: This cURL example shows how to query data within a specific namespace in Upstash Vector. The request is similar to a standard data query but targets the '/query-data/ns' endpoint.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: sh
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "data": "What is Upstash?", "topK": 2, "includeMetadata": true }'
```

--------------------------------

TITLE: cURL Example: Reset Default Namespace
DESCRIPTION: This cURL command demonstrates how to reset the default namespace of an Upstash Vector index. It sends a DELETE request to the /reset endpoint, authenticating with a bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/reset.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/reset \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Upsert Multiple Data with cURL
DESCRIPTION: This cURL example demonstrates how to upsert multiple raw text data entries into the default namespace of an Upstash Vector index. It includes IDs, data, and optional metadata for each entry.

SOURCE: https://upstash.com/docs/vector/api/endpoints/upsert-data.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[ \
    { "id": "id-0", "data": "Upstash is a serverless data platform.", "metadata": { "link": "upstash.com" } }, \
    { "id": "id-1", "data": "Upstash Vector is a serverless vector database." }\
  ]'
```

--------------------------------

TITLE: Configure Environment Variables for OpenAI and Upstash Vector
DESCRIPTION: This snippet shows the required environment variables to be set in your '.env' file. These variables include your OpenAI API key for generating responses and embeddings, and your Upstash Vector REST URL and token for database access. Replace the placeholder values with your actual credentials.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: Bash
CODE:
```
OPENAI_API_KEY=your_openai_api_key
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
```

--------------------------------

TITLE: List Upstash Vector Namespaces with cURL
DESCRIPTION: This cURL command demonstrates how to call the Upstash Vector API to list namespaces. It sends a GET request to the /list-namespaces endpoint and requires an Authorization header with a Bearer token for authentication. Replace $UPSTASH_VECTOR_REST_URL and $UPSTASH_VECTOR_REST_TOKEN with your actual values.

SOURCE: https://upstash.com/docs/vector/api/endpoints/list-namespaces.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/list-namespaces \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Successful Update Response Example
DESCRIPTION: This JSON snippet illustrates a successful response from the update operation, indicating that a vector was updated. The 'updated' field will be '1' if the update was successful.

SOURCE: https://upstash.com/docs/vector/api/endpoints/update.mdx

LANGUAGE: json
CODE:
```
{
    "result": {
        "updated": 1
    }
}
```

--------------------------------

TITLE: Update Vector Metadata in TypeScript
DESCRIPTION: This TypeScript example illustrates how to update an existing vector's metadata using the upsert method. By providing an existing ID and new metadata, the vector's metadata will be updated without changing its vector data. The second example shows updating metadata using the dedicated 'update' method.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert({
	id: "1234",
	vector: [0.1, 0.2, 0.3, 0.4, 0.5],
	metadata: {
		title: "Redis"
	}
})

await index.update({
	id: "1234",
	metadata: {
		title: "QStash"
	}
})
```

--------------------------------

TITLE: Upstash Vector Go SDK API Reference
DESCRIPTION: This section provides a reference for the core components and methods of the Upstash Vector Go SDK. It details the `Client` struct, its constructor `NewClient`, and key methods like `Upsert`, `Fetch`, `Delete`, and `Query`, along with their parameters and return types.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: APIDOC
CODE:
```
type Client struct {
    // Internal fields for HTTP client and configuration
}

func NewClient(opts ...ClientOption) (*Client, error)
- Description: Creates a new Upstash Vector client.
- Parameters:
    - opts ...ClientOption: Functional options to configure the client (e.g., WithUrl, WithToken).
- Returns:
    - *Client: A pointer to the initialized client.
    - error: An error if client creation fails.

func (c *Client) Upsert(ctx context.Context, vectors []Vector) (*UpsertResponse, error)
- Description: Inserts or updates multiple vectors in the database.
- Parameters:
    - ctx context.Context: The context for the request.
    - vectors []Vector: A slice of Vector structs to upsert.
- Returns:
    - *UpsertResponse: Response indicating success.
    - error: An error if the operation fails.

func (c *Client) Fetch(ctx context.Context, ids []string) ([]Vector, error)
- Description: Retrieves vectors by their IDs.
- Parameters:
    - ctx context.Context: The context for the request.
    - ids []string: A slice of vector IDs to fetch.
- Returns:
    - []Vector: A slice of fetched Vector structs.
    - error: An error if the operation fails.

func (c *Client) Delete(ctx context.Context, ids []string) (*DeleteResponse, error)
- Description: Deletes vectors by their IDs.
- Parameters:
    - ctx context.Context: The context for the request.
    - ids []string: A slice of vector IDs to delete.
- Returns:
    - *DeleteResponse: Response indicating success.
    - error: An error if the operation fails.

func (c *Client) Query(ctx context.Context, req QueryRequest) ([]QueryResult, error)
- Description: Performs a similarity search against the database.
- Parameters:
    - ctx context.Context: The context for the request.
    - req QueryRequest: The query request containing vector, topK, and optional filters.
- Returns:
    - []QueryResult: A slice of query results, each with ID, score, and metadata.
    - error: An error if the operation fails.

type Vector struct {
    ID       string            `json:"id"`
    Vector   []float32         `json:"vector"`
    Metadata map[string]string `json:"metadata,omitempty"`
}

type QueryRequest struct {
    Vector          []float32         `json:"vector"`
    TopK            int               `json:"topK"`
    IncludeMetadata bool              `json:"includeMetadata,omitempty"`
    Filter          string            `json:"filter,omitempty"`
}

type QueryResult struct {
    ID       string            `json:"id"`
    Score    float32           `json:"score"`
    Vector   []float32         `json:"vector,omitempty"`
    Metadata map[string]string `json:"metadata,omitempty"`
}
```

--------------------------------

TITLE: Fetch Vectors by ID Prefix in TypeScript
DESCRIPTION: This snippet shows how to fetch vectors using an ID prefix. All vectors whose IDs start with the specified prefix will be returned. For large datasets, consider using the 'range' command for pagination.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/fetch.mdx

LANGUAGE: typescript
CODE:
```
await index.fetch({ prefix: "test-" });
// [{ id: "test-1" }, { id: "test-2" }, { id: "test-3" }]
```

--------------------------------

TITLE: Initialize Upstash Vector Client with Configuration Object
DESCRIPTION: Initialize the Upstash Vector client by passing a configuration object containing the URL and token directly to the constructor. This method is useful for applications that need to manage connections to multiple Upstash projects.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index({
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>"
});
```

--------------------------------

TITLE: Curl Example: Upsert Multiple Vectors
DESCRIPTION: This curl command demonstrates how to upsert multiple vectors into the default namespace. It includes vector IDs, dense vector values, and optional metadata. Replace `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` with your actual credentials.

SOURCE: https://upstash.com/docs/vector/api/endpoints/upsert.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[ 
    { "id": "id-0", "vector": [0.1, 0.2], "metadata": { "link": "upstash.com" } }, 
    { "id": "id-1", "vector": [0.2, 0.3] }
  ]'
```

--------------------------------

TITLE: Perform Semantic Search using Upstash Vector in Python
DESCRIPTION: This Python script demonstrates how to perform semantic search using Upstash Vector. It initializes the index, resets it, upserts example documents (which are automatically embedded), waits for indexing, and then queries the index to find the top 3 semantically similar documents to a given query, including their metadata.

SOURCE: https://upstash.com/docs/vector/tutorials/semantic_search.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import Index
from dotenv import load_dotenv
import time

# Load environment variables from a .env file
load_dotenv()

# Initialize the index from environment variables (URL and token)
index = Index.from_env()

# Example documents to be indexed
documents = [
    {"id": "1", "text": "Python is a popular programming language."},
    {"id": "2", "text": "Machine learning enables computers to learn from data."},
    {"id": "3", "text": "Upstash provides low-latency database solutions."},
    {"id": "4", "text": "Semantic search is a technique for understanding the meaning of queries."},
    {"id": "5", "text": "Cloud computing allows for scalable and flexible resource management."}
]

# Reset the index to remove previous data
index.reset()

# Upsert documents into Upstash (embeddings are generated automatically)
for doc in documents:
    index.upsert(
        vectors=[
            (doc["id"], doc["text"], {"text": doc["text"]})
        ]
    )
    print(f"Document {doc['id']} inserted.")

# Wait for the documents to be indexed
time.sleep(1)

# Search for documents similar to the query
query = "What is Python?"
results = index.query(data=query, top_k=3, include_metadata=True)

# Display search results
print("Search Results:")
for result in results:
    print(f"ID: {result.id}")
    print(f"Score: {result.score:.4f}")
    print(f"Metadata: {result.metadata}")
    print("-" * 40)  # Separator line between results
```

--------------------------------

TITLE: Filter Array Elements by Index in SQL
DESCRIPTION: Individual array elements can be filtered by referencing them with the '[]' accessor using zero-based indexing. This example matches entries where the first major industry is 'Tourism'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.major_industries[0] = 'Tourism'
```

--------------------------------

TITLE: Python: Create a Synchronous Resumable Query
DESCRIPTION: Create a resumable query instance using the `resumable_query` method of the `Index` class. This allows you to define the query parameters such as the reference vector, top_k results, and inclusion of metadata or vectors. This query can then be started and resumed to fetch results in batches.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
query = index.resumable_query(
    vector=[0.1, 0.2],  # or use 'data' parameter for text-based queries
    top_k=2,
    include_metadata=True,
    include_vectors=True,
    namespace="your_namespace"
)
```

--------------------------------

TITLE: Initialize Upstash Vector Client in Go
DESCRIPTION: This snippet demonstrates how to initialize a new Upstash Vector client in Go. It requires the Upstash Vector URL and token, typically obtained from your Upstash console. The client is essential for performing any operations against the vector database.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: Go
CODE:
```
package main

import (
	"context"
	"fmt"
	"os"

	vector "github.com/upstash/vector-go/sdk"
)

func main() {
	client, err := vector.NewClient(
		vector.WithUrl(os.Getenv("UPSTASH_VECTOR_REST_URL")),
		vector.WithToken(os.Getenv("UPSTASH_VECTOR_REST_TOKEN")),
	)
		if err != nil {
			fmt.Printf("Error creating client: %v\n", err)
			return
		}
	fmt.Println("Upstash Vector client initialized successfully.")
}
```

--------------------------------

TITLE: Update Vector Metadata with cURL
DESCRIPTION: This cURL example demonstrates how to update only the metadata of a vector with a specific ID in the default namespace. It sends a POST request with the vector ID and the new metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/update.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/update \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-1", "metadata": { "link": "upstash.com" } }'
```

--------------------------------

TITLE: Curl Example for Deleting Upstash Vector Namespace
DESCRIPTION: This curl command demonstrates how to send a DELETE request to remove a namespace from your Upstash Vector index. Replace `$UPSTASH_VECTOR_REST_URL` with your endpoint and `$UPSTASH_VECTOR_REST_TOKEN` with your actual Bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/delete-namespace.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/delete-namespace/ns \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Configure Upstash Vector Environment Variables
DESCRIPTION: Set up environment variables for Upstash Vector by adding the REST URL and Token to a .env file. These credentials are required to connect to your Upstash Vector index.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
```

--------------------------------

TITLE: Group Boolean Operators with Parentheses in SQL
DESCRIPTION: Parentheses can be used to group boolean operators and control their precedence. This example matches entries where the country is 'Turkey' AND (the population is greater than 10,000,000 OR 'is_capital' is false).

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
country = 'Turkey' AND (population > 10000000 OR is_capital = false)
```

--------------------------------

TITLE: Combine Filters with AND Boolean Operator in SQL
DESCRIPTION: Boolean operators like AND can combine multiple filters to form compound conditions. This example matches entries where the country is 'Turkey' AND the population is greater than 10,000,000.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
country = 'Turkey' AND population > 10000000
```

--------------------------------

TITLE: Filter by Absence of Field with HAS NOT FIELD Operator in SQL
DESCRIPTION: The HAS NOT FIELD operator filters keys that do not possess the specified JSON field. This example matches entries that do not have the 'geography.coordinates.longitude' field.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
HAS NOT FIELD geography.coordinates.longitude
```

--------------------------------

TITLE: Handle Vector Not Found in TypeScript Fetch
DESCRIPTION: This example illustrates the behavior when one or more specified vector IDs are not found during a fetch operation. The result array will contain 'null' for each ID that does not correspond to an existing vector.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/fetch.mdx

LANGUAGE: typescript
CODE:
```
await index.fetch(["2", "3"]);
// [{ id: "2" }, null]
```

--------------------------------

TITLE: Initialize Hugging Face Embeddings and Upstash Vector Store
DESCRIPTION: Load environment variables and initialize the Hugging Face embeddings model (sentence-transformers/all-mpnet-base-v2) and the Upstash Vector store. The UpstashVectorStore automatically uses credentials from environment variables.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: python
CODE:
```
# Load environment variables for API keys and Upstash configuration
from dotenv import load_dotenv
import os
load_dotenv()

# Import required libraries
from langchain_huggingface.embeddings import HuggingFaceEmbeddings
from langchain_community.vectorstores.upstash import UpstashVectorStore

# Initialize Hugging Face embeddings model
embeddings = HuggingFaceEmbeddings(model_name="sentence-transformers/all-mpnet-base-v2")

# Set up Upstash Vector Store (automatically uses the environment variables)
vector_store = UpstashVectorStore(embedding=embeddings)
```

--------------------------------

TITLE: TypeScript: Perform Resumable Query with Vector
DESCRIPTION: Demonstrates how to perform a resumable query using a vector with Upstash Vector. It shows how to retrieve initial results, fetch subsequent batches, and stop the query to release resources, including examples of the output structure.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: typescript
CODE:
```
const { result, fetchNext, stop } = await index.resumableQuery({
  maxIdle: 3600,
  topK: 50,
  vector: [0, 1, 2, ..., 383], // 384-dimensional vector
  includeMetadata: true,
  includeVectors: true,
});

console.log(result);
/*
[
  {
    id: '6345',
    score: 1.00000012,
    vector: [0, 1, 2, ..., 383],
    metadata: {
      sentence: "Upstash is great."
    }
  },
  // ... more results
]
*/

const nextBatch = await fetchNext(5); // Fetch next 5 results
console.log(nextBatch);

await stop(); // Stop the resumable query
```

--------------------------------

TITLE: Query Upstash Vector and Include Metadata
DESCRIPTION: This example demonstrates how to query an Upstash Vector index and explicitly request the inclusion of associated metadata in the results. This is useful for retrieving contextual information along with the vector matches. Ensure your Upstash Vector REST URL and token are set.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    [0.9215, 0.3897],
    top_k=5,
    include_metadata=True,
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({
  vector: [0.9215, 0.3897],
  topK: 5,
  includeMetadata: true,
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.Query(vector.Query{
		Vector:          []float32{0.9215, 0.3897},
		TopK:            5,
		IncludeMetadata: true,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
  vector: [0.9215, 0.3897],
  topK: 5,
  includeMetadata: true,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
   "vector":[0.9215,0.3897],
   "topK" : 5,
   "includeMetadata": true
}'
```

--------------------------------

TITLE: Python: Fetch Upstash Vectors by ID Prefix
DESCRIPTION: This Python code shows how to fetch all vectors whose IDs start with a specified prefix from an Upstash Vector index. This is useful for retrieving groups of related vectors without knowing their exact IDs. For large datasets, consider using the 'range' command for pagination to prevent timeouts.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/fetch.mdx

LANGUAGE: python
CODE:
```
index.fetch(prefix="id-")
```

--------------------------------

TITLE: Filter by Presence of Field with HAS FIELD Operator in SQL
DESCRIPTION: The HAS FIELD operator filters keys that possess the specified JSON field. This example matches entries that have the 'geography.coordinates' field.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
HAS FIELD geography.coordinates
```

--------------------------------

TITLE: TypeScript: Perform Resumable Query with Data
DESCRIPTION: Illustrates how to execute a resumable query using raw data instead of a vector with Upstash Vector. This example demonstrates fetching initial results, retrieving additional batches, and properly stopping the query, along with expected output.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: typescript
CODE:
```
const { result, fetchNext, stop } = await index.resumableQuery({
  maxIdle: 3600,
  topK: 50,
  data: "lord of the rings",
  includeMetadata: true,
  includeData: true,
});

console.log(result);
/*
[
  {
    id: '6345',
    score: 1.00000012,
    data: "hobbit",
    metadata: {
      sentence: "Upstash is great."
    }
  },
  // ... more results
]
*/

const nextBatch = await fetchNext(5); // Fetch next 5 results
console.log(nextBatch);

await stop(); // Stop the resumable query
```

--------------------------------

TITLE: Curl Example: End Upstash Vector Resumable Query
DESCRIPTION: This curl command demonstrates how to send a POST request to end a resumable query. It requires setting the Authorization header with a Bearer token and providing the query's UUID in the request body.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/stop.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query-end \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "uuid": "550e8400-e29b-41d4-a716-446655440000"
  }'
```

--------------------------------

TITLE: cURL Example: Reset Specific Namespace
DESCRIPTION: This cURL command shows how to reset a specific namespace (e.g., 'ns') within an Upstash Vector index. The namespace is specified in the request path, and the request is authenticated with a bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/reset.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/reset/ns \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: TypeScript: Perform Resumable Query with Metadata Type
DESCRIPTION: Shows how to perform a resumable query with a specific metadata type definition in TypeScript. This example demonstrates type-safe access to metadata fields after a query, including filtering capabilities and proper query termination.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: typescript
CODE:
```
type Metadata = {
  title: string,
  genre: 'sci-fi' | 'fantasy' | 'horror' | 'action'
}

const { result, fetchNext, stop } = await index.resumableQuery<Metadata>({
  vector: [
    ... // query embedding
  ],
  includeMetadata: true,
  topK: 1,
  filter: "genre = 'fantasy' and title = 'Lord of the Rings'",
  maxIdle: 3600,
})

if (result[0].metadata) {
  // Since we passed the Metadata type parameter above,
  // we can interact with metadata fields without having to
  // do any typecasting.
  const { title, genre } = result[0].metadata;
  console.log(`The best match in fantasy was ${title}`)
}

await stop();
```

--------------------------------

TITLE: Review Upstash Vector Successful Query Response (JSON)
DESCRIPTION: This JSON example shows a typical successful response from an Upstash Vector data query. It includes a 'result' array containing objects, each with an 'id', 'score', and optionally 'metadata' for the matched vectors.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: json
CODE:
```
{
    "result": [
        {
            "id": "id-0",
            "score": 1.0,
            "metadata": {
                "link": "upstash.com"
            }
        },
        {
            "id": "id-1",
            "score": 0.99996454
        }
    ]
}
```

--------------------------------

TITLE: Upsert Single Data to Specific Namespace with cURL
DESCRIPTION: This cURL example shows how to upsert a single raw text data entry into a specified namespace ('ns') within an Upstash Vector index. It includes an ID, data, and optional metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/upsert-data.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert-data/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-2", "data": "Upstash is a serverless data platform.", "metadata": { "link": "upstash.com" } }'
```

--------------------------------

TITLE: Python: Reset All Namespaces in Upstash Vector
DESCRIPTION: This example illustrates how to reset all namespaces within an Upstash Vector index. This operation will clear all vectors and metadata across all namespaces associated with the index. Use with caution as it affects all data.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/reset.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
index = Index.from_env()

index.reset(all=True)
```

--------------------------------

TITLE: Start a Resumable Query with Upstash Vector
DESCRIPTION: Initiate a resumable query to fetch the first batch of approximate nearest neighbors. This operation returns the initial results and a unique handle to continue the query. Filters and inclusion flags (metadata, data) set here apply for the entire query duration.

SOURCE: https://upstash.com/docs/vector/features/resumablequery.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

result, handle = index.resumable_query(
    vector=[0.1, 0.2],
    top_k=2,
    include_metadata=True,
)

# first batch of the results
for r in result:
    print(r)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
});

const { result, fetchNext, stop } = await index.resumableQuery({
  vector: [0.1, 0.2],
  topK: 2,
  includeMetadata: true,
});

// first batch of the results
for (let r of result) {
  console.log(r);
}
```

LANGUAGE: go
CODE:
```
package main

import (
	"fmt"
	"log"

	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, handle, err := index.ResumableQuery(vector.ResumableQuery{
		Vector:          []float32{0.1, 0.2},
		TopK:            2,
		IncludeMetadata: true,
	})
	if err != nil {
		log.Fatal(err)
	}

	defer handle.Close()

	// first batch of the results
	for _, score := range scores {
		fmt.Printf("%+v\n", score)
	}
}
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "vector": [0.1, 0.2],
    "topK": 2,
    "includeMetadata": true
  }'
```

--------------------------------

TITLE: Query Upstash Vector Using a Vector Embedding in TypeScript
DESCRIPTION: This TypeScript code snippet demonstrates how to query an Upstash Vector index using a vector embedding. It shows how to specify the topK results, include metadata, and include the vectors in the response. The example also illustrates the expected structure of the returned results.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/query.mdx

LANGUAGE: typescript
CODE:
```
await index.query({
  topK: 2,
  vector: [ ... ],
  includeMetadata: true,
  includeVectors: true
}, { namespace: "my-namespace" })
/*
[
  {
    id: '6345',
    score: 0.85,
    vector: [],
    metadata: {
      sentence: "Upstash is great."
    }
  },
  {
    id: '1233',
    score: 0.75,
    vector: [],
    metadata: undefined
  },
]
*/
```

--------------------------------

TITLE: Perform Range Query on Upstash Vector
DESCRIPTION: This snippet illustrates how to perform a range query on the Upstash Vector index to retrieve vectors starting from a specific cursor with a defined limit. It requires an initialized Upstash Vector index. The output will be a list of vectors within the specified range, optionally including their metadata.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.range(
    cursor="0",
    limit=3,
    include_metadata=True,
)
```

LANGUAGE: JavaScript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.range({
  cursor: "0",
  limit: 3,
  includeMetadata: true,
})
```

LANGUAGE: Go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.Range(vector.Range{
		Cursor:          "0",
		Limit:           3,
		IncludeMetadata: true,
	})
}
```

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorRange;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->range(new VectorRange(
  limit: 3,
  includeMetadata: true,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/range \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "cursor" : "0",  "limit" : 3, "includeMetadata": true}'
```

LANGUAGE: json
CODE:
```
{
  "result": {
    "nextCursor": "4",
    "vectors": [
      { "id": "id-0", "metadata": { "url": "https://imgur.com/z9AVZLb" } },
      { "id": "id-1", "metadata": { "url": "https://imgur.com/a2nCEIt" } },
      { "id": "id-2", "metadata": { "url": "https://imgur.com/zfOPmnI" } }
    ]
  }
}
```

--------------------------------

TITLE: Upsert Multiple Vectors in TypeScript
DESCRIPTION: This TypeScript example shows how to upsert multiple vectors in a single call to the Upstash Vector index. Each vector object requires an ID and the vector array, with optional metadata. This is efficient for batch operations.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert([
  {
    id: "6789",
    vector: [0.6, 0.7, 0.8, 0.9, 0.9]
  },
  {
    id: "1234",
    vector: [0.1, 0.2, 0.3, 0.4, 0.5],
    metadata: {
      title: "Lord of The Rings",
      genre: "drama",
      category: "classic"
    }
  }
]);
```

--------------------------------

TITLE: Upsert Vectors with Namespace in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to upsert multiple vectors into a specific namespace within your Upstash Vector index. The namespace is provided as an option in the second argument of the upsert method. If not specified, the default namespace is used.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert([
  {
    id: "6789",
    vector: [0.6, 0.7, 0.8, 0.9, 0.9]
  }
], { namespace: "my-namespace" });
```

--------------------------------

TITLE: Upsert Single Vector in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to upsert a single vector into the Upstash Vector index. It includes an ID, the vector array, and optional metadata for the entry. Ensure the vector dimension matches your index configuration.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert({
  id: "1234",
  vector: [0.1, 0.2, 0.3, 0.4, 0.5],
  metadata: {
    title: "Lord of The Rings",
    genre: "drama",
    category: "classic"
  }
});
```

--------------------------------

TITLE: TypeScript: Upstash Vector Range Query with Improved Types for Metadata
DESCRIPTION: This example demonstrates how to use the 'range' method with a custom TypeScript type for metadata. By defining a 'Metadata' interface and passing it as a type parameter, developers can interact with metadata fields without explicit typecasting, improving type safety and code readability.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/range.mdx

LANGUAGE: TypeScript
CODE:
```
type Metadata = {
  title: string;
  genre: "sci-fi" | "fantasy" | "horror" | "action";
};

const responseRange = await index.range<Metadata>({
  cursor: 0,
  limit: 2,
  includeMetadata: true,
});

if (responseRange[0].metadata) {
  // Since we passed the Metadata type parameter above,
  // we can interact with metadata fields without having to
  // do any typecasting.
  const { title, genre } = results[0].metadata;
  console.log(`The best match in fantasy was ${title}`);
}
```

--------------------------------

TITLE: Review Upstash Vector Error Query Response (JSON)
DESCRIPTION: This JSON example illustrates an error response from the Upstash Vector API, specifically a 422 Unprocessable Entity error. It indicates that embedding data is not allowed for the index because it was not created with an embedding model.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: json
CODE:
```
{
    "error": "Embedding data for this index is not allowed. The index must be created with an embedding model to use it.",
    "status": 422
}
```

--------------------------------

TITLE: Retrieve Data with Upstash Vector Fetch Request
DESCRIPTION: This example shows how to perform a fetch request to Upstash Vector and include the associated data in the response. Setting `includeData` to `true` in the query options ensures that the original data points are returned along with the vector matches. This method is suitable for single or batch fetch operations.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: TypeScript
CODE:
```
import { Index } from '@upstash/vector';

const index = new Index();

async function fetchDataWithFetchRequest() {
  const results = await index.query({
    topK: 5,
    vector: [/* your vector data */],
    includeData: true,
  });

  results.forEach(item => {
    console.log(`ID: ${item.id}, Score: ${item.score}, Data: ${JSON.stringify(item.data)}`);
  });
}
```

--------------------------------

TITLE: PHP: Fetch Upstash Vector Index Information
DESCRIPTION: This snippet demonstrates how to initialize an Upstash Vector Index client and use the `getInfo()` method to retrieve comprehensive details about your index. The method returns an `Upstash\Vector\IndexInfo` instance containing metadata like vector counts, index size, dimensions, and similarity function.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/info.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$info = $index->getInfo();
```

--------------------------------

TITLE: Python: Reset Default Namespace in Upstash Vector
DESCRIPTION: This example demonstrates how to reset the default namespace of an Upstash Vector index. It clears all vectors and metadata not associated with a specific namespace. Ensure your environment variables are configured for index access.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/reset.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
index = Index.from_env()

index.reset()
```

--------------------------------

TITLE: Python: Fetch a Single Upstash Vector by ID
DESCRIPTION: This Python example illustrates how to retrieve a single vector from an Upstash Vector index by providing its unique identifier. This is a simplified usage of the 'fetch' method when only one specific vector is needed. The method returns the information for the requested vector.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/fetch.mdx

LANGUAGE: python
CODE:
```
index.fetch("id-4")
```

--------------------------------

TITLE: Resume Upstash Vector Query with cURL
DESCRIPTION: This cURL example demonstrates how to make a POST request to the Upstash Vector API to resume a resumable query. It sends the 'uuid' obtained from a previous query and the 'additionalK' parameter to specify the number of extra results to retrieve. Ensure you replace '$UPSTASH_VECTOR_REST_URL' and '$UPSTASH_VECTOR_REST_TOKEN' with your actual endpoint and bearer token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/resume.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query-next \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "uuid": "550e8400-e29b-41d4-a716-446655440000",
    "additionalK": 2
  }'
```

--------------------------------

TITLE: Filter Values with NOT IN Operator in SQL
DESCRIPTION: The NOT IN operator filters keys whose value is not equal to any of the provided literals. It is applicable to string, number, and boolean values. This example matches currencies that are not 'USD' or 'EUR'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.currency NOT IN ('USD', 'EUR')
```

--------------------------------

TITLE: Upsert Single Data for Embedding in TypeScript
DESCRIPTION: This TypeScript example demonstrates how to upsert a single piece of raw data, allowing Upstash Embedding to generate the vector. It requires an ID and the data string, with optional metadata. This is useful when you don't pre-compute embeddings.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert({
  id: "1234",
  data: "'The Lord of the Rings' follows Frodo Baggins and his allies on a quest to destroy a powerful ring and save Middle-earth from the dark lord Sauron.",
  metadata: {
    title: "Lord of The Rings",
    genre: "drama",
    category: "classic"
  }
});
```

--------------------------------

TITLE: Resume a Resumable Query with Upstash Vector
DESCRIPTION: Continue a previously initiated resumable query using the provided handle. This allows fetching the next batch of similar vectors, starting from the last response. You can call this method multiple times to iterate through the entire index.

SOURCE: https://upstash.com/docs/vector/features/resumablequery.mdx

LANGUAGE: python
CODE:
```
# next batch of the results
next_result = handle.fetch_next(
    additional_k=3,
)

for r in next_result:
    print(r)

# it is possible to call fetch_next more than once
next_result = handle.fetch_next(
    additional_k=5,
)

for r in next_result:
    print(r)
```

LANGUAGE: javascript
CODE:
```
// next batch of the results
let nextResult = await fetchNext(3);

for (let r of nextResult) {
  console.log(r);
}

// it is possible to call fetch_next more than once
nextResult = await fetchNext(3);

for (let r of nextResult) {
  console.log(r);
}
```

LANGUAGE: go
CODE:
```
// next batch of the results
scores, err = handle.Next(vector.ResumableQueryNext{
	AdditionalK: 3,
})
if err != nil {
	log.Fatal(err)
}

for _, score := range scores {
	fmt.Printf("%+v\n", score)
}

// it is possible to call Next more than once
scores, err = handle.Next(vector.ResumableQueryNext{
	AdditionalK: 5,
})
if err != nil {
	log.Fatal(err)
}

for _, score := range scores {
	fmt.Printf("%+v\n", score)
}
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query-next \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "uuid": "550e8400-e29b-41d4-a716-446655440000",
    "additionalK": 3
  }'
```

--------------------------------

TITLE: Upsert Dense and Sparse Vectors in Upstash Vector
DESCRIPTION: This code demonstrates how to upsert both dense and sparse vectors into an Upstash Vector index. For hybrid indexes, both dense and sparse vector components are required. The examples show how to initialize the Upstash Vector client and then use the `upsert` method to add vectors with their respective dense and sparse representations.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index, Vector
from upstash_vector.types import SparseVector

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    vectors=[
        Vector(id="id-0", vector=[0.1, 0.5], sparse_vector=SparseVector([1, 2], [0.1, 0.2])),
        Vector(id="id-1", vector=[0.3, 0.7], sparse_vector=SparseVector([123, 44232], [0.5, 0.4])),
    ]
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.upsert([{
  id: 'id-0',
  vector: [0.1, 0.5],
  sparseVector: {
    indices: [2, 3],
    values: [0.13, 0.87],
  },
}])
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	err := index.UpsertMany([]vector.Upsert{
		{
			Id:     "id-0",
			Vector: []float32{0.1, 0.5},
			SparseVector: &vector.SparseVector{
				Indices: []int32{1, 2},
				Values:  []float32{0.1, 0.2},
			},
		},
		{
			Id:     "id-1",
			Vector: []float32{0.3, 0.7},
			SparseVector: &vector.SparseVector{
				Indices: []int32{123, 44232},
				Values:  []float32{0.5, 0.4},
			},
		},
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;
use Upstash\Vector\SparseVector;

use function Upstash\Vector\createRandomVector;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->upsert(new VectorUpsert(
  id: 'id-0',
  vector: createRandomVector(384),
  sparseVector: new SparseVector(
    indices: [1, 2, 3],
    values: [5, 6, 7],
  ),
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[
    {"id": "id-0", "vector": [0.1, 0.5], "sparseVector": {"indices": [1, 2], "values": [0.1, 0.2]}},
    {"id": "id-1", "vector": [0.3, 0.7], "sparseVector": {"indices": [123, 44232], "values": [0.5, 0.4]}}
  ]'
```

--------------------------------

TITLE: Upsert Multiple Data for Embedding in TypeScript
DESCRIPTION: This TypeScript example shows how to upsert multiple pieces of raw data for embedding in a single call. Each data object requires an ID and the data string, with optional metadata. This streamlines the process of adding content for vectorization.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: typescript
CODE:
```
await index.upsert([
  {
    id: "6789",
    data: "'Harry Potter' follows the journey of a young wizard, Harry Potter, as he attends Hogwarts School of Witchcraft and Wizardry, forms deep friendships, and confronts the dark wizard Voldemort, who seeks immortality and domination over the magical world."
  },
  {
    id: "1234",
    data: "'The Lord of the Rings' follows Frodo Baggins and his allies on a quest to destroy a powerful ring and save Middle-earth from the dark lord Sauron.",
    metadata: {
      title: "Lord of The Rings",
      genre: "drama",
      category: "classic"
    }
  }
]);
```

--------------------------------

TITLE: Initialize Upstash Vector Store with LangChain in Python
DESCRIPTION: Load environment variables and initialize an UpstashVectorStore instance. The 'embedding=True' parameter ensures that embeddings are automatically generated by Upstash for documents added to the store.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
from dotenv import load_dotenv
from langchain_community.vectorstores.upstash import UpstashVectorStore

load_dotenv()

# Create a vector store instance where embeddings are generated by Upstash
store = UpstashVectorStore(embedding=True)
```

--------------------------------

TITLE: Update Vector Value in a Specific Namespace with cURL
DESCRIPTION: This cURL example shows how to update the vector value for a given ID within a specified namespace. It sends a POST request including the vector ID and the new vector array.

SOURCE: https://upstash.com/docs/vector/api/endpoints/update.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/update/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-2", "vector": [0.1, 0.2] }'
```

--------------------------------

TITLE: Perform a Namespaced Upstash Vector Query using cURL
DESCRIPTION: This cURL example shows how to query a specific namespace within your Upstash Vector index. It includes the namespace in the URL path and specifies the query vector, topK results, and whether to include metadata. Ensure `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` are correctly set.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query.mdx

LANGUAGE: sh
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "vector": [0.1, 0.2], "topK": 2, "includeMetadata": true }'
```

--------------------------------

TITLE: Filter Values with IN Operator in SQL
DESCRIPTION: The IN operator filters keys whose value is equal to any of the provided literals. It is applicable to string, number, and boolean values. This example matches countries that are 'Germany', 'Turkey', or 'France'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
country IN ('Germany', 'Turkey', 'France')
```

--------------------------------

TITLE: Curl Example: Upsert Single Vector to Specific Namespace
DESCRIPTION: This curl command shows how to upsert a single vector into a specified namespace, 'ns'. It includes the vector ID, dense vector value, and metadata. Remember to replace placeholders with your actual API endpoint and token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/upsert.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "id": "id-2", "vector": [0.1, 0.2], "metadata": { "link": "upstash.com" } }'
```

--------------------------------

TITLE: Configure Upstash Vector Credentials
DESCRIPTION: Create a .env file to store your Upstash Vector REST URL and Token. These environment variables are crucial for the application to authenticate and connect to your Upstash Vector database.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
```

--------------------------------

TITLE: Python: Reset Specific Namespace in Upstash Vector
DESCRIPTION: This example shows how to reset a specific namespace within an Upstash Vector index. It targets and clears only the vectors and metadata belonging to the designated namespace. Replace 'ns' with your desired namespace name.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/reset.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
index = Index.from_env()

index.reset(namespace="ns")
```

--------------------------------

TITLE: Filter Array Elements from Back with Negative Index in SQL
DESCRIPTION: Array elements can be indexed from the back using the '#' character with negative values, where '#-1' references the last element. This example matches entries where the last major industry is 'Finance'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.major_industries[#-1] = 'Finance'
```

--------------------------------

TITLE: Filter Strings with NOT GLOB Operator in SQL
DESCRIPTION: The NOT GLOB operator filters string values that do not match a given UNIX glob pattern. It shares the same properties as the GLOB operator. This example matches city names where the first character is not 'A'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
city NOT GLOB 'A*'
```

--------------------------------

TITLE: Filter Nested Objects with Dot Accessor in SQL
DESCRIPTION: Nested object keys can be filtered by referencing them using the '.' accessor. This allows filtering at arbitrary depths. This example matches entries where the currency is not 'USD' AND the latitude is greater than or equal to 35.0.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.currency != 'USD' AND geography.coordinates.latitude >= 35.0
```

--------------------------------

TITLE: Get Upstash Vector Index Statistics (TypeScript)
DESCRIPTION: Retrieve statistics for a list of specified vector IDs from your Upstash Vector index. This operation requires an initialized Upstash Vector client instance. The method returns statistical data related to the provided vector IDs.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: TypeScript
CODE:
```
await index.stats(["id-1", "id-2", "id-3"]);
```

--------------------------------

TITLE: Upstash Vector Data Management FAQs
DESCRIPTION: This section provides answers to questions regarding data management within Upstash Vector, specifically focusing on efficient methods for uploading large datasets and managing metadata fields. It details the recommended approach for batch inserts.

SOURCE: https://upstash.com/docs/vector/help/faq.mdx

LANGUAGE: APIDOC
CODE:
```
FAQ:
- How can I upload a large dataset quickly?
  - Perform batch inserts using the 'upsert' operation, which accepts an array of vectors.
  - Recommended array size: up to 1000 vectors for efficient batch inserts.
- How can I remove a metadata field from a vector?
  - (Content not provided in original text, placeholder for future documentation)
```

--------------------------------

TITLE: Perform a Single Upstash Vector Query using cURL
DESCRIPTION: This cURL example demonstrates how to send a single query to the Upstash Vector API. It specifies the vector, the number of top results to return (topK), and requests to include metadata in the response. Replace `$UPSTASH_VECTOR_REST_URL` and `$UPSTASH_VECTOR_REST_TOKEN` with your actual API endpoint and token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query.mdx

LANGUAGE: sh
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "vector": [0.1, 0.2], "topK": 2, "includeMetadata": true }'
```

--------------------------------

TITLE: Upstash Vector Functionality FAQs
DESCRIPTION: This section addresses questions about the current and future functionalities of Upstash Vector, including support for hybrid search, metadata filtering, replication, and requirements for vector IDs during insertion. It clarifies what features are available and what is on the roadmap.

SOURCE: https://upstash.com/docs/vector/help/faq.mdx

LANGUAGE: APIDOC
CODE:
```
FAQ:
- Do you support hybrid search?
  - Not currently, but on roadmap. Approach not finalized.
- Can I filter by metadata?
  - Yes, see Metadata Filtering documentation.
- Do you support replication?
  - Not in current release, but actively working on it for upcoming release.
- If I do not specify a UUID during adding vectors, will Upstash Vector create one automatically?
  - No, ID field is required and cannot be an empty string when inserting vectors.
```

--------------------------------

TITLE: QueryCommandPayload API Reference
DESCRIPTION: This section details the `QueryCommandPayload` interface, which defines the arguments required for the query method in Upstash Vector. It includes fields for the query vector or data, the number of results to return, and options for including metadata, vectors, or data in the response, as well as filtering and weighting strategies.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/query.mdx

LANGUAGE: APIDOC
CODE:
```
interface QueryCommandPayload {
  "vector | sparseVector | data": {
    type: "number[] | SparseVector | string",
    required: true,
    description: "The query data/vector to search for in the index. Can be a direct vector, sparse vector, or data for Upstash Embedding."
  },
  topK: {
    type: "number",
    required: true,
    description: "The total number of vectors to receive as a query result, sorted by distance metric score."
  },
  includeMetadata: {
    type: "boolean",
    description: "Whether to include the metadata of the vectors in the response."
  },
  includeVectors: {
    type: "boolean",
    description: "Whether to include the vectors themselves in the response."
  },
  includeData: {
    type: "boolean",
    description: "Whether to include the data field in the response."
  },
  filter: {
    type: "string",
    description: "Metadata filtering for narrowing down query results."
  },
  weightingStrategy: {
    type: "WeightingStrategy",
    description: "For sparse vectors, the weighting strategy for matching non-zero dimension values. If not provided, no weighting is used."
  },
  fusionAlgorithm: {
    type: "FusionAlgorithm",
    description: "Fusion algorithm for combining scores from dense and sparse components of a hybrid index. Defaults to RRF."
  },
  queryMode: {
    type: "QueryMode",
    description: "Query mode for hybrid indexes with Upstash-hosted embedding models (DENSE, SPARSE, or HYBRID). Defaults to HYBRID."
  }
}
```

LANGUAGE: APIDOC
CODE:
```
interface QueryCommandOptions {
  Namespace: {
    type: "string",
    description: "Namespace to query. If not set, the default namespace is used."
  }
}
```

--------------------------------

TITLE: Python: Delete a Single Vector by ID in Upstash Vector
DESCRIPTION: This Python example illustrates how to delete a single vector from an Upstash Vector index by directly passing its identifier to the 'delete' method. This is a shorthand for deleting a single ID without explicitly using the 'ids' parameter.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/delete.mdx

LANGUAGE: python
CODE:
```
index.delete("id-4")
```

--------------------------------

TITLE: Perform a Batch Upstash Vector Query using cURL
DESCRIPTION: This cURL example illustrates how to send multiple queries in a single batch request to the Upstash Vector API. The request body is an array of query objects, each with its own vector, topK, and includeMetadata parameters. This is efficient for querying multiple vectors simultaneously. Remember to replace placeholders with your actual URL and token.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query.mdx

LANGUAGE: sh
CODE:
```
curl "$UPSTASH_VECTOR_REST_URL/query" \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[
        {
          "vector": [0.1, 0.2],
          "topK": 2,
          "includeMetadata": true
        },
        {
          "vector": [0.2, 0.3],
          "topK": 3
        }
      ]'
```

--------------------------------

TITLE: Python: Patch Vector Metadata with JSON Merge Patch
DESCRIPTION: This Python example shows how to patch a vector's metadata using the JSON Merge Patch algorithm. It uses 'MetadataUpdateMode.PATCH' to update existing fields, delete fields (by setting to None), and add new fields. This requires the 'upstash_vector.types.MetadataUpdateMode' enum.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/update.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import MetadataUpdateMode

index = Index.from_env()

updated = index.update(
    id="id2",
    metadata={
        "existing-field": "new-value",
        "existing-field-to-delete": None,
        "new-field": "new-value",
    },
    metadata_update_mode=MetadataUpdateMode.PATCH,
)

print(updated)
```

--------------------------------

TITLE: Filter Array Values with CONTAINS Operator in SQL
DESCRIPTION: The CONTAINS operator filters keys whose array value contains the specified literal. It is applicable to array values. This example matches entries where 'Tourism' is one of the major industries.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.major_industries CONTAINS 'Tourism'
```

--------------------------------

TITLE: TypeScript: Delete Upstash Vectors by Prefix
DESCRIPTION: This TypeScript code snippet shows how to delete multiple vectors from an Upstash Vector index by specifying a prefix. All vectors whose IDs start with the given prefix will be deleted. The response indicates the total number of vectors deleted.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/delete.mdx

LANGUAGE: TypeScript
CODE:
```
const response = await index.delete({
  prefix: "article_",
});
// { deleted: 3 }
```

--------------------------------

TITLE: Retrieve Upstash Vector Index Info API
DESCRIPTION: This API endpoint returns various details about the Upstash Vector index. It provides insights into the number of ready and pending vectors, total index size, vector dimensions, similarity function, and index type. It also includes detailed configurations for dense and sparse indexes, and vector counts per namespace.

SOURCE: https://upstash.com/docs/vector/api/endpoints/info.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://{endpoint}/info
AuthMethod: bearer

Request:
  No additional data required.

Response:
  vectorCount: number (required)
    The number of vectors in the index that are ready to use, across all namespaces.
  pendingVectorCount: number (required)
    The number of vectors in the index that are still processing and not ready to use, across all namespaces.
  indexSize: number (required)
    The total size of the index, in bytes.
  dimension: number (required)
    Dimension of the vectors.
  similarityFunction: string (required)
    Name of the similarity function used in indexing and queries.
  indexType: string (required)
    Type of the index. Possible values: "DENSE", "SPARSE", "HYBRID"
  denseIndex: object (optional)
    Information about the dense vector index configuration.
    Properties:
      dimension: number (required)
        Dimension of the dense vectors.
      similarityFunction: string (required)
        Similarity function used for dense vector comparisons. Possible values: "COSINE", "EUCLIDEAN", "DOT_PRODUCT"
      embeddingModel: string (required)
        Name of the embedding model used for dense vectors.
  sparseIndex: object (optional)
    Information about the sparse vector index configuration.
    Properties:
      embeddingModel: string (required)
        Name of the embedding model used for sparse vectors.
  namespaces: object (required)
    Map of namespace names to namespace information.
    Note: Every index has at least one namespace called default namespace, whose name is the empty string "".
    Properties (for each namespace):
      vectorCount: number (required)
        The number of vectors in the namespace that are ready to use.
      pendingVectorCount: number (required)
        The number of vectors in the namespace that are still processing and not ready to use.
```

--------------------------------

TITLE: Python: Delete Vectors by Metadata Filter in Upstash Vector
DESCRIPTION: This Python example demonstrates how to delete vectors based on a metadata filter. The 'filter' parameter allows you to specify conditions (e.g., 'age > 30') that vectors' metadata must match for them to be deleted, enabling powerful conditional deletion.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/delete.mdx

LANGUAGE: python
CODE:
```
index.delete(filter="age > 30")
```

--------------------------------

TITLE: Parse Document with LlamaParse
DESCRIPTION: Initialize LlamaParse to process a document and extract its content into a structured format, such as markdown. This snippet demonstrates how to load a text file and apply the parser using SimpleDirectoryReader.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: python
CODE:
```
from llama_parse import LlamaParse
from llama_index.core import SimpleDirectoryReader

# Initialize the LlamaParse parser with the desired result format
parser = LlamaParse(result_type="markdown")  # "markdown" and "text" are available

# Parse the document using the parser
file_extractor = {".txt": parser}
documents = SimpleDirectoryReader(input_files=["./documents/global_warming.txt"], file_extractor=file_extractor).load_data()
```

--------------------------------

TITLE: Delete Vectors in Specific Namespace with cURL
DESCRIPTION: This cURL example demonstrates how to delete vectors from a specific namespace within an Upstash Vector index by providing an array of vector IDs. It uses the DELETE HTTP method and requires a Bearer token for authorization, specifying 'ns' as the target namespace.

SOURCE: https://upstash.com/docs/vector/api/endpoints/delete.mdx

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/delete/ns \
  -X DELETE \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "ids": [ "id-0", "id-1" ] }'
```

--------------------------------

TITLE: Python: Delete Vectors by ID Prefix in Upstash Vector
DESCRIPTION: This Python snippet illustrates how to delete multiple vectors whose IDs share a common prefix. By providing a 'prefix' string, all vectors with IDs starting with that prefix will be removed from the index, which is useful for batch deletion of related items.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/delete.mdx

LANGUAGE: python
CODE:
```
index.delete(prefix="id-")
```

--------------------------------

TITLE: Filter Strings with GLOB Operator in SQL
DESCRIPTION: The GLOB operator filters string values based on a UNIX glob pattern. It is case-sensitive and supports wildcards like *, ?, and []. This example matches city names where the second character is 's' or 'z' and the string ends with anything other than 'm' to 'z'.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
city GLOB '?[sz]*[^m-z]'
```

--------------------------------

TITLE: Filter Array Values with NOT CONTAINS Operator in SQL
DESCRIPTION: The NOT CONTAINS operator filters keys whose array value does not contain the specified literal. It is applicable to array values. This example matches entries where 'Steel Production' is not among the major industries.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: SQL
CODE:
```
economy.major_industries NOT CONTAINS 'Steel Production'
```

--------------------------------

TITLE: Fuse Dense and Sparse Query Scores with Reciprocal Rank Fusion (RRF)
DESCRIPTION: This example demonstrates how to explicitly set Reciprocal Rank Fusion (RRF) as the fusion algorithm when querying an Upstash Vector index. RRF combines results from dense and sparse indexes by mapping each result's score based on its rank, then summing scores if a result appears in both indexes. This method is effective for combining rankings from different sources.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import FusionAlgorithm, SparseVector

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    vector=[0.5, 0.4],
    sparse_vector=SparseVector([3, 5], [0.3, 0.5]),
    fusion_algorithm=FusionAlgorithm.RRF,
)
```

LANGUAGE: javascript
CODE:
```
import { FusionAlgorithm, Index } from "@upstash/vector";

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
});

await index.query({
  vector: [0.5, 0.4],
  sparseVector: {
    indices: [2, 3],
    values: [0.13, 0.87],
  },
  fusionAlgorithm: FusionAlgorithm.RRF,
  topK: 3,
});
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.Query(vector.Query{
		Vector: []float32{0.5, 0.4},
		SparseVector: &vector.SparseVector{
			Indices: []int32{3, 5},
			Values:  []float32{0.3, 05},
		},
		FusionAlgorithm: vector.FusionAlgorithmRRF,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;
use Upstash\Vector\Enums\FusionAlgorithm;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
  vector: [0.5, 0.4],
  sparseVector: new SparseVector(
    indices: [3, 5],
    values: [0.3, 0.5],
  ),
  topK: 5,
  includeMetadata: true,
  fusionAlgorithm: FusionAlgorithm::RECIPROCAL_RANK_FUSION,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector": [0.5, 0.4], "sparseVector": {"indices": [3, 5], "values": [0.3, 0.5]}, "fusionAlgorithm": "RRF"}'
```

--------------------------------

TITLE: Configure Environment Variables for Upstash and LLMs
DESCRIPTION: Set up environment variables in a .env file for secure access to Upstash Vector, OpenAI, and Llama Cloud APIs. These variables are crucial for authenticating requests and connecting to the respective services.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: plaintext
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
OPENAI_API_KEY=your_openai_api_key
LLAMA_CLOUD_API_KEY=your_llama_cloud_api_key
```

--------------------------------

TITLE: Delete Vectors by ID with Upstash Vector Go SDK
DESCRIPTION: This example illustrates how to delete specific vectors from the Upstash Vector database using their IDs. The `Delete` method can take a single ID or a slice of IDs to remove multiple vectors. This operation is useful for managing data lifecycle within your vector store.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: Go
CODE:
```
package main

import (
	"context"
	"fmt"
	"os"

	vector "github.com/upstash/vector-go/sdk"
)

func main() {
	client, err := vector.NewClient(
		vector.WithUrl(os.Getenv("UPSTASH_VECTOR_REST_URL")),
		vector.WithToken(os.Getenv("UPSTASH_VECTOR_REST_TOKEN")),
	)
		if err != nil {
			fmt.Printf("Error creating client: %v\n", err)
			return
		}

	resp, err := client.Delete(context.Background(), []string{"1", "2"})
		if err != nil {
			fmt.Printf("Error deleting vectors: %v\n", err)
			return
		}

	fmt.Printf("Delete response: %+v\n", resp)
}
```

--------------------------------

TITLE: Upsert Raw Text Data in Upstash Vector
DESCRIPTION: This example demonstrates upserting raw text data directly into Upstash Vector. When raw text is provided, the 'data' field is automatically set to this text, allowing you to store and retrieve textual content associated with a vector ID without needing to provide vector embeddings explicitly.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [
        {
            "id": "id-2",
            "data": "Upstash is a serverless data platform.",
        },
    ],
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.upsert([
  {
    id: "id-2",
    data: "Upstash is a serverless data platform.",
  }
])
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->upsertData(new DataUpsert(
  id: 'id-0',
  data: 'Upstash is a serverless data platform.',
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
        "id": "id-0",
        "data": "Upstash is a serverless data platform."
      }'
```

--------------------------------

TITLE: Upstash Vector Account and Usage FAQs
DESCRIPTION: This section addresses common questions about Upstash Vector account limits, billing calculations for storage, bandwidth, and operations, and how different actions are counted for billing purposes. It clarifies maximum index counts, dimension limits, and charges for exceeding usage tiers.

SOURCE: https://upstash.com/docs/vector/help/faq.mdx

LANGUAGE: APIDOC
CODE:
```
FAQ:
- What is the maximum number of indexes I can create in my account?
  - Up to 10 indexes per account. Contact support@upstash.com for more.
- What is the maximum dimension I can set for my indexes?
  - Free tier: 1536
  - Fixed/Pay-as-you-go tiers: 3072
  - Pro tier: Up to 5376
- How do you calculate the storage to be charged?
  - Storage = Vector Storage + Metadata Storage
  - Vector Storage: vector count * dimension count * 4 bytes (each dimension ~4 bytes)
  - Metadata Storage: vector count * metadata size (up to 48 Kbytes)
- What happens when I exceed my Metadata Storage limit?
  - Soft limit. Email reminder for optimization. Cost remains $0.25/GB. Upgrade to Pro for incremental metadata storage.
- What happens when I exceed bandwidth limit of 200GB?
  - Initial 200GB free. Additional usage charged at $0.03/GB.
- If I upload my dataset for pay as you go tier and don’t have any read/write operation during the month, how much will I pay?
  - Only charged for index and metadata storage at $0.25/GB. No hourly charges for index creation.
- How do you count Updates and Queries for billing purposes?
  - $0.40 per 100,000 operations (ranges, queries, fetches, upserts, deletes).
  - Query types (ranges, queries, fetches): 1 operation regardless of vectors returned.
  - Update types (upserts, deletes): Billable request count equals number of vectors involved (e.g., batch upsert of 1000 vectors counts as 1000 requests).
- What is the maximum number of vectors I can have in an index?
  - Depends on dimension size and plan's max vector*dimension limit.
  - Pay-as-you-go tier: 2 billion (e.g., 5 million vectors * 400 dimension).
```

--------------------------------

TITLE: Python: Query Document with LlamaIndex Query Engine
DESCRIPTION: This snippet initializes a query engine from the previously created LlamaIndex and performs two queries against the indexed document. The results of the queries, which are generated based on the document's content, are then printed to the console.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaindex.mdx

LANGUAGE: python
CODE:
```
# Initialize the query engine
query_engine = index.as_query_engine()

# Query the document about global warming
res1 = query_engine.query("What is global warming?")
print(res1)

res2 = query_engine.query("How should we modify our diets to reduce our carbon footprint?")
print(res2)
```

--------------------------------

TITLE: Query Parsed Document with Upstash Vector and OpenAI
DESCRIPTION: Integrate the parsed document with Upstash Vector and an OpenAI LLM to enable querying. This code sets up the vector store, indexes the document, and then uses a query engine to retrieve information based on a user's question.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: python
CODE:
```
from llama_index.core import VectorStoreIndex
from llama_index.vector_stores.upstash import UpstashVectorStore
from llama_index.core import StorageContext
import openai

# Load environment variables for API keys and Upstash configuration
from dotenv import load_dotenv
import os
load_dotenv()

# Set up OpenAI API key
openai.api_key = os.getenv("OPENAI_API_KEY")

# Set up Upstash Vector Store
upstash_vector_store = UpstashVectorStore(
    url=os.getenv("UPSTASH_VECTOR_REST_URL"),
    token=os.getenv("UPSTASH_VECTOR_REST_TOKEN"),
)

# Create a storage context for Upstash Vector and index the parsed document
storage_context = StorageContext.from_defaults(vector_store=upstash_vector_store)
index = VectorStoreIndex.from_documents(documents, storage_context=storage_context)

# Create a query engine for the index and perform a query
query_engine = index.as_query_engine()
query = "What are the main points discussed in the document?"
response = query_engine.query(query)
print(response)
```

--------------------------------

TITLE: Embed and Store Sample Documents in Upstash Vector
DESCRIPTION: Define sample documents, embed them using the initialized Hugging Face embeddings, and then store these embedded documents in the Upstash Vector store. Documents are batched for efficient processing and storage, optimizing both embedding creation and HTTP requests to Upstash Vector.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: python
CODE:
```
# Sample documents to embed and store
documents = [
    Document(page_content="Global warming is causing sea levels to rise."),
    Document(page_content="AI is transforming many industries."),
    Document(page_content="Renewable energy is vital for sustainable development.")
]
vector_store.add_documents(documents=documents, batch_size=100, embedding_chunk_size=200)
```

--------------------------------

TITLE: Initialize LlamaIndex with Upstash Vector Store
DESCRIPTION: This Python snippet demonstrates how to initialize LlamaIndex with Upstash Vector as the backend vector store. It loads environment variables, sets the OpenAI API key, initializes the UpstashVectorStore, loads documents from a directory, and creates a VectorStoreIndex.

SOURCE: https://upstash.com/docs/vector/integrations/llamaindex.mdx

LANGUAGE: python
CODE:
```
from llama_index.core import VectorStoreIndex, SimpleDirectoryReader
from llama_index.vector_stores.upstash import UpstashVectorStore
from llama_index.core import StorageContext
import os
from dotenv import load_dotenv

# Load environment variables
load_dotenv()

# Set OpenAI API key
openai.api_key = os.environ["OPENAI_API_KEY"]

# Initialize Upstash Vector store
upstash_vector_store = UpstashVectorStore(
    url=os.environ["UPSTASH_VECTOR_REST_URL"],
    token=os.environ["UPSTASH_VECTOR_REST_TOKEN"],
)

# Load documents using SimpleDirectoryReader
documents = SimpleDirectoryReader("./documents/").load_data()

# Create a storage context and initialize the index
storage_context = StorageContext.from_defaults(vector_store=upstash_vector_store)
index = VectorStoreIndex.from_documents(
    documents, storage_context=storage_context
)
```

--------------------------------

TITLE: Initialize UpstashVectorStore with Namespace
DESCRIPTION: This Python snippet illustrates how to specify a namespace when initializing the UpstashVectorStore. Using namespaces allows for better organization and isolation of data within your Upstash Vector index.

SOURCE: https://upstash.com/docs/vector/integrations/llamaindex.mdx

LANGUAGE: python
CODE:
```
vector_store = UpstashVectorStore(
    url="your_upstash_url",
    token="your_upstash_token",
    namespace="your_namespace"
)
```

--------------------------------

TITLE: Configure Upstash Vector and OpenAI Environment Variables
DESCRIPTION: This snippet shows how to set up environment variables for Upstash Vector and OpenAI API keys. These variables are crucial for authenticating and connecting to the Upstash Vector database and the OpenAI service.

SOURCE: https://upstash.com/docs/vector/integrations/llamaindex.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
OPENAI_API_KEY=your_openai_api_key
```

--------------------------------

TITLE: Utilize Namespaces in Upstash Vector
DESCRIPTION: Organize different types of documents within Upstash Vector by using namespaces. You can specify a namespace when initializing an `UpstashVectorStore` instance, allowing for logical separation and management of your data.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import UpstashVectorStore

# Initialize UpstashVectorStore with a specific namespace
vector_store = UpstashVectorStore(
    url="YOUR_UPSTASH_VECTOR_URL",
    token="YOUR_UPSTASH_VECTOR_TOKEN",
    namespace="my_document_type"
)

# You can create another instance for a different namespace
vector_store_users = UpstashVectorStore(
    url="YOUR_UPSTASH_VECTOR_URL",
    token="YOUR_UPSTASH_VECTOR_TOKEN",
    namespace="user_profiles"
)
```

--------------------------------

TITLE: Run the Python Semantic Search Script
DESCRIPTION: This command executes the Python script `main.py` which contains the code for performing semantic search using Upstash Vector. Ensure that the `.env` file is correctly configured with your Upstash Vector URL and token before running.

SOURCE: https://upstash.com/docs/vector/tutorials/semantic_search.mdx

LANGUAGE: Bash
CODE:
```
python main.py
```

--------------------------------

TITLE: Configure Upstash Vector Client with Environment Variables
DESCRIPTION: Configure the Upstash Vector client by setting the UPSTASH_VECTOR_REST_URL and UPSTASH_VECTOR_REST_TOKEN environment variables. Once set, the client can be initialized without any arguments, automatically picking up these values.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL="your_rest_url"
UPSTASH_VECTOR_REST_TOKEN="your_rest_token"
```

LANGUAGE: typescript
CODE:
```
import { Index } from "@upstash/vector";

const index = new Index();
```

--------------------------------

TITLE: Query LlamaIndex for Retrieval-Augmented Generation
DESCRIPTION: This Python snippet shows how to query the LlamaIndex after it has been initialized with documents. It demonstrates creating a query engine from the index and performing multiple queries to retrieve and generate responses based on the indexed content.

SOURCE: https://upstash.com/docs/vector/integrations/llamaindex.mdx

LANGUAGE: python
CODE:
```
# Initialize the query engine
query_engine = index.as_query_engine()

# Perform queries
response_1 = query_engine.query("What is global warming?")
print(response_1)

response_2 = query_engine.query("How can we reduce our carbon footprint?")
print(response_2)
```

--------------------------------

TITLE: APIDOC: Upstash Vector Index Info Method
DESCRIPTION: The `info` method provides statistical information about an Upstash Vector index. It returns details such as the total number of vectors, pending vectors, index size, dimension, and the similarity function used. It also includes statistics for each namespace within the index.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/info.mdx

LANGUAGE: APIDOC
CODE:
```
Method: info()
Returns:
  - vector_count: integer (Total number of vectors in the index)
  - pending_vector_count: integer (Number of vectors currently pending processing)
  - index_size: integer (Size of the index in bytes)
  - dimension: integer (Number of dimensions the index has)
  - similarity_function: string (Similarity function chosen for the index)
  - namespaces: map<string, object> (Map of namespace names to their statistics)
    - namespace_name: string (Name of the namespace)
      - vector_count: integer (Vector count for the specific namespace)
      - pending_vector_count: integer (Pending vector count for the specific namespace)
```

--------------------------------

TITLE: Configure Environment Variables for Upstash Vector and LlamaParse
DESCRIPTION: This snippet shows how to set up environment variables in a '.env' file. These variables include the REST URL and token for your Upstash Vector instance and your Llama Cloud API key. These credentials are essential for authenticating and connecting to the respective services.

SOURCE: https://upstash.com/docs/vector/integrations/llamaparse.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
LLAMA_CLOUD_API_KEY=your_llama_cloud_api_key
```

--------------------------------

TITLE: Python: Configure Upstash Vector and LlamaIndex for RAG
DESCRIPTION: This code snippet loads environment variables, initializes the Upstash Vector store, reads a document, and creates a LlamaIndex VectorStoreIndex. It configures the index with specified dimensions and cosine distance for efficient retrieval.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaindex.mdx

LANGUAGE: python
CODE:
```
from llama_index.core import VectorStoreIndex, SimpleDirectoryReader
from llama_index.vector_stores.upstash import UpstashVectorStore
from llama_index.core import StorageContext
import openai
import os
from dotenv import load_dotenv

# Load environment variables
load_dotenv()
openai.api_key = os.environ["OPENAI_API_KEY"]

# Setup the Upstash vector store 
upstash_vector_store = UpstashVectorStore(
    url=os.environ["UPSTASH_VECTOR_REST_URL"],
    token=os.environ["UPSTASH_VECTOR_REST_TOKEN"],
)

# Read the document about global warming from the documents directory
documents = SimpleDirectoryReader("./documents/").load_data()

# Initialize the storage context with the Upstash vector store
storage_context = StorageContext.from_defaults(vector_store=upstash_vector_store)

# Create the index from the loaded document with 1536 dimensions and cosine distance
index = VectorStoreIndex.from_documents(
    documents, storage_context=storage_context
)
```

--------------------------------

TITLE: Create and Use Upstash Vector Namespaces
DESCRIPTION: This code demonstrates how to implicitly create a namespace by performing an upsert operation within it, and then query vectors specifically within that namespace. Namespaces are created if they do not already exist upon the first upsert.

SOURCE: https://upstash.com/docs/vector/features/namespaces.mdx

LANGUAGE: python
CODE:
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

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

const namespace = index.namespace("ns")

await namespace.upsert({
  id: "id-0",
  vector: [0.9215, 0.3897],
})

await namespace.query({
  vector: [0.9215, 0.3897],
  topK: 5,
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	namespace := index.Namespace("ns")

	namespace.Upsert(vector.Upsert{
		Id:     "id-0",
		Vector: []float32{0.9215, 0.3897},
	})

	namespace.Query(vector.Query{
		Vector: []float32{0.9215, 0.3897},
		TopK:   5,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$namespace = $index->namespace('ns');

$namespace->upsert(new VectorUpsert(
  id: 'id-0',
  vector: [0.9215, 0.3897],
));

$namespace->query(new VectorQuery(
  vector: [0.9215, 0.3897],
  topK: 5,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert/ns \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"id":"id-0", "vector":[0.9215,0.3897]}'

curl $UPSTASH_VECTOR_REST_URL/query/ns \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector":[0.9215,0.3897], "topK" : 5}'
```

--------------------------------

TITLE: Query Sparse Upstash Vector Indexes with PHP SDK
DESCRIPTION: This code snippet demonstrates how to query a sparse vector index using the Upstash Vector PHP SDK. It initializes an `Index` object and then uses the `query()` method with a `VectorQuery` containing a `SparseVector`. The `SparseVector` requires `indices` and `values` arrays, and the `topK` parameter specifies the number of results.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/query.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->query(new VectorQuery(
  sparseVector: new SparseVector(
    indices: [1, 2, 3],
    values: [5.0, 6.0, 7.0],
  ),
  topK: 15,
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->query(new VectorQuery(
  sparseVector: new SparseVector(
    indices: [1, 2, 3],
    values: [5.0, 6.0, 7.0],
  ),
  topK: 15,
));
```

--------------------------------

TITLE: PHP: Fetch Vectors by ID Prefix
DESCRIPTION: This code snippet illustrates how to retrieve all vectors whose IDs match a specified prefix from an Upstash Vector database. It uses the `fetch()` method with a `VectorFetchByPrefix` object, providing options to include metadata, vectors, and string data. Remember to substitute the placeholder URL and token with your actual Upstash Vector credentials.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/fetch.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorFetchByPrefix;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->fetch(new VectorFetchByPrefix(
  prefix: 'users:',
  includeMetadata: true, // (optional) if true the fetch results will contain metadata.
  includeVectors: true, // (optional) if true the fetch results will contain the indexed vectors.
  includeData: true // (optional) if true the fetch results will contain the string data.
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorFetchByPrefix;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->fetch(new VectorFetchByPrefix(
  prefix: 'users:',
  includeMetadata: true, // (optional) if true the fetch results will contain metadata.
  includeVectors: true, // (optional) if true the fetch results will contain the indexed vectors.
  includeData: true // (optional) if true the fetch results will contain the string data.
));
```

--------------------------------

TITLE: Perform Semantic Search with LangChain and Upstash Vector in Python
DESCRIPTION: This Python code demonstrates how to use LangChain with Upstash Vector for semantic search. It initializes a vector store, adds sample documents, and then performs a similarity search based on a query. Ensure environment variables for Upstash credentials are loaded.

SOURCE: https://upstash.com/docs/vector/integrations/langchain.mdx

LANGUAGE: python
CODE:
```
from dotenv import load_dotenv
from langchain_community.vectorstores.upstash import UpstashVectorStore
from langchain.schema import Document

# Load environment variables
load_dotenv()

# Create a vector store instance
store = UpstashVectorStore(
    embedding=True  # Embedding option enabled
)

# Sample documents to upload
documents = [
    Document(page_content="Upstash Vector is a scalable vector database."),
    Document(page_content="LangChain is a framework for building intelligent apps."),
    Document(page_content="Semantic search enables advanced query matching."),
]

# Add documents to the Upstash Vector index
store.add_documents(documents)

# Perform a similarity search
query = "What is LangChain?"
results = store.similarity_search(query, k=3)

print("Similarity Search Results:")
for res in results:
    print(res.page_content)
```

--------------------------------

TITLE: Query Hybrid Upstash Vector Indexes with PHP SDK
DESCRIPTION: This code snippet demonstrates how to query a hybrid vector index using the Upstash Vector PHP SDK. It initializes an `Index` object and then uses the `query()` method with a `VectorQuery` that includes both a dense `vector` and a `sparseVector`. The `topK` parameter specifies the number of results.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/query.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->query(new VectorQuery(
  vector: [0.1, 0.2, ...],
  sparseVector: new SparseVector(
    indices: [1, 2, 3],
    values: [5.0, 6.0, 7.0],
  ),
  topK: 15,
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->query(new VectorQuery(
  vector: [0.1, 0.2, ...],
  sparseVector: new SparseVector(
    indices: [1, 2, 3],
    values: [5.0, 6.0, 7.0],
  ),
  topK: 15,
));
```

--------------------------------

TITLE: PHP: Access Upstash Vector IndexInfo Properties
DESCRIPTION: This snippet illustrates how to access various properties of the `Upstash\Vector\IndexInfo` object returned by the `getInfo()` method. It shows how to retrieve the number of ready and pending vectors, index size, dimensions, similarity function, and information about specific namespaces.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/info.mdx

LANGUAGE: php
CODE:
```
// To know the number of vectors ready to query.
$info->vectorCount;

// To know the number of vectors that are getting indexed.
$info->pendingVectorCount;

// To know the size of the index in bytes.
$info->indexSize;

// To know the dimensions of your vector index.
$info->dimension;

// To know which similarity function is being used.
$info->similarityFunction;

// To get information about a specific index you can (More on next section):
$namespaceInfo = $info->namespace('my-namespace');
```

--------------------------------

TITLE: Load Document for Upstash Vector Indexing in Python
DESCRIPTION: Load a text document, such as 'global_warming.txt', using LangChain's TextLoader. This prepares the document for subsequent processing and uploading to the Upstash Vector index.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
from langchain_community.document_loaders import TextLoader
from langchain_text_splitters import CharacterTextSplitter

# Load the document
loader = TextLoader("documents/global_warming.txt")
documents = loader.load()
```

--------------------------------

TITLE: Using Upstash Hosted Embedding Models with TypeScript
DESCRIPTION: This snippet demonstrates how to use Upstash's hosted embedding models. It configures the Upstash Vector client, defines a chunking function to split content by periods, and provides functions for upserting data and querying the index. Dependencies include '@upstash/vector'. Ensure UPSTASH_VECTOR_REST_URL and UPSTASH_VECTOR_REST_TOKEN are set in your environment.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: TypeScript
CODE:
```
import { Index } from '@upstash/vector'

// Configure Upstash Vector client
// Make sure UPSTASH_VECTOR_REST_URL and UPSTASH_VECTOR_REST_TOKEN are in your .env
const index = new Index({
  url: process.env.UPSTASH_VECTOR_REST_URL!,
  token: process.env.UPSTASH_VECTOR_REST_TOKEN!,
})

// Chunking logic: split on period
function generateChunks(input: string): string[] {
  return input
    .trim()
    .split('.')
    .filter(i => i !== '')
}

// Upsert
export async function upsertEmbedding(resourceId: string, content: string) {
  const chunks = generateChunks(content)
  
  // Convert each chunk into an Upstash upsert object
  const toUpsert = chunks.map((chunk, i) => ({
    id: `${resourceId}-${i}`,
    data: chunk, // Using the data field instead of vector because embeddings are generated by Upstash
    metadata: {
      resourceId,
      content: chunk, // Store the chunk as metadata to use during response generation
    },
  }))

  await index.upsert(toUpsert)
}

// Query
export async function findRelevantContent(query: string, k = 4) {
  const result = await index.query({
    data: query, // Again, using the data field instead of vector field
    topK: k,
    includeMetadata: true, // Fetch metadata as well
  })

  return result
}
```

--------------------------------

TITLE: Configure Upstash Vector Credentials in .env
DESCRIPTION: Create a .env file to store your Upstash Vector REST URL and Token. Replace the placeholder values with your actual credentials. This file allows the application to securely load environment variables.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: bash
CODE:
```
UPSTASH_VECTOR_REST_URL=your_upstash_url
UPSTASH_VECTOR_REST_TOKEN=your_upstash_token
```

--------------------------------

TITLE: Parse Documents Using LlamaParse in Python
DESCRIPTION: This Python code demonstrates how to initialize LlamaParse and use it to parse documents from a specified directory. It sets the result type to markdown and loads data from a text file, preparing the content for further processing and indexing.

SOURCE: https://upstash.com/docs/vector/integrations/llamaparse.mdx

LANGUAGE: python
CODE:
```
from llama_parse import LlamaParse
from llama_index.core import SimpleDirectoryReader

# Initialize the parser
parser = LlamaParse(result_type="markdown")

# Parse a document
file_extractor = {".txt": parser}
documents = SimpleDirectoryReader(
    input_files=["./documents/global_warming.txt"],
    file_extractor=file_extractor
).load_data()
```

--------------------------------

TITLE: Implement Chat UI with Vercel AI SDK
DESCRIPTION: This React component, implemented in TypeScript, sets up the frontend chat interface. It leverages the Vercel AI SDK's `useChat` hook to manage message state, handle user input, and submit messages to the `/api/chat` endpoint. The UI renders conversation messages and provides an input field for user interaction, optionally showing tool invocation status.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: TypeScript
CODE:
```
'use client'

import { useChat } from 'ai/react'

export default function Home() {
  // This hook handles message state + streaming from /api/chat
  const { messages, input, handleInputChange, handleSubmit } = useChat({
    // You can enable multi-step calls if you want the model to call multiple tools in one session
    maxSteps: 3,
  })

  return (
    <div className="mx-auto max-w-md py-6">
      <h1 className="text-xl font-bold mb-4">RAG Chatbot with Upstash Vector</h1>
      
      {/* Render messages */}
      <div className="space-y-2 mb-8">
        {messages.map(m => (
          <div key={m.id} className="border p-2 rounded">
            <strong>{m.role}:</strong> 
            <div>
              {/* If the model calls a tool, show which tool it called */}
              {m.content.length > 0 ? (
                m.content
              ) : (
                <i>calling tool: {m?.toolInvocations?.[0]?.toolName}</i>
              )}
            </div>
          </div>
        ))}
      </div>

      {/* Text input */}
      <form onSubmit={handleSubmit} className="flex gap-2">
        <input
          className="flex-1 border rounded px-2 py-1"
          placeholder="Say something..."
          value={input}
          onChange={handleInputChange}
        />
        <button className="px-4 py-1 bg-black text-white rounded" type="submit">
          Send
        </button>
      </form>
    </div>
  )
}
```

--------------------------------

TITLE: PHP: Access Upstash Vector NamespaceInfo Properties
DESCRIPTION: This snippet illustrates how to access properties of the `Upstash\Vector\NamespaceInfo` object, which is returned by the `getNamespaceInfo()` method. It specifically shows how to retrieve the count of ready and pending vectors within a given namespace.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/info.mdx

LANGUAGE: php
CODE:
```
// To know the number of vectors ready to query.
$myNamespaceInfo->vectorCount;

// To know the number of vectors that are getting indexed.
$myNamespaceInfo->pendingVectorCount;
```

--------------------------------

TITLE: Query Vectors with Upstash Vector Go SDK
DESCRIPTION: This snippet demonstrates how to perform a similarity search (query) against the Upstash Vector database. The `Query` method takes a query vector, the number of top results to return, and optional filtering parameters. It returns a slice of `QueryResult` objects, each containing a vector ID, score, and metadata.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: Go
CODE:
```
package main

import (
	"context"
	"fmt"
	"os"

	vector "github.com/upstash/vector-go/sdk"
)

func main() {
	client, err := vector.NewClient(
		vector.WithUrl(os.Getenv("UPSTASH_VECTOR_REST_URL")),
		vector.WithToken(os.Getenv("UPSTASH_VECTOR_REST_TOKEN")),
	)
		if err != nil {
			fmt.Printf("Error creating client: %v\n", err)
			return
		}

	queryVector := []float32{0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8}
	results, err := client.Query(context.Background(), vector.QueryRequest{
		Vector: queryVector,
		TopK:   2,
		IncludeMetadata: true,
		Filter: "genre = 'science-fiction'",
	})
		if err != nil {
			fmt.Printf("Error querying vectors: %v\n", err)
			return
		}

	for _, r := range results {
		fmt.Printf("Query Result ID: %s, Score: %f, Metadata: %v\n", r.ID, r.Score, r.Metadata)
	}
}
```

--------------------------------

TITLE: Create Resource Server Action with TypeScript
DESCRIPTION: This server action demonstrates how to create a new resource and upsert its embeddings into the Upstash Vector index. It uses Zod for input validation and generates a unique resource ID. This action is designed to be used by a chatbot to store information. Dependencies include 'zod' and '@/lib/ai/upstashVector'.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: TypeScript
CODE:
```
'use server'

import { z } from 'zod'
import { upsertEmbeddings } from '@/lib/ai/upstashVector'

// A simple schema for incoming resource content
const NewResourceSchema = z.object({
  content: z.string().min(1),
})

// Server action to parse the input and upsert to the index
export async function createResource(input: { content: string }) {
  const { content } = NewResourceSchema.parse(input)

  // Generate a random ID
  const resourceId = crypto.randomUUID()

  // Upsert the chunks/embeddings to Upstash Vector
  await upsertEmbeddings(resourceId, content)

  return `Resource ${resourceId} created and embedded.`
}
```

--------------------------------

TITLE: APIDOC: Upstash Vector Fetch Method Reference
DESCRIPTION: This API documentation describes the 'fetch' method for retrieving vectors from an Upstash Vector index. It details the input parameters such as IDs, prefix, include flags, and namespace, along with the structure of the 'vectors' field returned in the response. This method allows flexible retrieval of vector data based on various criteria.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/fetch.mdx

LANGUAGE: APIDOC
CODE:
```
Method: fetch
Description: Retrieves vectors from the index based on their identifiers or a prefix.

Input Parameters:
- `ids`: string | string[] (optional)
  Description: A string or a list of strings representing the identifiers of the vectors to be fetched.
- `prefix`: string (optional)
  Description: A string prefix to match vector IDs. All vectors with IDs that start with this prefix will be retrieved.
- `include_vectors`: boolean (optional)
  Description: Flag indicating whether to include vectors in the fetch results.
- `include_metadata`: boolean (optional)
  Description: Flag indicating whether to include metadata in the fetch results.
- `include_data`: boolean (optional)
  Description: Flag indicating whether to include data in the fetch results.
- `namespace`: string (optional)
  Description: The namespace to use. When not specified, the default namespace is used.

Response Fields:
- `vectors`: Array<Object>
  Description: A list containing information for each fetched vector.
  Object Properties:
  - `id`: string
  - `vector`: Array<number> (present if `include_vectors` is true)
  - `sparse_vector`: Object (present if `include_vectors` is true)
  - `metadata`: Object (present if `include_metadata` is true)
  - `data`: string (present if `include_data` is true)
```

--------------------------------

TITLE: Implement Chat API Route with AI Model and Tools
DESCRIPTION: This TypeScript code defines the /api/chat POST route, serving as the backend for the chatbot. It uses the Vercel AI SDK's streamText function, integrates with an OpenAI model (gpt-4o), processes user messages, and defines tools for adding resources and retrieving information from a knowledge base. The route is configured to allow streaming responses for up to 30 seconds.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: TypeScript
CODE:
```
import { openai } from '@ai-sdk/openai'
import { streamText, tool } from 'ai'
import { z } from 'zod'

// Tools
import { createResource } from '@/lib/actions/resources'
import { findRelevantContent } from '@/lib/ai/upstashVector'

// Allow streaming responses up to 30 seconds
export const maxDuration = 30

export async function POST(req: Request) {
  const { messages } = await req.json()

  const result = streamText({
    // 1. Choose your AI model
    model: openai('gpt-4o'),

    // 2. Pass along the conversation messages from the user
    messages,

    // 3. Prompt the model
    system: `You are a helpful RAG assistant. 
    You have the ability to add and retrieve content from your knowledge base.
    Only respond to the user with information found in your knowledge base.
    If no relevant information is found, respond with: "Sorry, I don't know."`,

    // 4. Provide your "tools": resource creation & retrieving content
    tools: {
      addResource: tool({
        description: `Add new content to the knowledge base.`,
        parameters: z.object({
          content: z.string().describe('The content to embed and store'),
        }),
        execute: async ({ content }) => {
          const msg = await createResource({ content })
          return msg
        },
      }),
      getInformation: tool({
        description: `Retrieve relevant knowledge from your knowledge base to answer user queries.`,
        parameters: z.object({
          question: z.string().describe('The question to search for'),
        }),
        execute: async ({ question }) => {
          const hits = await findRelevantContent(question)
          // Return array of metadata for each chunk
          // e.g. [{ id, score, metadata: { resourceId, content }}, ... ]
          return hits
        },
      }),
    },
  })

  // 5. Return the streaming response
  return result.toDataStreamResponse()
}
```

--------------------------------

TITLE: Python: Execute Upstash Vector Range Query
DESCRIPTION: Demonstrates how to perform a basic range query using the `range` method in Python. It initializes an Upstash Vector index and executes a query to retrieve vectors, then prints the next cursor and details of each retrieved vector.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/range.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index.from_env()

# Execute the range query
range_result = index.range(
    cursor="",
    limit=10,
    include_vectors=False,
    include_metadata=True,
    include_data=True,
)

# Print the range result
print("Next Cursor:", range_result.next_cursor)

for vector_info in range_result.vectors:
    print("ID:", vector_info.id)
    print("Vector:", vector_info.vector)
    print("Metadata:", vector_info.metadata)
    print("Data:", vector_info.data)
```

--------------------------------

TITLE: API Reference for Upstash Vector Fetch Command
DESCRIPTION: Detailed API documentation for the 'fetch' command in Upstash Vector, outlining its arguments, their types, and descriptions, as well as the structure of the response. It supports fetching by specific IDs or by a prefix.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/fetch.mdx

LANGUAGE: APIDOC
CODE:
```
interface Fetch {
  /**
   * Used to retrieve the vector by ID.
   */
  (
    IDs: string[] | number[]
  ): Promise<FetchResult[]>;
  (
    payload: FetchPayload,
    options?: FetchOptions
  ): Promise<FetchResult[]>;
}

interface FetchPayload {
  ids?: string[] | number[];
  prefix?: string; // For fetching larger datasets with prefix, it is recommended to use the paginated `range` command instead.
}

interface FetchOptions {
  includeMetadata?: boolean; // Whether to include the metadata of the vectors in the response. Setting this `true` would be the best practice, since it will make it easier to identify the vectors.
  includeVectors?: boolean; // Whether to include the vector themselves in the response.
  includeData?: boolean; // Whether to include the data field in the response.
  namespace?: string; // Namespace to fetch from. If not set, default namespace is used.
}

interface FetchResult {
  id: string | number; // The ID of the resulting vector.
  vector?: number[]; // The vectors (if `includeVectors` is set to true)
  sparseVector?: SparseVector; // The resulting sparseVector (if `includeVectors` is set to true)
  metadata?: Record<string, unknown>; // The metadata of the vectors (if `includeMetadata` is set to true)
  data?: string; // The data of the vector (if `includeData` is set to true)
}

type SparseVector = any; // Placeholder for actual SparseVector type
```

--------------------------------

TITLE: Query Parsed Content with Upstash Vector in Python
DESCRIPTION: This Python code illustrates how to index parsed documents using Upstash Vector and then query the indexed content. It loads environment variables, sets up the Upstash Vector store, creates a storage context, and performs a semantic query on the document's content.

SOURCE: https://upstash.com/docs/vector/integrations/llamaparse.mdx

LANGUAGE: python
CODE:
```
from llama_index.core import VectorStoreIndex
from llama_index.vector_stores.upstash import UpstashVectorStore
from llama_index.core import StorageContext
from dotenv import load_dotenv
import os

# Load environment variables
load_dotenv()

# Set up Upstash Vector Store
vector_store = UpstashVectorStore(
    url=os.getenv("UPSTASH_VECTOR_REST_URL"),
    token=os.getenv("UPSTASH_VECTOR_REST_TOKEN")
)

# Create storage context and index the parsed document
storage_context = StorageContext.from_defaults(vector_store=vector_store)
index = VectorStoreIndex.from_documents(documents, storage_context=storage_context)

# Perform a query
query_engine = index.as_query_engine()
response = query_engine.query("What is the main topic discussed in the document?")
```

--------------------------------

TITLE: Upstash Vector: Embedding Models for Sparse and Hybrid Indexes
DESCRIPTION: This table lists the specific embedding models available for sparse and hybrid indexes in Upstash Vector. These models are optimized for use cases requiring sparse vector representations, such as those detailed in the 'Creating Sparse Vectors' documentation.

SOURCE: https://upstash.com/docs/vector/features/embeddingmodels.mdx

LANGUAGE: APIDOC
CODE:
```
| Name |
| :------------------------------------------------ |
| [BAAI/bge-m3](https://huggingface.co/BAAI/bge-m3) |
| [BM25](https://en.wikipedia.org/wiki/Okapi_BM25) |
```

--------------------------------

TITLE: Upstash Vector Infrastructure Details
DESCRIPTION: This section provides information about the cloud provider and regions where Upstash Vector is currently hosted. It clarifies that clients do not need to be on AWS but will experience better performance if they are.

SOURCE: https://upstash.com/docs/vector/help/faq.mdx

LANGUAGE: APIDOC
CODE:
```
Cloud Provider:
  - Name: AWS
  - Future Plans: Expansion to other cloud providers (contact support@upstash.com for requests)

Available Regions:
  - AWS us-east-1
  - AWS eu-west-1
  - Future Plans: Expansion to more regions where other Upstash products are offered

Client Location:
  - Requirement: Not required to be on AWS
  - Performance: Clients in AWS regions will have better performance
```

--------------------------------

TITLE: API Reference for Upstash Vector Query Method
DESCRIPTION: This section details the `query` method for retrieving vectors from an Upstash Vector index. It outlines all accepted parameters, their types, and descriptions, along with the structure of the response object including id, metadata, score, vector, sparse_vector, and data fields.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/query.mdx

LANGUAGE: APIDOC
CODE:
```
Method: query
Description: Retrieve vectors from the index based on specific criteria.

Parameters:
- vector: (list[float]) The reference vector for similarity comparison.
- sparse_vector: (list[float]) The sparse vector value to query.
- data: (str) A string for text-based queries (mutually exclusive with vector).
- include_metadata: (bool) Flag to include metadata in results.
- include_vector: (bool) Flag to include vectors in results.
- include_data: (bool) Flag to include data in results.
- top_k: (int) The number of top matching vectors to retrieve.
- filter: (str) Metadata filtering expression (e.g., "genre = 'fantasy'").
- namespace: (str, optional) The namespace to use. Defaults to the default namespace.
- weighting_strategy: (str, optional) Weighting strategy for sparse vectors.
- fusion_algorithm: (str, optional) Fusion algorithm for hybrid vectors.
- query_mode: (str, optional) Query mode for hybrid indexes with Upstash-hosted embedding models.

Response Fields:
- id: (str) The identifier associated with the matching vector.
- metadata: (dict) Additional information or attributes linked to the matching vector.
- score: (float) A measure of similarity [0, 1], where 1 is a perfect match.
- vector: (list[float], optional) The vector itself (if include_vector is True).
- sparse_vector: (list[float], optional) The sparse vector itself (if include_vector is True).
- data: (str, optional) Additional unstructured information linked to the matching vector.
```

--------------------------------

TITLE: Query Dense and Sparse Vectors in Upstash Vector
DESCRIPTION: This snippet demonstrates how to query dense and sparse vectors directly using the Upstash Vector index. It shows how to initialize the index with a URL and token, then perform separate queries for dense and sparse vectors. The results can then be reranked as needed.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: JavaScript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

const denseResults = await index.query(
  {
    vector: [0.5, 0.4],
    topK: 3,
  },
)

const sparseResults = await index.query(
  {
    sparseVector: {
      indices: [2, 3],
      values: [0.13, 0.87],
    },
    topK: 3,
  },
)

// Rerank dense and sparse results as you like here
```

LANGUAGE: Go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	denseScores, err := index.Query(vector.Query{
		Vector: []float32{0.5, 0.4},
	})

	sparseScores, err := index.Query(vector.Query{
		SparseVector: &vector.SparseVector{
			Indices: []int32{3, 5},
			Values:  []float32{0.3, 05},
		},
	})

	// Rerank dense and sparse results as you like here
}
```

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$denseResults = $index->query(new VectorQuery(
  vector: [0.5, 0.4],
  topK: 3,
));

$sparseResults = $index->query(new VectorQuery(
  sparseVector: new SparseVector(
    indices: [3, 5],
    values: [0.3, 0.5],
  ),
  topK: 3,
));

// Rerank dense and sparse results as you like here
```

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector": [0.5, 0.4]}'

curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"sparseVector": {"indices": [3, 5], "values": [0.3, 0.5]}}'
```

--------------------------------

TITLE: Python: Insert Documents into Upstash Vector Index
DESCRIPTION: After splitting documents, this code snippet demonstrates how to add them to your Upstash Vector index using the 'store.add_documents' method. This action vectorizes the document chunks and stores them, making them ready for semantic search. Ensure 'store' is an initialized UpstashVectorStore instance.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
inserted_vectors = store.add_documents(docs)
```

--------------------------------

TITLE: Query Dense Upstash Vector Indexes with PHP SDK
DESCRIPTION: This code snippet demonstrates how to query a dense vector index using the Upstash Vector PHP SDK. It initializes an `Index` object with the REST URL and token, then uses the `query()` method with a `VectorQuery` object. The `VectorQuery` specifies the dense vector, `topK` limit, and optional parameters like `includeMetadata`, `includeVectors`, `includeData`, and `filter`.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/query.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->query(new VectorQuery(
  vector: [0.1, 0.2, ...], // "..." represents the dimension size of your vector index.
  topK: 15, // topK is the limit number of records we want to be returned.
  includeMetadata: true, // (optional) if true the query results will contain metadata.
  includeVectors: true, // (optional) if true the query results will contain the indexed vectors.
  includeData: true, // (optional) if true the query results will contain the string data.
  filter: '', // (optional) if set, the query results will be filtered by the given filter.
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->query(new VectorQuery(
  vector: [0.1, 0.2, ...], // "..." represents the dimension size of your vector index.
  topK: 15, // topK is the limit number of records we want to be returned.
  includeMetadata: true, // (optional) if true the query results will contain metadata.
  includeVectors: true; // (optional) if true the query results will contain the indexed vectors.
  includeData: true, // (optional) if true the query results will contain the string data.
  filter: '', // (optional) if set, the query results will be filtered by the given filter.
));
```

--------------------------------

TITLE: Embed and Store Documents in Upstash Vector
DESCRIPTION: Define sample documents as LangChain Document objects, then embed them using the initialized Hugging Face model and store them in Upstash Vector. Documents are batched for efficient processing and storage, with `embedding_chunk_size` controlling parallel embedding and `batch_size` controlling HTTP request batching.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: python
CODE:
```
# Import the required Document class from LangChain
from langchain.schema import Document

# Sample documents to embed and store as Document objects
documents = [
    Document(page_content="Global warming is causing sea levels to rise."),
    Document(page_content="Artificial intelligence is transforming many industries."),
    Document(page_content="Renewable energy is vital for sustainable development.")
]

# Embed documents and store in Upstash Vector with batching
vector_store.add_documents(
    documents=documents,
    batch_size=100,               
    embedding_chunk_size=200      
)

print("Documents with embeddings have been stored in Upstash Vector.")
```

--------------------------------

TITLE: Upstash Vector: Range Method API Documentation
DESCRIPTION: This section details the Upstash Vector 'range' method, including its arguments and response structure. It outlines parameters like cursor, prefix, limit, and options for including metadata or vector data, along with the structure of the paginated response.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/range.mdx

LANGUAGE: APIDOC
CODE:
```
class UpstashVectorIndex {
  /**
   * Retrieves vectors in chunks with pagination.
   * This method is stateless, meaning all parameters must be passed in each subsequent request.
   * @param options - Configuration options for the range query.
   * @param namespaceOption - Optional namespace for the query.
   * @returns A RangeResponse object containing the next cursor and an array of vectors.
   */
  range<T = Record<string, unknown>>(options: {
    cursor: string | number; // The cursor to the last retrieved vector. Should be set to `0` in the initial range request.
    prefix?: string; // An string prefix to match vector IDs. All vectors with IDs that start with this prefix will be retrieved.
    limit: number; // The number of maximum vectors wanted in the response of range. (page size)
    includeMetadata?: boolean; // Whether to include the metadata of the vectors in the response.
    includeVectors?: boolean; // Whether to include the vector themselves in the response.
    includeData?: boolean; // Whether to include the data field in the response.
  }, namespaceOption?: { namespace?: string }): Promise<RangeResponse<T>>;
}

interface RangeResponse<T = Record<string, unknown>> {
  nextCursor: string | number; // Cursor to use in the next range request.
  vectors: Array<Vector<T>>; // An array of retrieved vectors.
}

interface Vector<T = Record<string, unknown>> {
  id: string | number; // The ID of the vector
  vector?: number[]; // The vectors (if `includeVectors` is set to true)
  metadata?: T; // The metadata of the vectors (if `includeMetadata` is set to true)
  data?: string; // The data of the vector (if `includeData` is set to true)
}
```

--------------------------------

TITLE: Python: Fetch Upstash Vector with Namespace
DESCRIPTION: This Python snippet demonstrates how to fetch a vector from a specific namespace within your Upstash Vector index. By providing the 'namespace' parameter, you can target operations to a particular logical partition of your data. If no namespace is specified, the default namespace is used.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/fetch.mdx

LANGUAGE: python
CODE:
```
index.fetch("id-4", namespace="ns")
```

--------------------------------

TITLE: Enable Nested Event Loops for Jupyter Notebook
DESCRIPTION: Apply nest_asyncio to allow nested event loops, which is necessary when running LlamaParse within a Jupyter Notebook environment. This ensures asynchronous operations can be executed without conflicts.

SOURCE: https://upstash.com/docs/vector/tutorials/llamaparse.mdx

LANGUAGE: python
CODE:
```
import nest_asyncio
nest_asyncio.apply()
```

--------------------------------

TITLE: Python: Range Query with Namespace
DESCRIPTION: Shows how to specify a namespace when performing a range query. This allows operations to be scoped to a particular namespace within the Upstash Vector index, rather than the default one.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/range.mdx

LANGUAGE: python
CODE:
```
index.range(..., namespace="ns")
```

--------------------------------

TITLE: Query Upstash Vector with Metadata Filtering
DESCRIPTION: This snippet demonstrates how to query the Upstash Vector index, apply a filter based on metadata, and specify the number of top results to retrieve. It requires an initialized Upstash Vector index with a valid URL and token. The output will be a list of vectors matching the query and filter criteria.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
  vector: [0.9215, 0.3897],
  topK: 5,
  includeMetadata: true,
  filter: "url GLOB '*imgur.com*'",
))
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
   "vector":[0.9215,0.3897],
   "topK" : 5,
   "includeMetadata": true,
   "filter": "url GLOB \"*imgur.com*\""
}'
```

--------------------------------

TITLE: List Upstash Vector Namespaces across languages
DESCRIPTION: This snippet demonstrates how to list all active namespaces in an Upstash Vector index. It requires an initialized Index object with a valid REST URL and token. The operation returns a list of strings, where each string is the name of an active namespace.

SOURCE: https://upstash.com/docs/vector/features/namespaces.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.list_namespaces()
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.listNamespaces()
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.ListNamespaces()
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->listNamespaces();
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/list-namespaces \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN"
```

--------------------------------

TITLE: Python: Fetch All Results with Resumable Query
DESCRIPTION: Illustrates a common pattern for fetching all results from a resumable query iteratively. This approach uses a `while` loop to continuously fetch batches of results until no more are available, then stops the query to release resources.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
query = index.resumable_query(
  vector=[0.1, 0.2],
  top_k=2,
  include_metadata=True
)
results = query.start()
while True:
  next_batch = query.fetch_next(2)
  if not next_batch:
    break
  results.extend(next_batch)
query.stop()
```

--------------------------------

TITLE: APIDOC: Upstash Vector Query Options
DESCRIPTION: This section details the `query` method options for the Upstash Vector client, specifically focusing on the `includeData` parameter. Understanding these options is crucial for controlling the type and amount of data returned from vector queries.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: APIDOC
CODE:
```
interface QueryOptions {
  topK: number; // The number of top results to return.
  vector: number[]; // The query vector.
  includeData?: boolean; // Optional. If true, includes the original data associated with the vector in the results. Defaults to false.
  includeVectors?: boolean; // Optional. If true, includes the vector itself in the results. Defaults to false.
}

interface QueryResult {
  id: string; // The ID of the matched vector.
  score: number; // The similarity score.
  data?: any; // The original data associated with the vector, present if includeData is true.
  vector?: number[]; // The vector itself, present if includeVectors is true.
}
```

--------------------------------

TITLE: APIDOC: Resumable Query Parameters
DESCRIPTION: This section details the parameters available for configuring a resumable query in Upstash Vector. Parameters include options for specifying the query vector or data, controlling result content (metadata, vectors, data), limiting results (top_k), applying filters, and managing namespaces and hybrid search strategies.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: json
CODE:
```
{
  "vector": "The reference vector for similarity comparison.",
  "sparse_vector": "The sparse vector value to query.",
  "data": "A string for text-based queries (mutually exclusive with vector).",
  "include_metadata": "A boolean flag indicating whether to include metadata in the query results.",
  "include_vector": "A boolean flag indicating whether to include vectors in the query results.",
  "include_data": "A boolean flag indicating whether to include data in the query results.",
  "top_k": "The number of top matching vectors to retrieve.",
  "filter": "Metadata filtering of the vector is used to query your data based on the filters and narrow down the query results.",
  "namespace": "The namespace to use. When not specified, the default namespace is used.",
  "weighting_strategy": "Weighting strategy to be used for sparse vectors.",
  "fusion_algorithm": "Fusion algorithm to use while fusing scores from hybrid vectors.",
  "query_mode": "Query mode for hybrid indexes with Upstash-hosted embedding models.",
  "max_idle": "The maximum idle time for the query in seconds."
}
```

--------------------------------

TITLE: Fetch Vectors by ID with Upstash Vector Go SDK
DESCRIPTION: This snippet demonstrates how to retrieve vectors from the Upstash Vector database using their unique IDs. The `Fetch` method allows fetching multiple vectors in a single call. It returns a slice of `Vector` objects, which include the vector data and any associated metadata.

SOURCE: https://upstash.com/docs/vector/sdk/gosdk.mdx

LANGUAGE: Go
CODE:
```
package main

import (
	"context"
	"fmt"
	"os"

	vector "github.com/upstash/vector-go/sdk"
)

func main() {
	client, err := vector.NewClient(
		vector.WithUrl(os.Getenv("UPSTASH_VECTOR_REST_URL")),
		vector.WithToken(os.Getenv("UPSTASH_VECTOR_REST_TOKEN")),
	)
		if err != nil {
			fmt.Printf("Error creating client: %v\n", err)
			return
		}

	vectors, err := client.Fetch(context.Background(), []string{"1", "2"})
		if err != nil {
			fmt.Printf("Error fetching vectors: %v\n", err)
			return
		}

	for _, v := range vectors {
		fmt.Printf("Fetched vector ID: %s, Vector: %v, Metadata: %v\n", v.ID, v.Vector, v.Metadata)
	}
}
```

--------------------------------

TITLE: Fetch Random Vector API Reference
DESCRIPTION: This section provides the API reference for fetching a random vector. It includes the HTTP method, endpoint, and details on path parameters, request body (none), and the structure of the expected response.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch-random.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://{endpoint}/random/{namespace}

Path Parameters:
- namespace: string (optional)
  Description: The namespace to use. When no namespace is specified, the default namespace will be used.

Response:
- null (if namespace is empty)
- result: object
  - id: string (required)
    Description: The id of the vector.
  - vector: number[] (optional)
    Description: The dense vector value for dense and hybrid indexes.
  - sparseVector: object[] (optional)
    Description: The sparse vector value for sparse and hybrid indexes.
    - indices: number[]
      Description: Indices of the non-zero valued dimensions.
    - values: number[]
      Description: Values of the non-zero valued dimensions.
```

--------------------------------

TITLE: Improve Upstash Vector Query Type-Checking with TypeScript Generics
DESCRIPTION: This TypeScript code demonstrates how to improve type-checking for metadata when querying Upstash Vector by using a generic type parameter. It defines a `Metadata` interface and applies it to the `index.query` method, allowing direct access to metadata fields without explicit typecasting. This enhances code safety and readability.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/query.mdx

LANGUAGE: typescript
CODE:
```
type Metadata = {
  title: string,
  genre: 'sci-fi' | 'fantasy' | 'horror' | 'action'
}

const results = await index.query<Metadata>({
  vector: [
    ... // query embedding
  ],
  includeVectors: true,
  topK: 1,
  filter: "genre = 'fantasy' and title = 'Lord of the Rings'"
})

if (results[0].metadata) {
  // Since we passed the Metadata type parameter above,
  // we can interact with metadata fields without having to
  // do any typecasting.
  const { title, genre } = results[0].metadata;
  console.log(`The best match in fantasy was ${title}`)
}
```

--------------------------------

TITLE: Query Upstash Vector and Include Data
DESCRIPTION: This code demonstrates how to query vectors and retrieve the associated 'data' field. By setting 'include_data' (or 'includeData') to true, the query results will contain the unstructured data stored with each vector, allowing direct access to contextual information.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

result = index.query(
    data="What is Upstash?",
    include_data=True,
)

for res in result:
    print(f"{res.id}: {res.data}")
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

const result = await index.query({
  data: "What is Upstash?",
  includeData: true,
  topK: 3
})

for (const vector of result) {
  console.log(`${vector.id}: ${vector.data}`)
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$results = $index->queryData(new DataQuery(
  data: 'Upstash is a serverless data platform.',
  topK: 3
  includeData: true,
));

foreach ($results as $result) {
  print_r($result->toArray());
}
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
        "data": "What is Upstash?",
        "includeData": true,
      }'
```

--------------------------------

TITLE: Query Upstash Vector Data with PHP
DESCRIPTION: This snippet demonstrates how to query an Upstash Vector index using a simple string. The index must be configured with an embedding model to automatically convert the string into vector embeddings. The query returns a specified number of top results and can include the original data.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/query.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->queryData(new DataQuery(
  data: 'What is the capital of France?',
  topK: 1, // to only return 1 result.
  includeData: true,
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->queryData(new DataQuery(
  data: 'What is the capital of France?',
  topK: 1, // to only return 1 result.
  includeData: true,
));
```

--------------------------------

TITLE: Upstash Vector API Reference
DESCRIPTION: This section details the API endpoints, request methods, and data schemas for interacting with the Upstash Vector service. It includes definitions for vector operations like upsert, query, and delete, along with their respective parameters and response formats.

SOURCE: https://upstash.com/docs/vector/overall/llms-txt.mdx

LANGUAGE: APIDOC
CODE:
```
## Upstash Vector API

### Base URL
`https://vector.upstash.app/v1`

### Authentication
All requests require an `Authorization` header with your Upstash Vector token.
`Authorization: Bearer <YOUR_UPSTASH_VECTOR_TOKEN>`

### Endpoints

#### 1. Upsert Vectors
**Description**: Inserts or updates vectors in the index.
**Method**: `POST`
**Path**: `/vectors`
**Request Body**: `application/json`
```json
[
  {
    "id": "string",
    "vector": ["number"],
    "metadata": {"key": "value"}
  }
]
```
**Response**: `200 OK`
```json
{
  "message": "Vectors upserted successfully"
}
```

#### 2. Query Vectors
**Description**: Queries the index for similar vectors.
**Method**: `POST`
**Path**: `/query`
**Request Body**: `application/json`
```json
{
  "vector": ["number"],
  "topK": "integer",
  "includeMetadata": "boolean",
  "includeVectors": "boolean"
}
```
**Response**: `200 OK`
```json
[
  {
    "id": "string",
    "score": "number",
    "vector": ["number"] (optional),
    "metadata": {"key": "value"} (optional)
  }
]
```

#### 3. Delete Vectors
**Description**: Deletes vectors from the index by ID.
**Method**: `DELETE`
**Path**: `/vectors`
**Request Body**: `application/json`
```json
[
  "string" (vector ID)
]
```
**Response**: `200 OK`
```json
{
  "message": "Vectors deleted successfully"
}
```
```

--------------------------------

TITLE: List Upstash Vector Index Namespaces via API
DESCRIPTION: This API endpoint retrieves a list of all namespace names associated with an Upstash Vector index. It requires no additional request data and returns an array of strings representing the namespace names. Every index includes a default namespace, identified by an empty string.

SOURCE: https://upstash.com/docs/vector/api/endpoints/list-namespaces.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://{endpoint}/list-namespaces
AuthMethod: bearer

Request:
  This endpoint doesn't require any additional data.

Response:
  namespaces: string[] (required)
    Array of namespace names.
    Note: Every index has at least one namespace called default namespace, whose name is the empty string "".
```

--------------------------------

TITLE: Upstash Vector: General Purpose Embedding Models for Dense and Hybrid Indexes
DESCRIPTION: This table lists general-purpose embedding models available for dense and hybrid indexes in Upstash Vector. It includes key specifications such as dimension, sequence length, and MTEB scores to help users select an appropriate model for tasks like classification, clustering, or retrieval.

SOURCE: https://upstash.com/docs/vector/features/embeddingmodels.mdx

LANGUAGE: APIDOC
CODE:
```
| Name | Dimension | Sequence Length | MTEB |
| :-------------------------------------------------------------------------------------- | :-------- | :-------------- | :---- |
| [mixedbread-ai/mxbai-embed-large-v1](https://huggingface.co/mixedbread-ai/mxbai-embed-large-v1) | 1024 | 512 | 64.68 |
| [WhereIsAI/UAE-Large-V1](https://huggingface.co/WhereIsAI/UAE-Large-V1) | 1024 | 512 | 64.64 |
| [BAAI/bge-large-en-v1.5](https://huggingface.co/BAAI/bge-large-en-v1.5) | 1024 | 512 | 64.23 |
| [BAAI/bge-base-en-v1.5](https://huggingface.co/BAAI/bge-base-en-v1.5) | 768 | 512 | 63.55 |
| [BAAI/bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5) | 384 | 512 | 62.17 |
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | 384 | 256 | 56.26 |
| [BAAI/bge-m3](https://huggingface.co/BAAI/bge-m3) | 1024 | 8192 | * |
| [google-bert/bert-base-uncased](https://huggingface.co/google-bert/bert-base-uncased) | 768 | 512 | 38.33 |
```

--------------------------------

TITLE: Upsert Vectors with Data and Metadata in Upstash Vector
DESCRIPTION: This code demonstrates how to upsert vectors, including both structured metadata and unstructured data. The 'data' field provides contextual information directly tied to the vector, which can be fetched during queries. This eliminates the need for a separate database to store related textual content.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [
        {
            "id": "id-0",
            "vector": [0.9215, 0.3897],
            "metadata": {"url": "https://imgur.com/z9AVZLb"},
            "data": "data-0",
        },
        {
            "id": "id-1",
            "vector": [0.3897, 0.9215],
            "data": "data-1",
        },
    ],
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.upsert([
  {
    id: "id-0",
    vector: [0.9215, 0.3897],
    metadata: {"url": "https://imgur.com/z9AVZLb"},
    data: "data-0",
  },
  {
    id: "id-1",
    vector: [0.3897, 0.9215],
    data: "data-1",
  },
])
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->upsertMany([
  new VectorUpsert(
    id: 'id-0',
    vector: [0.9215, 0.3897],
    data: 'data-0',
  ),
  new VectorUpsert(
    id: 'id-1',
    vector: [0.3897, 0.9215],
    data: 'data-1',
  ),
]);
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[
        {
            "id": "id-0",
            "vector": [0.9215, 0.3897],
            "metadata": {"url": "https://imgur.com/z9AVZLb"},
            "data": "data-0"
        },
        {
            "id": "id-1",
            "vector": [0.3897, 0.9215],
            "data": "data-1"
        }
    ]'
```

--------------------------------

TITLE: Query Data with Upstash Vector Embedding Models
DESCRIPTION: This code snippet demonstrates how to query raw text data from an Upstash Vector index. It requires your Upstash Vector REST URL and token for authentication. The query searches for similar data points based on the provided text, returning the top K results and optionally including metadata.

SOURCE: https://upstash.com/docs/vector/features/embeddingmodels.mdx

LANGUAGE: python
CODE:
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

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({
  data: "What is Upstash?",
  topK: 1,
  includeMetadata: true,
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.QueryData(vector.QueryData{
		Data:            "What is Upstash?",
		TopK:            1,
		IncludeMetadata: true,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->queryData(new DataQuery(
  data: 'What is Upstash?',
  topK: 1,
  includeMetadata: true,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "What is Upstash?", "topK": 1, "includeMetadata": "true"}'
```

--------------------------------

TITLE: Upsert Vectors in Python via Dictionary
DESCRIPTION: This Python snippet demonstrates how to upsert vectors into an Upstash Vector index using a list of dictionaries. Each dictionary must include 'id' and 'vector' keys, and can optionally include 'metadata' and 'data' keys. This method requires an initialized `Index` instance from the `upstash_vector` library.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/upsert.mdx

LANGUAGE: python
CODE:
```
import random

from upstash_vector import Index

index = Index.from_env()

dimension = 128  # Adjust based on your index's dimension
upsert_amount = 100

vectors = [
    {
        "id": f"generated-id-{i}",
        "vector": [random.random() for _ in range(dimension)],
        "metadata": {"some_field": f"some_value-{i}"},
        "data": f"some-unstructured-data-{i}",
    }
    for i in range(upsert_amount)
]

index.upsert(vectors=vectors)
```

--------------------------------

TITLE: APIDOC: Upstash Vector Range Method Definition
DESCRIPTION: Defines the `range` method for the Upstash Vector index, detailing its parameters and the structure of the returned object. This method allows fetching vectors based on a cursor, prefix, and various inclusion flags.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/range.mdx

LANGUAGE: APIDOC
CODE:
```
method: range(
  cursor: string, 
  prefix: string, 
  limit: number, 
  include_vectors: boolean, 
  include_metadata: boolean, 
  include_data: boolean
) -> {
  next_cursor: string,
  vectors: Array<{
    id: string,
    vector: Array<number>,
    metadata: object,
    data: string
  }>
}
```

--------------------------------

TITLE: Upsert Vectors in Python via Vector Object
DESCRIPTION: This Python snippet demonstrates how to upsert vectors into an Upstash Vector index using a list of `Vector` objects. It requires the `upstash_vector` library and an initialized `Index` instance. The `Vector` objects must include an `id`, a `vector` (list of floats), and optionally `metadata` and `data` fields.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/upsert.mdx

LANGUAGE: python
CODE:
```
import random

from upstash_vector import Index, Vector

index = Index.from_env()

dimension = 128  # Adjust based on your index's dimension
upsert_amount = 100

vectors = [
    Vector(
        id=f"generated-id-{i}",
        vector=[random.random() for _ in range(dimension)],
        metadata={"some_field": f"some_value-{i}"},
        data=f"some-unstructured-data-{i}",
    )
    for i in range(upsert_amount)
]

index.upsert(vectors=vectors)
```

--------------------------------

TITLE: View Query Results from LangChain Upstash Vector Search
DESCRIPTION: This plaintext output shows the results of a similarity search performed using LangChain and Upstash Vector. The results are ordered by relevance, demonstrating how semantic search retrieves contextually similar documents.

SOURCE: https://upstash.com/docs/vector/integrations/langchain.mdx

LANGUAGE: plaintext
CODE:
```
Similarity Search Results:
LangChain is a framework for building intelligent apps.
Semantic search enables advanced query matching.
Upstash Vector is a scalable vector database.
```

--------------------------------

TITLE: PHP: Fetch Specific Vectors by ID
DESCRIPTION: This code snippet demonstrates how to fetch specific vectors from an Upstash Vector database using their unique IDs. It utilizes the `fetch()` method with a `VectorFetch` object, allowing optional inclusion of metadata, vectors, and string data in the results. Ensure you replace the placeholder URL and token with your actual Upstash Vector credentials.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/fetch.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorFetch;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->fetch(new VectorFetch(
  ids: ['1', '2'],
  includeMetadata: true, // (optional) if true the fetch results will contain metadata.
  includeVectors: true, // (optional) if true the fetch results will contain the indexed vectors.
  includeData: true // (optional) if true the fetch results will contain the string data.
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorFetch;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->fetch(new VectorFetch(
  ids: ['1', '2'],
  includeMetadata: true, // (optional) if true the fetch results will contain metadata.
  includeVectors: true, // (optional) if true the fetch results will contain the indexed vectors.
  includeData: true // (optional) if true the fetch results will contain the string data.
));
```

--------------------------------

TITLE: Upstash Vector: Query with Metadata Filter
DESCRIPTION: This snippet demonstrates how to perform a vector similarity search with a metadata filter. The filter uses a SQL-like syntax to specify conditions on metadata fields, ensuring only vectors matching the criteria are returned. It requires an initialized Upstash Vector Index with a valid URL and token.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
  url="UPSTASH_VECTOR_REST_URL",
  token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
  vector=[0.9215, 0.3897],
  filter="population >= 1000000 AND geography.continent = 'Asia'",
  top_k=5,
  include_metadata=True
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({
  vector: [0.9215, 0.3897],
  filter: "population >= 1000000 AND geography.continent = 'Asia'",
  topK: 5,
  includeMetadata: true,
});
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.Query(vector.Query{
		Vector:          []float32{0.9215, 0.3897},
		Filter:          `population >= 1000000 AND geography.continent = 'Asia'`,
		TopK:            5,
		IncludeMetadata: true,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
  vector: [0.9215, 0.3897],
  topK: 5,
  includeMetadata: true,
  filter: "population >= 1000000 AND geography.continent = 'Asia'",
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
   "vector":[0.9215,0.3897],
   "topK" : 5,
   "filter": "population >= 1000000 AND geography.continent = \"Asia\"",
   "includeMetadata": true
}'
```

--------------------------------

TITLE: Python: Perform Semantic Search in Upstash Vector
DESCRIPTION: This snippet shows how to perform a semantic search on the Upstash Vector index using a natural language query. The 'similarity_search' method retrieves the top 'k' most semantically similar documents. The output includes the document content and metadata, allowing for relevant information retrieval.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
result = store.similarity_search("Technology's role in global warming.", k=5)
print(result)
```

--------------------------------

TITLE: Query Vectors API Reference
DESCRIPTION: This section provides the API reference for querying vectors in Upstash Vector. It details the HTTP method, endpoint, authentication, and all available request body and path parameters with their types, descriptions, and default values. Both single and batch query requests are supported.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/query/{namespace}
AuthMethod: bearer

Request Body (single query):
  vector: number[] (required) - The query vector. Must have the same dimensions as your index.
  topK: number (default: 10) - The total number of vectors to receive as a query result. Response is sorted by distance metric score.
  includeMetadata: boolean (default: false) - Whether to include the metadata of the vectors in the response.
  includeVectors: boolean (default: false) - Whether to include the vector values in the response.
  includeData: boolean (default: false) - Whether to include the data of the vectors in the response.
  filter: string (default: "") - Metadata filter to apply.
  weightingStrategy: string (optional) - For sparse/hybrid indexes, specifies weighting strategy for non-zero dimension values. Only 'IDF' (inverse document frequency) is possible.
  fusionAlgorithm: string (optional) - Fusion algorithm for dense and sparse components of a hybrid index. Defaults to 'RRF' (Reciprocal Rank Fusion). Other possible value is 'DBSF' (Distribution-Based Score Fusion).

Request Body (batch query):
  Array of the single query request body fields.

Path Parameters:
  namespace: string (default: "") - The namespace to use. If not specified, the default namespace will be used.
```

--------------------------------

TITLE: Apply IDF Weighting Strategy to Upstash Vector Queries
DESCRIPTION: This code snippet demonstrates how to use the IDF weighting strategy when querying an Upstash Vector index. It requires an initialized Upstash Vector Index client with your REST URL and token. The query will return the top K results, with term importance adjusted by their inverse document frequency.

SOURCE: https://upstash.com/docs/vector/features/sparseindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import WeightingStrategy

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    data="Upstash Vector",
    top_k=5,
    weighting_strategy=WeightingStrategy.IDF,
)
```

LANGUAGE: javascript
CODE:
```
import { Index, WeightingStrategy } from "@upstash/vector";

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
});

await index.query({
  sparseVector: {
    indices: [2, 3],
    values: [0.13, 0.87],
  },
  weightingStrategy: WeightingStrategy.IDF,
  topK: 3,
});
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.QueryData(vector.QueryData{
		Data:              "Upstash Vector",
		TopK:              5,
		WeightingStrategy: vector.WeightingStrategyIDF,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;
use Upstash\Vector\Enums\WeightingStrategy;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->queryData(new DataQuery(
  data: 'Upstash Vector',
  topK: 5,
  weightingStrategy: WeightingStrategy::INVERSE_DOCUMENT_FREQUENCY,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "Upstash Vector", "topK": 5, "weightingStrategy": "IDF"}'
```

--------------------------------

TITLE: Using a Custom Embedding Model (OpenAI) with TypeScript
DESCRIPTION: This snippet illustrates how to integrate a custom embedding model, specifically OpenAI's `text-embedding-ada-002`, with Upstash Vector. It includes functions to generate single and multiple embeddings, and then upsert these into the index. This approach requires generating embeddings client-side before upserting. Dependencies include '@upstash/vector', 'ai', and '@ai-sdk/openai'.

SOURCE: https://upstash.com/docs/vector/integrations/ai-sdk.mdx

LANGUAGE: TypeScript
CODE:
```
import { Index } from '@upstash/vector'
import { embed, embedMany } from 'ai'
import { openai } from '@ai-sdk/openai'

// Configure Upstash Vector client
const index = new Index({
  url: process.env.UPSTASH_VECTOR_REST_URL!,
  token: process.env.UPSTASH_VECTOR_REST_TOKEN!,
})

// Chunking logic: split on period
function generateChunks(input: string): string[] {
  return input
    .trim()
    .split('.')
    .filter(i => i !== '')
}

// Define the embedding model
const embeddingModel = openai.embedding('text-embedding-ada-002')

// Function to generate a single embedding
async function generateEmbedding(value: string): Promise<number[]> {
  const input = value.replaceAll('\n', ' ')
  const { embedding } = await embed({
    model: embeddingModel,
    value: input,
  })
  return embedding
}

// Function to generate embeddings for multiple chunks
async function generateEmbeddings(
  value: string,
): Promise<Array<{ content: string; embedding: number[] }>> {
  const chunks = generateChunks(value)
  const { embeddings } = await embedMany({
    model: embeddingModel,
    values: chunks,
  })
  return embeddings.map((vector, i) => ({
    content: chunks[i],
    embedding: vector,
  }))
}

// Upsert
export async function upsertEmbeddings(resourceId: string, content: string) {
  // Generate embeddings for each chunk
  const chunkEmbeddings = await generateEmbeddings(content)
  // Convert each chunk into an Upstash upsert object
  const toUpsert = chunkEmbeddings.map((chunk, i) => ({
    id: `${resourceId}-${i}`, // e.g. "abc123-0"
    vector: chunk.embedding,
    metadata: {
      resourceId,
      content: chunk.content,
    },
  }))

  await index.upsert(toUpsert)
}

// Query
export async function findRelevantContent(query: string, k = 4) {
  const userEmbedding = await generateEmbedding(query)
  const result = await index.query({
    vector: userEmbedding,
    topK: k,
    includeMetadata: true,
  })

  return result
}
```

--------------------------------

TITLE: Upsert Vectors in Python via Tuple
DESCRIPTION: This Python snippet illustrates how to upsert vectors into an Upstash Vector index using a list of tuples. Each tuple should contain the vector's ID, the vector data (list of floats), optional metadata (dictionary), and optional unstructured data, in that specific order. An initialized `Index` instance from the `upstash_vector` library is required.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/upsert.mdx

LANGUAGE: python
CODE:
```
import random

from upstash_vector import Index

index = Index.from_env()

dimension = 128  # Adjust based on your index's dimension
upsert_amount = 100

vectors = [
    (
        f"generated-id-{i}",
        [random.random() for _ in range(dimension)],
        {"some_field": f"some_value-{i}"},
        f"some-unstructured-data-{i}",
    )
    for i in range(upsert_amount)
]

index.upsert(vectors=vectors)
```

--------------------------------

TITLE: Access Upstash Vector Index for Operations
DESCRIPTION: Access an Upstash Vector index to perform data operations such as fetch. The `index` method allows you to interact with your vector data.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
await index.fetch([....], { includeMetadata: true, includeVectors: true });
```

--------------------------------

TITLE: Perform Text-Based Semantic Search with Upstash Vector
DESCRIPTION: Execute a semantic search using a text query against the Upstash Vector store. The query text is first embedded, and then the similarity search returns the top 'k' most semantically similar documents based on their content.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: python
CODE:
```
# Querying Vectors using a text query
query_text = "What are the effects of global warming?"
query_embedding = embeddings.embed_query(query_text)

# Perform similarity search with the query text
result_text_query = vector_store.similarity_search(
    query=query_text,
    k=5  # Number of top results to return
)

print("Results for text-based similarity search:")
for res in result_text_query:
    print(res.page_content)
```

--------------------------------

TITLE: APIDOC: Upstash Vector Index Info Response Schema
DESCRIPTION: This section defines the structure of the response object returned when querying for index information. It includes details such as the total number of vectors, pending vectors, index size, dimension, similarity function, and a map of namespaces with their respective vector counts.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/info.mdx

LANGUAGE: APIDOC
CODE:
```
Response:
  vectorCount: number (required) - The total number of vectors in the index, that are ready to use.
  pendingVectorCount: number (required) - The number of vectors in the index, that is still processing and not ready to use.
  indexSize: number (required) - The size of the index, in `b`.
  dimension: number (required) - Dimension of the vectors.
  similarityFunction: string (required) - Name of the similarity function used in indexing and queries.
  namespaces: Record<string, Object> (required) - A map of namespaces to their information.
    namespaces properties:
      vectorCount: number (required) - The total number of vectors in the namespace, that are ready to use.
      pendingVectorCount: number (required) - The number of vectors in the namespace, that is still processing and not ready to use.
```

--------------------------------

TITLE: Python: Create an Asynchronous Resumable Query
DESCRIPTION: Create an asynchronous resumable query instance using the `resumable_query` method of the `AsyncIndex` class. This is suitable for non-blocking operations and follows the same parameter structure as the synchronous version.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
query = await async_index.resumable_query(
  vector=[0.1, 0.2],
  top_k=2,
  include_metadata=True,
  include_vectors=True,
  namespace='your_namespace'
)
```

--------------------------------

TITLE: BM25 Algorithm Formula
DESCRIPTION: This snippet presents the mathematical formula for the BM25 algorithm used in Upstash Vector. It details the components such as term frequency, inverse document frequency, document length, and the parameters k1 and b, which are crucial for understanding how relevance is calculated.

SOURCE: https://upstash.com/docs/vector/features/sparseindexes.mdx

LANGUAGE: Math
CODE:
```
                       IDF(qᵢ) * f(qᵢ, D) * (k₁ + 1)
BM25(D, Q) = Σ ----------------------------------------------
               f(qᵢ, D) + k₁ * (1 - b + b * (|D| / avg(|D|)))
```

--------------------------------

TITLE: API Reference for Range Vectors
DESCRIPTION: This section provides the API documentation for ranging over vectors in Upstash Vector. It details the HTTP method, endpoint, authentication, request body parameters, path parameters, and the structure of the successful response.

SOURCE: https://upstash.com/docs/vector/api/endpoints/range.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://{endpoint}/range/{namespace}

Authentication: Bearer Token (GET method)

Request Body Parameters:
- "cursor": string (required) - The offset to the last retrieved vector. Set to "0" for initial range.
- "prefix": string (optional) - Prefix of the vector IDs to range over.
- "limit": number (required) - Maximum number of vectors to return in the response (page size).
- "includeMetadata": boolean (optional, default: false) - Whether to include vector metadata in the response. Recommended to set to true.
- "includeVectors": boolean (optional, default: false) - Whether to include vector values in the response. Recommended to set to false.
- "includeData": boolean (optional, default: false) - Whether to include unstructured data of vectors in the response.

Path Parameters:
- "namespace": string (optional, default: "") - The namespace to use. If not specified, the default namespace is used.

Response (200 OK):
- "nextCursor": string (required) - The offset for the next range. Use this in the 'cursor' field for subsequent requests. Empty string if no more vectors.
- "vectors": Object[] (required) - Array of vector objects.
  - "id": string (required) - The ID of the vector.
  - "vector": number[] (optional) - The dense vector value.
  - "sparseVector": Object[] (optional) - The sparse vector value.
    - "indices": number[] (required) - Indices of non-zero valued dimensions.
    - "values": number[] (required) - Values of non-zero valued dimensions.
  - "metadata": Object (optional) - The metadata of the vector.
  - "data": string (optional) - The unstructured data of the vector.
```

--------------------------------

TITLE: SQL: Apply Less Than Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'less than' operator. It is applicable only to number values in metadata. Multiple conditions can be combined using boolean operators like OR.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
population < 20000000 OR geography.coordinates.longitude < 30.0
```

--------------------------------

TITLE: Python: Update Vector Data and Metadata
DESCRIPTION: This Python snippet demonstrates how to update a vector's metadata and data using the 'update' method. It requires an initialized Upstash Vector Index client. The 'id' parameter specifies the target vector, and 'metadata' and 'data' provide the new values. The method returns a boolean indicating success.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/update.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index.from_env()

updated = index.update(
    id="id1",
    metadata={"new": "metadata"},
    data="new-data",
)

print(updated)
```

--------------------------------

TITLE: SQL: Apply Equals Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'equals' operator. It can be applied to string, number, and boolean metadata values to match exact literals. Multiple conditions can be combined using boolean operators like AND.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
country = 'Turkey' AND population = 15460000 AND is_capital = false
```

--------------------------------

TITLE: Fetch Vectors API Reference
DESCRIPTION: This API endpoint allows you to retrieve vectors from your Upstash Vector database. You can specify vector IDs or an ID prefix to fetch, and optionally include metadata, vector values, or unstructured data in the response. By default, vectors are fetched from the default namespace, but a different namespace can be specified in the path.

SOURCE: https://upstash.com/docs/vector/api/endpoints/fetch.mdx

LANGUAGE: APIDOC
CODE:
```
GET https://{endpoint}/fetch/{namespace}

Request Body:
  ids: string[] - Array of vector IDs to fetch.
  prefix: string - Prefix of vector IDs to fetch (max 1000 vectors returned).
  includeMetadata: boolean = false - Whether to include vector metadata.
  includeVectors: boolean = false - Whether to include vector values.
  includeData: boolean = false - Whether to include unstructured data.

Path Parameters:
  namespace: string = "" - The namespace to use. Default namespace is used if not specified.

Response (200 OK):
  Vectors: Object[] - Array of vectors, ordered by provided IDs. Null if vector not found.
    id: string (required) - The ID of the vector.
    vector: number[] - Dense vector value (for dense/hybrid indexes).
    sparseVector: Object[] - Sparse vector value (for sparse/hybrid indexes).
      indices: number[] - Indices of non-zero dimensions.
      values: number[] - Values of non-zero dimensions.
    metadata: Object - Vector metadata.
    data: string - Unstructured data of the vector.
```

--------------------------------

TITLE: Python: Fetch Multiple Upstash Vectors by ID
DESCRIPTION: This Python snippet demonstrates how to fetch multiple vectors from an Upstash Vector index using a list of IDs. It configures the fetch operation to include both the vector data and associated metadata in the results. The output iterates through and prints the ID, vector, metadata, and data for each retrieved vector.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/fetch.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index.from_env()

# Specify the identifiers of vectors to be fetched
ids_to_fetch = ["id-1", "id-2", "id-3"]

# Fetch the specified vectors with vectors and metadata included
fetch_result = index.fetch(
    ids=ids_to_fetch,
    include_vectors=True,
    include_metadata=True,
    include_data=True,
)

# Display the fetched vectors
for vector_info in fetch_result:
    print("ID:", vector_info.id)
    print("Vector:", vector_info.vector)
    print("Metadata:", vector_info.metadata)
    print("Data:", vector_info.data)
```

--------------------------------

TITLE: Configure Batch Processing for Upstash Vector
DESCRIPTION: Optimize the efficiency of document processing and storage in Upstash Vector by adjusting the `batch_size` and `embedding_chunk_size` parameters. These parameters control how documents are grouped and processed, impacting performance and resource usage.

SOURCE: https://upstash.com/docs/vector/tutorials/gradio-application.mdx

LANGUAGE: Python
CODE:
```
# Example of setting batch_size and embedding_chunk_size (conceptual)
# from upstash_vector import UpstashVectorStore

# vector_store = UpstashVectorStore(
#     url="YOUR_UPSTASH_VECTOR_URL",
#     token="YOUR_UPSTASH_VECTOR_TOKEN",
#     batch_size=100, # Example batch size
#     embedding_chunk_size=500 # Example embedding chunk size
# )
```

--------------------------------

TITLE: Python: Fetch More Synchronous Results
DESCRIPTION: Retrieve additional results from an ongoing resumable query. The `fetch_next()` method takes the desired number of results as an argument and returns a list of new results. If no more results are available, an empty list is returned.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
next_results = query.fetch_next(number_of_results)
```

--------------------------------

TITLE: Perform Vector-Based Semantic Search with Upstash Vector
DESCRIPTION: Perform a semantic search directly using a pre-computed query embedding against the Upstash Vector store. This method allows for querying based on the similarity of the vector itself, returning the top 'k' most similar documents.

SOURCE: https://upstash.com/docs/vector/tutorials/huggingface-embeddings.mdx

LANGUAGE: python
CODE:
```
# Querying Vectors using a vector directly
result_vector_query = vector_store.similarity_search_by_vector(
    embedding=query_embedding,
    k=5
)

print("Results for vector-based similarity search:")
for res in result_vector_query:
    print(res.page_content)
```

--------------------------------

TITLE: Resume Upstash Vector Query API Reference
DESCRIPTION: This API endpoint allows you to resume a previously initiated resumable query to retrieve more results. It requires the unique identifier from the initial query and the number of additional results to fetch. The response provides a list of scored vectors, including their IDs, similarity scores, and optional vector data or metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/resumable-query/resume.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/resumable-query-next
Authorization: bearer

Request:
  uuid: string (required) - The unique identifier returned from the start resumable query request.
  additionalK: number (required) - The number of additional results to fetch.

Response:
  Scores: Object[]
    id: string (required) - The id of the vector.
    score: number (required) - The similarity score of the vector, calculated based on the distance metric of your index.
    vector: number[] (optional) - The dense vector value for dense and hybrid indexes.
    sparseVector: Object[] (optional) - The sparse vector value for sparse and hybrid indexes.
      indices: number[] - Indices of the non-zero valued dimensions.
      values: number[] - Values of the non-zero valued dimensions.
    metadata: Object (optional) - The metadata of the vector, if any.
    data: string (optional) - The unstructured data of the vector, if any.
```

--------------------------------

TITLE: Upsert Vectors with Python
DESCRIPTION: This Python snippet demonstrates how to upsert vectors into your Upstash Vector index. It uses the `requests` library to make a POST request to the `/vectors` endpoint, sending a list of vector objects with IDs, vector arrays, and optional metadata. Ensure you replace `YOUR_UPSTASH_VECTOR_TOKEN` and `YOUR_UPSTASH_VECTOR_URL` with your actual credentials.

SOURCE: https://upstash.com/docs/vector/overall/llms-txt.mdx

LANGUAGE: Python
CODE:
```
import requests
import os

UPSTASH_VECTOR_URL = os.getenv("UPSTASH_VECTOR_URL")
UPSTASH_VECTOR_TOKEN = os.getenv("UPSTASH_VECTOR_TOKEN")

headers = {
    "Authorization": f"Bearer {UPSTASH_VECTOR_TOKEN}",
    "Content-Type": "application/json"
}

vectors_to_upsert = [
    {
        "id": "vec1",
        "vector": [0.1, 0.2, 0.3, 0.4],
        "metadata": {"genre": "fiction"}
    },
    {
        "id": "vec2",
        "vector": [0.5, 0.6, 0.7, 0.8],
        "metadata": {"genre": "non-fiction"}
    }
]

try:
    response = requests.post(f"{UPSTASH_VECTOR_URL}/vectors", json=vectors_to_upsert, headers=headers)
    response.raise_for_status() # Raise an exception for HTTP errors
    print("Vectors upserted successfully:", response.json())
except requests.exceptions.RequestException as e:
    print(f"Error upserting vectors: {e}")
```

--------------------------------

TITLE: Upserting Sparse Vectors
DESCRIPTION: This section introduces the methods available for upserting sparse vectors into Upstash Vector indexes. It indicates that there are two distinct ways to perform this operation, which will be detailed in subsequent documentation.

SOURCE: https://upstash.com/docs/vector/features/sparseindexes.mdx

LANGUAGE: English
CODE:
```
You can upsert sparse vectors into Upstash Vector indexes in two different ways.
```

--------------------------------

TITLE: Upsert Data with Upstash Vector Embedding Models
DESCRIPTION: This code snippet demonstrates how to upsert raw text data into an Upstash Vector index after it has been initialized with an embedding model. It requires your Upstash Vector REST URL and token for authentication. The operation inserts a data point with an ID, the text content, and optional metadata.

SOURCE: https://upstash.com/docs/vector/features/embeddingmodels.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.upsert(
    [('id-0', 'Upstash is a serverless data platform.', {'field': 'value'})],
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.upsert({
  id: "id-0",
  data: "Upstash is a serverless data platform.",
  metadata: {
    field: "value",
  },
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.UpsertData(vector.UpsertData{
		Id:       "id-0",
		Data:     "Upstash is a serverless data platform.",
		Metadata: map[string]any{"field": "value"},
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->upsertData(new DataUpsert(
  id: 'id-0',
  data: 'Upstash is a serverless data platform.',
  metadata: [
    'field' => 'value',
  ],
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/upsert-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"id": "1", "data": "Upstash is a serverless data platform.", "metadata": {"field": "value"}}'
```

--------------------------------

TITLE: SQL: Apply Less Than or Equals Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'less than or equals' operator. It is applicable only to number values in metadata. Multiple conditions can be combined using boolean operators like OR.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
population <= 20000000 OR geography.coordinates.longitude <= 30.0
```

--------------------------------

TITLE: Execute Upstash Vector Batch Data Query with cURL
DESCRIPTION: This snippet illustrates how to perform a batch data query against the Upstash Vector API using cURL. It sends a POST request with an array of JSON objects, where each object represents an individual query with its own data, topK, and includeMetadata parameters.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: sh
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '[
        {
          "data": "What is Upstash?",
          "topK": 2,
          "includeMetadata": true
        },
        {
          "data": "What is Upstash Vector?",
          "topK": 3
        }
      ]'
```

--------------------------------

TITLE: Upsert Method API Reference
DESCRIPTION: This section defines the 'upsert' method, its accepted payloads, and the expected response. It supports two main input types: 'VectorPayload' for pre-computed vectors and 'DataPayload' for raw data to be embedded. Both can include optional metadata and a namespace.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/upsert.mdx

LANGUAGE: APIDOC
CODE:
```
interface VectorPayload {
  id: string | number; // The ID of the vector
  vector: number[]; // The vectors to add to the store
  metadata?: Record<string, unknown>; // Metadata of the vector
}

interface DataPayload {
  id: string | number; // The ID of the vector
  data: string; // The data to create embeddings from
  metadata?: Record<string, unknown>; // Metadata of the vector
}

interface NamespacePayload {
  namespace?: string; // Namespace to upsert to. If not set, default namespace is used.
}

// Method Signature
upsert(payload: VectorPayload | VectorPayload[] | DataPayload | DataPayload[], options?: NamespacePayload): Promise<'Success'>;
```

--------------------------------

TITLE: Reset All Upstash Vector Namespaces (PHP)
DESCRIPTION: This snippet shows how to clear all namespaces within an Upstash Vector index by calling the `resetAll()` method. This action will remove all data across all namespaces associated with the index. Ensure you have your Upstash Vector REST URL and token configured.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/reset.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->resetAll();
```

--------------------------------

TITLE: Python: Split Documents into Chunks with LangChain
DESCRIPTION: This snippet uses LangChain's CharacterTextSplitter to divide a collection of documents into smaller, manageable chunks. This is crucial for optimizing vector database performance and search relevance. The chunk_size and chunk_overlap parameters control the size of each chunk and the amount of shared content between consecutive chunks.

SOURCE: https://upstash.com/docs/vector/tutorials/langchain.mdx

LANGUAGE: python
CODE:
```
text_splitter = CharacterTextSplitter(chunk_size=1000, chunk_overlap=0)
docs = text_splitter.split_documents(documents)
```

--------------------------------

TITLE: Upstash Vector QueryResult Response Structure
DESCRIPTION: This API documentation describes the structure of the QueryResult object returned by the Upstash Vector query operation. It outlines the properties available in each result, including ID, score, optional vector data, sparse vector data, metadata, and raw data, depending on the query parameters.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/query.mdx

LANGUAGE: APIDOC
CODE:
```
Response: QueryResult
  id: string | number (required)
    The ID of the resulting vector.
  score: number (required)
    The score of the vector data, calculated based on the distance metric of your index.
  vector: number[] (optional)
    The resulting vector (if `includeVectors` is set to true)
  sparseVector: SparseVector (optional)
    The resulting sparseVector (if `includeVectors` is set to true)
  metadata: Record<string, unknown> (optional)
    The metadata of the vector (if `includeMetadata` is set to true)
  data: string (optional)
    The data of the vector (if `includeData` is set to true)
```

--------------------------------

TITLE: Access Upstash Vector Index with Metadata Typing
DESCRIPTION: Access an Upstash Vector index and apply TypeScript type-checking to metadata by passing a type parameter to the `index()` method. This ensures type safety when interacting with metadata fields after querying.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
type Metadata = {
  title: string,
  genre: 'sci-fi' | 'fantasy' | 'horror' | 'action'
}

await index.upsert([{
  id: '1234',
  vector: [
    .... // embedding values
  ],
  metadata: {
    title: 'Lord of The Rings',
    genre: 'drama',
    category: 'classic'
  }
}])

const results = await index.query<Metadata>({
  vector: [
    ... // query embedding
  ],
  includeVectors: true,
  topK: 1,
})

if (results[0].metadata) {
  // Since we passed the Metadata type parameter above,
  // we can interact with metadata fields without having to
  // do any typecasting.
  const { title, genre, category } = results[0].metadata;
  console.log(`The best match in fantasy was ${title}`)
}
```

--------------------------------

TITLE: APIDOC: Dot Product Similarity Function
DESCRIPTION: Describes the Dot Product function, which measures similarity by multiplying corresponding components and summing results. It provides a measure of alignment between vectors, requiring vectors to be normalized to unit length. Useful in Machine Learning Models and Collaborative Filtering. The score is normalized between 0 and 1.

SOURCE: https://upstash.com/docs/vector/features/similarityfunctions.mdx

LANGUAGE: APIDOC
CODE:
```
Function: Dot Product
Description: Measures the similarity by multiplying the corresponding components of two vectors and summing the results. Vectors must be normalized to unit length.
Use Cases:
- Machine Learning Models: Sentiment analysis or classification.
- Collaborative Filtering: Recommending items based on user behavior or preferences.
Score Calculation: (1 + dot_product(v1, v2)) / 2
Normalized Score: 0 to 1 (1 indicates highest similarity)
```

--------------------------------

TITLE: Execute Upstash Vector Data Query with cURL
DESCRIPTION: This code snippet demonstrates how to perform a data query against the Upstash Vector API using cURL. It sends a POST request with a JSON payload containing the data to query, the number of top results to retrieve (topK), and an option to include metadata.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: sh
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{ "data": "What is Upstash?", "topK": 2, "includeMetadata": true }'
```

--------------------------------

TITLE: Upsert Data API Reference
DESCRIPTION: This section details the API endpoint for upserting data into an Upstash Vector index. It describes the request method, URL, authentication, and the structure of the request body and response.

SOURCE: https://upstash.com/docs/vector/api/endpoints/upsert-data.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/upsert-data/{namespace}
Auth: Bearer Token

Request Body (single data):
{
  "id": "string" (required, The id of the vector.)
  "data": "string" (required, The raw text data to embed and upsert.)
  "metadata": "Object" (optional, The metadata of the vector. This makes identifying vectors on retrieval easier and can be used to with filters on queries.)
}

Request Body (multiple data):
[
  {
    "id": "string" (required, The id of the vector.)
    "data": "string" (required, The raw text data to embed and upsert.)
    "metadata": "Object" (optional, The metadata of the vector. This makes identifying vectors on retrieval easier and can be used to with filters on queries.)
  }
]

Path Parameters:
  namespace: "string" (optional, default: "", The namespace to use. When no namespace is specified, the default namespace will be used.)

Response (200 OK):
{
  "result": "Success" (string)
}

Response (422 Unprocessable Entity):
{
  "error": "Embedding data for this index is not allowed. The index must be created with an embedding model to use it.",
  "status": 422
}
```

--------------------------------

TITLE: Python: Fetch More Asynchronous Results
DESCRIPTION: Retrieve additional results from an ongoing asynchronous resumable query. The `async_fetch_next()` method takes the desired number of results and returns a list of new results, or an empty list if no more are available.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
next_results = await query.async_fetch_next(number_of_results)
```

--------------------------------

TITLE: Python: Handle ClientError After Stopping Query
DESCRIPTION: Demonstrates how attempting to interact with a resumable query after it has been stopped will raise a `ClientError`. This applies to both synchronous and asynchronous `fetch_next` and `stop` calls, ensuring proper resource management.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/resumable-query.mdx

LANGUAGE: python
CODE:
```
with pytest.raises(ClientError):
  query.fetch_next(1)
  query.async_fetch_next(1)

for async with pytest.raises(ClientError):
  query.stop() # or await query.async_stop() for async
```

--------------------------------

TITLE: Filter Upstash Vector Query Results by Metadata
DESCRIPTION: This code demonstrates how to refine Upstash Vector query results by applying a metadata filter. The 'filter' parameter uses a SQL-like syntax (e.g., 'url GLOB "*imgur.com*"') to match specific metadata values. This allows for more precise searches based on the context stored with your vectors.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    [0.9215, 0.3897],
    top_k=5,
    include_metadata=True,
    filter="url GLOB '*imgur.com*'",
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({
  vector: [0.9215, 0.3897],
  topK: 5,
  includeMetadata: true,
  filter: "url GLOB '*imgur.com*'",
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex("UPSTASH_VECTOR_REST_URL", "UPSTASH_VECTOR_REST_TOKEN")

	index.Query(vector.Query{
		Vector:          []float32{0.9215, 0.3897},
		TopK:            5,
		IncludeMetadata: true,
		Filter:          "url GLOB '*imgur.com*'",
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
```

--------------------------------

TITLE: Query Upstash Vector with Text Data
DESCRIPTION: This snippet illustrates how to query Upstash Vector using raw text data. If the sparse index was created with an Upstash-hosted sparse embedding model, the service will automatically embed the text data before performing the query. This simplifies the process by abstracting the embedding step.

SOURCE: https://upstash.com/docs/vector/features/sparseindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    data="Upstash Vector",
    top_k=5,
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query(
  {
    data: "Upstash Vector",
    topK: 1,
  },
)
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.QueryData(vector.QueryData{
		Data: "Upstash Vector",
		TopK: 5,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->queryData(new DataQuery(
  data: 'Upstash Vector',
  topK: 5,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "Upstash Vector", "topK": 5}'
```

--------------------------------

TITLE: Implement DBSF for Hybrid Index Queries in Upstash Vector
DESCRIPTION: This code demonstrates how to perform a hybrid index query using the Distribution-Based Score Fusion (DBSF) algorithm. DBSF normalizes scores from dense and sparse indexes based on their statistical distribution, then combines them to produce a final ranking. This method is more sensitive to score variations than RRF.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import FusionAlgorithm, SparseVector

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    vector=[0.5, 0.4],
    sparse_vector=SparseVector([3, 5], [0.3, 0.5]),
    fusion_algorithm=FusionAlgorithm.DBSF,
)
```

LANGUAGE: javascript
CODE:
```
import { FusionAlgorithm, Index } from "@upstash/vector";

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
});

await index.query({
  vector: [0.5, 0.4],
  sparseVector: {
    indices: [2, 3],
    values: [0.13, 0.87],
  },
  fusionAlgorithm: FusionAlgorithm.DBSF,
  topK: 3,
});
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.Query(vector.Query{
		Vector: []float32{0.5, 0.4},
		SparseVector: &vector.SparseVector{
			Indices: []int32{3, 5},
			Values:  []float32{0.3, 05},
		},
		FusionAlgorithm: vector.FusionAlgorithmDBSF,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;
use Upstash\Vector\Enums\FusionAlgorithm;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
  vector: [0.5, 0.4],
  sparseVector: new SparseVector(
    indices: [3, 5],
    values: [0.3, 0.5],
  ),
  topK: 5,
  includeMetadata: true,
  fusionAlgorithm: FusionAlgorithm::DISTRIBUTION_BASED_SCORE_FUSION,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector": [0.5, 0.4], "sparseVector": {"indices": [3, 5], "values": [0.3, 0.5]}, "fusionAlgorithm": "DBSF"}'
```

--------------------------------

TITLE: Query Upstash Vector Index with Vector Values
DESCRIPTION: Query an Upstash Vector index using a vector value and specify options like `topK`, `includeVectors`, and `includeMetadata`. The dimension of the query vector must match the index's dimension.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
type QueryOptions = {
  vector: number[];
  topK: number;
  includeVectors?: boolean;
  includeMetadata?: boolean;
};
```

LANGUAGE: typescript
CODE:
```
> await index.query({ topK: 3, vector: [ ... ]})
{
  matches: [
    {
      id: '6345',
      score: 1.00000012,
      vector: [],
      metadata: undefined
    },
    {
      id: '1233',
      score: 1.00000012,
      vector: [],
      metadata: undefined
    },
    {
      id: '4142',
      score: 1.00000012,
      vector: [],
      metadata: undefined
    }
  ],
  namespace: ''
}
```

--------------------------------

TITLE: Upsert Vectors in Python with Namespace
DESCRIPTION: This Python snippet shows how to specify a namespace when performing an upsert operation on an Upstash Vector index. By default, operations occur in the default namespace; providing the `namespace` argument directs the upsert to a specific namespace. This requires an initialized `Index` instance and the vectors to be upserted.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/upsert.mdx

LANGUAGE: python
CODE:
```
index.upsert(..., namespace="ns")
```

--------------------------------

TITLE: APIDOC: ResumableQueryResponse Object Definition
DESCRIPTION: Defines the structure of the ResumableQueryResponse object returned by Upstash Vector's resumable query. It includes the initial query results, a function to fetch more results, and a function to stop the query and release resources.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: APIDOC
CODE:
```
ResumableQueryResponse: Object
  result: QueryResult[] (required)
    The initial query results.
  fetchNext: (additionalK: number) => Promise<Vector[]> (required)
    A function to fetch the next batch of results.
  stop: () => Promise<string> (required)
    A function to stop the resumable query and release resources.
```

--------------------------------

TITLE: APIDOC: Upstash Vector Index Reset Method
DESCRIPTION: Defines the `reset` method for the Upstash Vector index, including its arguments and expected response. This method is used to clear data from namespaces.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/reset.mdx

LANGUAGE: APIDOC
CODE:
```
interface UpstashVectorIndex {
  reset(options?: {
    namespace?: string; // Specifies a namespace to reset. Leave empty for the default namespace.
    all?: true; // Whether to reset all namespaces. Can only be set to `true`.
  }): Promise<'Success'>;
}
```

--------------------------------

TITLE: Upsert Multiple Vectors in PHP
DESCRIPTION: This code snippet shows how to efficiently upsert multiple vectors into an Upstash Vector index using the `upsertMany()` method. It requires the Upstash Vector SDK and a configured Index instance. Multiple VectorUpsert objects are passed in an array to the method.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-vectors.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

use function Upstash\Vector\createRandomVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->upsertMany([
  new VectorUpsert(
    id: '1',
    vector: createRandomVector(dimensions: 1536)
  ),
  new VectorUpsert(
    id: '2',
    vector: createRandomVector(dimensions: 1536)
  ),
]);
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

use function Upstash\Vector\createRandomVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->upsertMany([
  new VectorUpsert(
    id: '1',
    vector: createRandomVector(dimensions: 1536)
  ),
  new VectorUpsert(
    id: '2',
    vector: createRandomVector(dimensions: 1536)
  ),
]);
```

--------------------------------

TITLE: Upsert Single Data Point with PHP Embedding Model
DESCRIPTION: Use the `upsertData()` method to insert a single data point into your Upstash Vector index. The embedding model configured for the index will automatically generate the vector embedding. This requires an initialized Upstash Vector Index instance.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-data.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->upsertData(new DataUpsert(
  id: '1',
  data: 'The capital of Japan is Tokyo',
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->upsertData(new DataUpsert(
  id: '1',
  data: 'The capital of Japan is Tokyo',
));
```

--------------------------------

TITLE: SQL: Apply Greater Than Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'greater than' operator. It is applicable only to number values in metadata. Multiple conditions can be combined using boolean operators like OR.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
population > 10000000 OR geography.coordinates.latitude > 39.5
```

--------------------------------

TITLE: Query Hybrid Indexes with Text Data for Reranking
DESCRIPTION: This snippet demonstrates how to query hybrid indexes using text data with Upstash-hosted embedding models. It shows how to perform queries over only dense and only sparse components by embedding text data into respective vectors. This allows for custom reranking of semantically similar dense results and exact sparse matches.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: Python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import SparseVector, QueryMode

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

dense_results = index.query(
    data="Upstash Vector",
    query_mode=QueryMode.DENSE,
)

sparse_results = index.query(
    data="Upstash Vector",
    query_mode=QueryMode.SPARSE,
)

# Rerank dense and sparse results as you like here
```

LANGUAGE: JavaScript
CODE:
```
import { Index, QueryMode } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

const denseResults = await index.query({
  data: "Upstash Vector",
  queryMode: QueryMode.DENSE,
})

const sparseResults = await index.query({
  data: "Upstash Vector",
  queryMode: QueryMode.SPARSE,
})

// Rerank dense and sparse results as you like here
```

LANGUAGE: Go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	denseScores, err := index.QueryData(vector.QueryData{
		Data:      "Upstash Vector",
		QueryMode: vector.QueryModeDense,
	})

	sparseScores, err := index.QueryData(vector.QueryData{
		Data:      "Upstash Vector",
		QueryMode: vector.QueryModeSparse,
	})

	// Rerank dense and sparse results as you like here
}
```

LANGUAGE: PHP
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;
use Upstash\Vector\Enums\QueryMode;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$denseResults = $index->queryData(new DataQuery(
  data: 'Upstash Vector',
  topK: 3,
  queryMode: QueryMode::DENSE,
));

$sparseResults = $index->queryData(new DataQuery(
  data: 'Upstash Vector',
  topK: 3,
  queryMode: QueryMode::SPARSE,
));

// Rerank dense and sparse results as you like here
```

LANGUAGE: curl
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "Upstash Vector", "queryMode": "DENSE"}'

curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "Upstash Vector", "queryMode": "SPARSE"}'
```

--------------------------------

TITLE: SQL: Apply Greater Than or Equals Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'greater than or equals' operator. It is applicable only to number values in metadata. Multiple conditions can be combined using boolean operators like OR.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
population >= 10000000 OR geography.coordinates.latitude >= 39.5
```

--------------------------------

TITLE: Fetch Vectors by ID in TypeScript
DESCRIPTION: This code snippet demonstrates how to fetch vectors using a list of IDs. The response will be an array of objects, each containing the ID of the fetched vector. If a vector is not found, its corresponding entry in the array will be null.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/fetch.mdx

LANGUAGE: typescript
CODE:
```
await index.fetch(["2", "3"]);
// [{ id: "2" }, { id: "3" }]
```

--------------------------------

TITLE: Fetch Records by IDs from Upstash Vector Index
DESCRIPTION: Fetch one or more records from the Upstash Vector index by providing a list of their unique IDs. The method returns the records corresponding to the provided IDs.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
const fetchResult = await index.fetch(["id-1", "id-2"]);
```

--------------------------------

TITLE: SQL: Apply Not Equals Operator in Metadata Filter
DESCRIPTION: This SQL-like filter syntax demonstrates the 'not equals' operator. It can be applied to string, number, and boolean metadata values to exclude exact literals. Multiple conditions can be combined using boolean operators like AND.

SOURCE: https://upstash.com/docs/vector/features/filtering.mdx

LANGUAGE: sql
CODE:
```
country != 'Germany' AND population != 12500000 AND is_capital != true
```

--------------------------------

TITLE: Upsert Sparse Vectors in PHP
DESCRIPTION: This code snippet illustrates how to upsert sparse vectors into an Upstash Vector index. Sparse indexes require a `SparseVector` object containing `indices` and `values`. It uses the `upsert()` method with the `sparseVector` parameter, requiring the Upstash Vector SDK and a configured Index instance.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-vectors.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->upsert(new VectorUpsert(
  id: '1',
  sparseVector: new SparseVector(
    indices: [0, 1],
    values: [1.0, 2.0],
  ),
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->upsert(new VectorUpsert(
  id: '1',
  sparseVector: new SparseVector(
    indices: [0, 1],
    values: [1.0, 2.0],
  ),
));
```

--------------------------------

TITLE: Perform Custom Reranking with Upstash Vector Hybrid Indexes
DESCRIPTION: This Python code demonstrates how to query dense and sparse components of a hybrid index separately to enable custom reranking. By obtaining results from each component independently, users can apply external reranker models or algorithms (e.g., bge-reranker-v2-m3) to combine and reorder the results according to specific use case requirements.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import SparseVector

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

dense_results = index.query(
    vector=[0.5, 0.4],
)

sparse_results = index.query(
    sparse_vector=SparseVector([3, 5], [0.3, 0.5]),
)

```

--------------------------------

TITLE: Python: Representing Dense vs. Sparse Vectors
DESCRIPTION: This snippet illustrates the difference in representation between dense and sparse vectors. Dense vectors have many non-zero values, while sparse vectors use two arrays: one for the indices of non-zero dimensions and another for their corresponding values, significantly reducing storage for high-dimensional data with many zeros.

SOURCE: https://upstash.com/docs/vector/features/sparseindexes.mdx

LANGUAGE: python
CODE:
```
dense = [0.1, 0.3, , ...thousands of non-zero values..., 0.5, 0.2]

sparse = (
    [23, 42, 5523, 123987, 240001], # some low number of dimension indices
    [0.1, 0.3, 0.1, 0.2, 0.5], # non-zero values corresponding to dimensions
)
```

--------------------------------

TITLE: Upstash Vector Delete Method API Reference
DESCRIPTION: This API documentation details the 'delete' method for the Upstash Vector index. It outlines the various ways to specify vectors for deletion (by IDs, prefix, or metadata filter), the optional namespace parameter, and the structure of the successful deletion response, including the count of deleted vectors.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/delete.mdx

LANGUAGE: APIDOC
CODE:
```
method: delete
arguments:
  - name: IDs
    type: string[] | number[] | string | number
    required: true
    description: One or more vector IDs to delete.
  - name: DeletePayload
    type: object
    required: true
    description: You can only use one of the `ids`, `prefix`, or `filter` fields.
    properties:
      - name: ids
        type: string[] | number[] | string | number
        description: One or more vector IDs to delete.
      - name: prefix
        type: string
        description: A string prefix to match vector IDs for deletion. All vectors with IDs starting with this prefix will be deleted.
      - name: filter
        type: string
        description: A metadata filter for vector deletion. See Metadata Filtering for more information. Deleting vectors with metadata filter is a O(N) operation that performs a full scan. Therefore, it might be slow for large indexes.
  - name: Options
    type: DeleteCommandOptions
    properties:
      - name: namespace
        type: string
        description: Namespace to delete from. If not set, default namespace is used.
response:
  - name: Response
    type: DeleteResult
    required: true
    properties:
      - name: deleted
        type: number
        required: true
        description: The number of vectors that were successfully deleted.
```

--------------------------------

TITLE: Upsert a Single Vector in PHP
DESCRIPTION: This code snippet demonstrates how to upsert a single vector into an Upstash Vector index using the `upsert()` method. It requires the Upstash Vector SDK and a configured Index instance with your REST URL and token. The vector is created with random dimensions.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-vectors.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

use function Upstash\Vector\createRandomVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->upsert(new VectorUpsert(
  id: '1',
  vector: createRandomVector(dimensions: 1536)
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpsert;

use function Upstash\Vector\createRandomVector;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->upsert(new VectorUpsert(
  id: '1',
  vector: createRandomVector(dimensions: 1536)
));
```

--------------------------------

TITLE: Query Upstash Vector with Text Data
DESCRIPTION: This code snippet demonstrates how to query an Upstash Vector index using raw text data. Upstash automatically embeds the text using its hosted dense and sparse embedding models before performing the query. Ensure you have your Upstash Vector REST URL and token configured.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    data="Upstash Vector",
    top_k=5,
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query(
  {
    data: "Upstash Vector",
    topK: 1,
  },
)
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.QueryData(vector.QueryData{
		Data: "Upstash Vector",
		TopK: 5,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataQuery;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->queryData(new DataQuery(
  data: 'Upstash Vector',
  topK: 5,
  includeMetadata: true,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query-data \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"data": "Upstash Vector", "topK": 5}'
```

--------------------------------

TITLE: Upsert Records into Upstash Vector Index
DESCRIPTION: Upsert single or multiple records into an Upstash Vector index. Records must conform to the `UpstashRecord` type, including an ID, vector, and optional metadata.

SOURCE: https://upstash.com/docs/vector/sdks/ts/overview-backup.mdx

LANGUAGE: typescript
CODE:
```
type UpstashRecord = {
  id: number | string;
  vector: number[];
  metadata?: Record<string, unknown>;
};

// Upsert multiple records
await index.upsert([...]);

// Upsert a single record
await index.upsert({...});
```

--------------------------------

TITLE: APIDOC: ResumableQuery Method Reference
DESCRIPTION: This API documentation describes the `resumableQuery` method, which allows for performing queries that can be resumed to fetch additional results, useful for large result sets or pagination. The dimension of the query vector must match the index dimension. Scores returned are normalized between 0 and 1.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: APIDOC
CODE:
```
method: resumableQuery
  description: Allows performing queries that can be resumed to fetch additional results.
  arguments:
    Payload: 
      type: ResumableQueryPayload
      required: true
      properties:
        vector | sparseVector | data:
          type: number[] | SparseVector | string
          required: true
          description: The query data/vector to search for in the index. Can be a pre-created vector (dense or sparse) or raw data for Upstash Embedding.
        topK:
          type: number
          required: true
          description: The initial number of vectors to retrieve, sorted by distance metric score.
        includeMetadata:
          type: boolean
          description: Whether to include the metadata of the vectors in the response. Recommended for easier vector identification.
        includeVectors:
          type: boolean
          description: Whether to include the vector values in the response.
        includeData:
          type: boolean
          description: Whether to include the data field in the response.
        filter:
          type: string
          description: Metadata filtering string to narrow down query results. Refer to Metadata Filtering documentation for syntax.
        weightingStrategy:
          type: WeightingStrategy
          description: For sparse vectors, the weighting strategy to use when querying matching non-zero dimension values. If not provided, no weighting is used.
        fusionAlgorithm:
          type: FusionAlgorithm
          description: Fusion algorithm to use for fusing scores from dense and sparse components of a hybrid index. Defaults to `RRF` if not provided.
        queryMode:
          type: QueryMode
          description: Query mode for hybrid indexes with Upstash-hosted embedding models (dense only, sparse only, or both). Defaults to `HYBRID` if not provided.
        maxIdle:
          type: number
          description: Maximum idle time for the resumable query in seconds.
```

--------------------------------

TITLE: Delete Vectors by ID Prefix in PHP
DESCRIPTION: This snippet shows how to delete vectors that share a common ID prefix. This is useful for logically grouped vectors. It utilizes the `VectorDeleteByPrefix` class and requires an initialized Upstash Vector Index client.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/delete-vectors.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorDeleteByPrefix;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->delete(new VectorDeleteByPrefix(
  prefix: 'users:',
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorDeleteByPrefix;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->delete(new VectorDeleteByPrefix(
  prefix: 'users:',
));
```

--------------------------------

TITLE: TypeScript: Reset Upstash Vector Default Namespace
DESCRIPTION: Demonstrates how to use the `reset` method to clear all vectors and metadata from the default namespace of an Upstash Vector index. This operation does not require any arguments.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/reset.mdx

LANGUAGE: TypeScript
CODE:
```
const responseReset = await index.reset();
// 'Successful'
```

--------------------------------

TITLE: TypeScript: Reset All Upstash Vector Namespaces
DESCRIPTION: Illustrates how to use the `reset` method with the `all: true` option to clear all vectors and metadata across all namespaces within an Upstash Vector index. This action affects the entire index.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/reset.mdx

LANGUAGE: TypeScript
CODE:
```
const responseReset = await index.reset({ all: true });
// 'Successful'
```

--------------------------------

TITLE: Query Upstash Vector with Dense and Sparse Vectors
DESCRIPTION: This snippet demonstrates how to query a hybrid Upstash Vector index by providing both dense and sparse vectors. The query results will return fused scores from both the dense and sparse indexes. Ensure your REST URL and token are correctly set.

SOURCE: https://upstash.com/docs/vector/features/hybridindexes.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index
from upstash_vector.types import SparseVector

index = Index(
    url="UPSTASH_VECTOR_REST_URL",
    token="UPSTASH_VECTOR_REST_TOKEN",
)

index.query(
    vector=[0.5, 0.4],
    sparse_vector=SparseVector([3, 5], [0.3, 0.5]),
    top_k=5,
    include_metadata=True,
)
```

LANGUAGE: javascript
CODE:
```
import { Index } from "@upstash/vector"

const index = new Index({
  url: "UPSTASH_VECTOR_REST_URL",
  token: "UPSTASH_VECTOR_REST_TOKEN",
})

await index.query({
  vector: [0.5, 0.4],
  sparseVector: {
    indices: [2, 3],
    values: [0.13, 0.87],
  },
  includeData: true,
  topK: 3,
})
```

LANGUAGE: go
CODE:
```
package main

import (
	"github.com/upstash/vector-go"
)

func main() {
	index := vector.NewIndex(
		"UPSTASH_VECTOR_REST_URL",
		"UPSTASH_VECTOR_REST_TOKEN",
	)

	scores, err := index.Query(vector.Query{
		Vector: []float32{0.5, 0.4},
		SparseVector: &vector.SparseVector{
			Indices: []int32{3, 5},
			Values:  []float32{0.3, 05},
		},
		TopK:            5,
		IncludeMetadata: true,
	})
}
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;
use Upstash\Vector\SparseVector;

$index = new Index(
  url: 'UPSTASH_VECTOR_REST_URL',
  token: 'UPSTASH_VECTOR_REST_TOKEN',
);

$index->query(new VectorQuery(
  vector: [0.5, 0.4],
  sparseVector: new SparseVector(
    indices: [3, 5],
    values: [0.3, 0.5],
  ),
  topK: 5,
  includeMetadata: true,
));
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/query \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{"vector": [0.5, 0.4], "sparseVector": {"indices": [3, 5], "values": [0.3, 0.5]}, "topK": 5, "includeMetadata": true}'
```

--------------------------------

TITLE: Configure Max Idle Time for Upstash Vector Resumable Query
DESCRIPTION: Set the maximum idle time for a resumable query during its initialization. Queries that remain untouched for longer than this duration will be automatically stopped by the server. The 'maxIdle' parameter is specified in seconds.

SOURCE: https://upstash.com/docs/vector/features/resumablequery.mdx

LANGUAGE: python
CODE:
```
result, handle = index.resumable_query(
    vector=[0.1, 0.2],
    top_k=2,
    include_metadata=True,
    max_idle = 7200 # two hours, in seconds
)
```

LANGUAGE: javascript
CODE:
```
const { result, fetchNext, stop } = await index.resumableQuery({
  vector: [0.1, 0.2],
  topK: 2,
  includeMetadata: true,
  maxIdle: 7200 // two hours, in seconds
});
```

LANGUAGE: go
CODE:
```
scores, handle, err := index.ResumableQuery(vector.ResumableQuery{
	Vector:          []float32{0.1, 0.2},
	TopK:            2,
	IncludeMetadata: true,
	MaxIdle:         7200, // two hours, in seconds
})
```

LANGUAGE: shell
CODE:
```
curl $UPSTASH_VECTOR_REST_URL/resumable-query \
  -X POST \
  -H "Authorization: Bearer $UPSTASH_VECTOR_REST_TOKEN" \
  -d '{
    "vector": [0.1, 0.2],
    "topK": 2,
    "includeMetadata": true,
    "maxIdle": 7200
  }'
```

--------------------------------

TITLE: Query Data API Reference
DESCRIPTION: This API endpoint allows querying approximate nearest neighbors of raw text data after embedding it. It supports batch requests and various parameters for controlling the query results, including metadata and vector inclusion, filtering, and weighting strategies. An embedding model must be configured for the index to use this endpoint.

SOURCE: https://upstash.com/docs/vector/api/endpoints/query-data.mdx

LANGUAGE: APIDOC
CODE:
```
POST https://{endpoint}/query-data/{namespace}

Authentication: Bearer Token

Request Body (application/json):
[
  {
    "data": "string" (required, The raw text data to embed and query.)
    "topK": "number" (required, default: 10, The total number of vectors to receive as a query result. Response is sorted by distance metric score, returning at most `topK` vectors.)
    "includeMetadata": "boolean" (default: false, Whether to include the metadata of the vectors in the response, if any. Recommended to set to `true` for identification.)
    "includeVectors": "boolean" (default: false, Whether to include the vector values in the response. Recommended to set to `false` due to size.)
    "includeData": "boolean" (default: false, Whether to include the raw text data used during upserting in the response.)
    "filter": "string" (default: "", Metadata filter to apply.)
    "weightingStrategy": "string" (optional, For sparse vectors of sparse and hybrid indexes, specifies the weighting strategy for querying matching non-zero dimension values. Possible value: `IDF`.)
    "fusionAlgorithm": "string" (optional, default: `RRF`, Fusion algorithm to use while fusing scores from dense and sparse components of a hybrid index. Possible values: `RRF`, `DBSF`.)
    "queryMode": "string" (optional, default: `HYBRID`, Query mode for hybrid indexes with Upstash-hosted embedding models. Specifies whether to run the query in only the dense index, only the sparse index, or in both. Possible values: `HYBRID`, `DENSE`, `SPARSE`.)
  }
]

Path Parameters:
  namespace: "string" (optional, default: "", The namespace to use. If not specified, the default namespace will be used.)
```

--------------------------------

TITLE: Filter Upstash Vector Data by Metadata with PHP
DESCRIPTION: This snippet illustrates how to filter vectors based on their associated metadata values when querying an Upstash Vector index. It allows for complex filtering expressions using logical operators. The query requires a vector and returns a specified number of top results matching the filter criteria.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/query.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->query(new VectorQuery(
  vector: [0.1, 0.2, ...],
  topK: 15,
  filter: "country = 'PT' AND continent = 'EU'"
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorQuery;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$results = $index->namespace('my-namespace')->query(new VectorQuery(
  vector: [0.1, 0.2, ...],
  topK: 15,
  filter: "country = 'PT' AND continent = 'EU'"
));
```

--------------------------------

TITLE: Configure Retry Behavior in Upstash Vector Python SDK
DESCRIPTION: This snippet demonstrates how to customize the retry mechanism when initializing an Upstash Vector Index in Python. You can specify the number of retries and the interval between each retry to better handle transient network or API issues.

SOURCE: https://upstash.com/docs/vector/sdks/py/features.mdx

LANGUAGE: python
CODE:
```
from upstash_vector import Index

# Try 5 times with a 2-second interval between retries
index = Index.from_env(retries=5, retry_interval=2.0)
```

--------------------------------

TITLE: API Response for Upstash Vector Query with Metadata
DESCRIPTION: This JSON snippet illustrates the expected structure of a successful API response when querying an Upstash Vector index with 'includeMetadata' set to true. The 'result' array contains objects, each with an 'id', 'score', and a 'metadata' object containing the associated key-value pairs.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: json
CODE:
```
{
  "result": [
    {
      "id": "id-0",
      "score": 1,
      "metadata": {
        "url": "https://imgur.com/z9AVZLb"
      }
    },
    {
      "id": "id-3",
      "score": 0.99961007,
      "metadata": {
        "url": "https://imgur.com/zfOPmnI"
      }
    }
  ]
}
```

--------------------------------

TITLE: APIDOC: QueryResult Object Definition
DESCRIPTION: Defines the structure of a single QueryResult object within the ResumableQueryResponse. It includes the vector's ID, score, optional vector data, sparse vector, metadata, and raw data, depending on query parameters.

SOURCE: https://upstash.com/docs/vector/sdks/ts/commands/resumable-query.mdx

LANGUAGE: APIDOC
CODE:
```
QueryResult: Object
  id: string | number (required)
    The ID of the resulting vector.
  score: number (required)
    The score of the vector data, calculated based on the distance metric of your index.
  vector: number[] (optional)
    The resulting vector (if `includeVectors` is set to true)
  sparseVector: SparseVector (optional)
    The resulting sparseVector (if `includeVectors` is set to true)
  metadata: Record<string, unknown> (optional)
    The metadata of the vector (if `includeMetadata` is set to true)
  data: string (optional)
    The data of the vector (if `includeData` is set to true)
```

--------------------------------

TITLE: Upsert Multiple Data Points with PHP Embedding Model
DESCRIPTION: Utilize the `upsertDataMany()` method to efficiently insert or update multiple data points into your Upstash Vector index in a single batch. The embedding model will generate vectors for each data entry. For optimal performance, limit each batch to a maximum of 1,000 records.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-data.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->upsertDataMany([
  new DataUpsert(id: '1', data: 'The capital of Japan is Tokyo'),
  new DataUpsert(id: '2', data: 'The capital of France is Paris'),
  new DataUpsert(id: '3', data: 'The capital of Germany is Berlin'),
]);
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\DataUpsert;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->upsertDataMany([
  new DataUpsert(id: '1', data: 'The capital of Japan is Tokyo'),
  new DataUpsert(id: '2', data: 'The capital of France is Paris'),
  new DataUpsert(id: '3', data: 'The capital of Germany is Berlin'),
]);
```

--------------------------------

TITLE: Retrieve Data with Upstash Vector Iterator
DESCRIPTION: This code snippet demonstrates how to use an iterator to retrieve data from Upstash Vector, ensuring that the associated data is included in the results. The `includeData` option must be set to `true` in the query parameters. This is useful for processing large result sets efficiently.

SOURCE: https://upstash.com/docs/vector/features/metadata.mdx

LANGUAGE: TypeScript
CODE:
```
import { Index } from '@upstash/vector';

const index = new Index();

async function fetchDataWithIterator() {
  const results = await index.query({
    topK: 10,
    vector: [/* your vector data */],
    includeData: true,
  });

  for (const item of results) {
    console.log(`ID: ${item.id}, Score: ${item.score}, Data: ${JSON.stringify(item.data)}`);
  }
}
```

--------------------------------

TITLE: Python: Update Vector in a Specific Namespace
DESCRIPTION: This Python snippet illustrates how to perform an update operation within a specific namespace. By default, operations occur in the default namespace. Specifying the 'namespace' parameter directs the update to the desired namespace.

SOURCE: https://upstash.com/docs/vector/sdks/py/example_calls/update.mdx

LANGUAGE: python
CODE:
```
index.update(..., namespace="ns")
```

--------------------------------

TITLE: Update Vector Metadata in PHP
DESCRIPTION: This code snippet demonstrates how to update existing vector data, specifically metadata, in an Upstash Vector index using the `update()` method. Unlike `upsert`, `update` only modifies data already present. It requires the Upstash Vector SDK and a configured Index instance, specifying the vector ID and new metadata with an update mode.

SOURCE: https://upstash.com/docs/vector/sdks/php/commands/upsert-vectors.mdx

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpdate;
use Upstash\Vector\Enums\UpdateMode;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->update(new VectorUpdate(
  id: '1',
  metadata: ['foo' => 'baz'],
  metadataUpdateMode: UpdateMode::OVERWRITE,
));
```

LANGUAGE: php
CODE:
```
use Upstash\Vector\Index;
use Upstash\Vector\VectorUpdate;
use Upstash\Vector\Enums\UpdateMode;

$index = new Index(
  url: "<UPSTASH_VECTOR_REST_URL>",
  token: "<UPSTASH_VECTOR_REST_TOKEN>",
);

$index->namespace('my-namespace')->update(new VectorUpdate(
  id: '1',
  metadata: ['foo' => 'baz'],
  metadataUpdateMode: UpdateMode::OVERWRITE,
));
```
```

