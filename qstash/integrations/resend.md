On this page
The `qstash-js` SDK offers an integration to easily send emails using Resend, streamlining email delivery in your applications.
## 
​
Basic Email Sending
To send a single email, use the `publishJSON` method with the `resend` provider. Ensure your `QSTASH_TOKEN` and `RESEND_TOKEN` are set for authentication.
Copy
Ask AI
```
import { Client, resend } from "@upstash/qstash";
const client = new Client({ token: "<QSTASH_TOKEN>" });

await client.publishJSON({
  api: {
    name: "email",
    provider: resend({ token: "<RESEND_TOKEN>" }),
  },
  body: {
    from: "Acme <onboarding@resend.dev>",
    to: ["delivered@resend.dev"],
    subject: "Hello World",
    html: "<p>It works!</p>",
  },
});

```

In the `body` field, specify any parameters supported by the Resend Send Email API, such as `from`, `to`, `subject`, and `html`.
## 
​
Sending Batch Emails
To send multiple emails at once, use Resend’s Batch Email API. Set the `batch` option to `true` to enable batch sending. Each email configuration is defined as an object within the `body` array.
Copy
Ask AI
```
await client.publishJSON({
  api: {
    name: "email",
    provider: resend({ token: "<RESEND_TOKEN>", batch: true }),
  },
  body: [
    {
      from: "Acme <onboarding@resend.dev>",
      to: ["foo@gmail.com"],
      subject: "Hello World",
      html: "<h1>It works!</h1>",
    },
    {
      from: "Acme <onboarding@resend.dev>",
      to: ["bar@outlook.com"],
      subject: "World Hello",
      html: "<p>It works!</p>",
    },
  ],
});

```

Each entry in the `body` array represents an individual email, allowing customization of `from`, `to`, `subject`, `html`, and any other Resend-supported fields.
Was this page helpful?
YesNo
Suggest editsRaise issue
LLM with AnthropicPipedream
Assistant
Responses are generated using AI and may contain mistakes.
