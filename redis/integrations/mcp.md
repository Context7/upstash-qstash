On this page
We provide an open source Upstash MCP to use natural language to interact with your Upstash account, e.g.:
  * “Create a new Redis database in us-east-1”
  * “List my databases”
  * “Show all keys starting with “user:” in my users-db”
  * “Create a backup”
  * “Show me the throughput spikes for the last 7 days”


* * *
## 
​
Quickstart
### 
​
Step 1: Get your API Key
  1. Go to `Account > Management API > Create API key` and create an API key. 
  2. Note down your `<UPSTASH_EMAIL>` and `<UPSTASH_API_KEY>`.


* * *
### 
​
Step 2: Locate `mcp.json`
  * **Cursor** : Navigate to `Cursor Settings > Features > MCP` and click `+ Add new global MCP server`. This will open the `mcp.json` file. 
  * **Claude** : Navigate to `Settings > Developer` and click `Edit Config`. This will open the `claude_desktop_config.json` file. Refer to the MCP documentation for more details.
  * **Copilot** : Create a `.vscode/mcp.json` file in your workspace directory. For Copilot, first update the `mcp.json` file as described in the next step on this page, then follow the Copilot documentation (starting from step 2) to configure MCP servers in VS Code Chat.


* * *
### 
​
Step 3: Configure the MCP File
There are two transport modes for MCP servers: `stdio` and `sse`.
  * **Stdio** : Best for local development. The server runs locally, and the client connects directly to it.
  * **SSE** : Designed for server deployments. However, since clients don’t yet support SSE connections with all the features we need, you need a proxy server. The proxy acts as a `stdio` server for the client and communicates with the SSE server in the background.


#### 
​
Option 1: Stdio Server
Add the following configuration to your MCP file:
Claude & Cursor
Copilot
Copy
Ask AI
```
{
  "mcpServers": {
    "upstash": {
      "command": "npx",
      "args": [
        "-y",
        "@upstash/mcp-server",
        "run",
        "<UPSTASH_EMAIL>",
        "<UPSTASH_API_KEY>"
      ]
    }
  }
}

```

#### 
​
Option 2: SSE Server with Proxy
SSE (Server-Sent Events) is the next stage in MCP transport modes after `stdio`. It is designed for server deployments and will eventually be followed by an HTTP-based transport mode. However, since clients currently do not support direct connections to SSE servers, we use a proxy to bridge the gap. The proxy, powered by `supergateway`, acts as a `stdio` server locally while communicating with the SSE server in the background. This allows you to use the SSE server seamlessly with your client. Add the following configuration to your `mcp.json` file:
Claude & Cursor
Copilot
Copy
Ask AI
```
{
  "mcpServers": {
    "upstash": {
      "command": "npx",
      "args": [
        "-y",
        "supergateway",
        "--sse",
        "https://mcp.upstash.io/sse",
        "--oauth2Bearer",
        "<UPSTASH_EMAIL>:<UPSTASH_API_KEY>"
      ]
    }
  }
}

```

* * *
### 
​
Step 4: Use MCP with Your Client
Once your MCP is configured, your client can now interact with the MCP server for tasks like:
  * Seeding data
  * Querying databases
  * Creating new databases
  * Managing backups
  * Analyzing performance metrics

For example, you can ask your client to “add ten users to my Redis database” or “show me the throughput spikes for the last 7 days.”
Was this page helpful?
YesNo
Suggest editsRaise issue
CeleryCaching in Laravel with Redis
Assistant
Responses are generated using AI and may contain mistakes.
