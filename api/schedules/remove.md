Skip to main content
On this page
You’ll need to authenticate your requests to access any of the endpoints in the QStash API. In this guide, we’ll look at how authentication works.
## 
​
Bearer Token
When making requests to QStash, you will need your `QSTASH_TOKEN` — you will find it in the console. Here’s how to add the token to the request header using cURL:
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/publish/... \
  -H "Authorization: Bearer <QSTASH_TOKEN>"

```

## 
​
Query Parameter
In environments where setting the header is not possible, you can use the `qstash_token` query parameter instead.
Copy
Ask AI
```
curl https://qstash.upstash.io/v2/publish/...?qstash_token=<QSTASH_TOKEN>

```

Always keep your token safe and reset it if you suspect it has been compromised.
Was this page helpful?
YesNo
Suggest editsRaise issue
Periodic Data UpdatesAPI Rate Limit Response
Ctrl+I
Assistant
Responses are generated using AI and may contain mistakes.
;
