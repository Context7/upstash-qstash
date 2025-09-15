The Upstash API requires API keys to authenticate requests. You can view and manage API keys at the Upstash Console. Upstash API uses HTTP Basic authentication. You should pass `EMAIL` and `API_KEY` as basic authentication username and password respectively. With a client such as `curl`, you can pass your credentials with the `-u` option, as the following example shows:
Copy
Ask AI
```
curl https://api.upstash.com/v2/redis/database -u EMAIL:API_KEY

```

Replace `EMAIL` and `API_KEY` with your email and API key.
Was this page helpful?
YesNo
Suggest editsRaise issue
Getting StartedHTTP Status Codes
Assistant
Responses are generated using AI and may contain mistakes.
