# Resume Queue

> Resume a paused queue

Resuming a queue starts the delivery of enqueued messages from the earliest undelivered message.
If the queue is already active, this action has no effect.

## Request

<ParamField path="queueName" type="string" required>
  The name of the queue to resume.
</ParamField>

## Response

This endpoint simply returns 200 OK if the queue is resumed successfully.

<RequestExample>
  ```sh curl theme={"system"}
  curl -X POST https://qstash.upstash.io/v2/queues/queue_1234/resume \
    -H "Authorization: Bearer <token>"
  ```

  ```js Node theme={"system"}
  import { Client } from "@upstash/qstash";
  /**
   * Import a fetch polyfill only if you are using node prior to v18.
   * This is not necessary for nextjs, deno or cloudflare workers.
   */
  import "isomorphic-fetch";

  const c = new Client({
    token: "<QSTASH_TOKEN>",
  });

  c.queue({ queueName: "<QUEUE_NAME>" }).resume()
  ```

  ```python Python  theme={"system"}
  from qstash import QStash

  client = QStash("<QSTASH_TOKEN>")

  client.queue.resume("<QUEUE_NAME>")
  ```

  ```go Go theme={"system"}
  package main

  import (
  	"github.com/upstash/qstash-go"
  )

  func main() {
  	client := qstash.NewClient("<QSTASH_TOKEN>")

  	// error checking is omitted for brevity
  	err := client.Queues().Resume("<QUEUE_NAME>")
  }
  ```
</RequestExample>
