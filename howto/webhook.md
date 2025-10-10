# Use as Webhook Receiver

You can configure QStash to receive and process your webhook calls.

Instead of having the webhook service call your endpoint directly, QStash acts as an intermediary, receiving the request and forwarding it to your endpoint.
QStash provides additional control over webhook requests, allowing you to configure properties such as delay, retries, timeouts, callbacks, and flow control.

There are multiple ways to configure QStash to receive webhook requests.

## 1. Publish

You can configure your webhook URL as a QStash publish request.

For example, if your webhook endpoint is:

`https://example.com/api/webhook`

Instead of using this URL directly as the webhook address, use:

`https://qstash.upstash.io/v2/publish/https://example.com/api/webhook?qstash_token=<QSTASH_TOKEN>`

<Note>
  Request configurations such as custom retries, timeouts, and other settings can be specified using HTTP headers in the publish request.
  Refer to the [REST API documentation](/qstash/api/publish) for a full list of available configuration headers.

  It’s also possible to pass configuration via query parameters. You can use the lowercase format of headers as the key, such as ?upstash-retries=3\&upstash-delay=100s. This makes it easier to configure webhook messages.
</Note>

<Tip>
  By default, any headers in the publish request that are prefixed with `Upstash-Forward-` will be forwarded to your endpoint.

  However, since most webhook services do not allow header prefixing, we introduced a configuration option to enable forwarding all incoming request headers.

  To enable this, set `Upstash-Header-Forward: true` in the publish request or append the query parameter `?upstash-header-forward=true` to the request URL. This ensures that all headers are forwarded to your endpoint without requiring the `Upstash-Forward-` prefix.
</Tip>

## 2. URL Group

URL Groups allow you to define server-side templates for publishing messages. You can create a URL Group either through the UI or programmatically.

For example, if your webhook endpoint is:

`https://example.com/api/webhook`

Instead of using this URL directly, you can create a URL Group and add this URL as an endpoint.

`https://qstash.upstash.io/v2/publish/<URL_GROUP_NAME>?qstash_token=<QSTASH_TOKEN>`

You can define default headers for a URL Group, which will automatically apply to all requests sent to that group.

```
curl -X PATCH https://qstash.upstash.io/v2/topics/<URL_GROUP_NAME> \
    -H "Authorizarion: Bearer <QSTASH_TOKEN>"
    -d '{
        "headers": {
            "Upstash-Header-Forward": ["true"],
            "Upstash-Retries": "3"
        }
    }'
```

When you save this header for your URL Group, it ensures that all headers are forwarded as needed for your webhook processing.

A URL Group also enables you to define multiple endpoints within group.
When a publish request is made to a URL Group, all associated endpoints will be triggered, allowing you to fan-out a single webhook call to multiple destinations.
