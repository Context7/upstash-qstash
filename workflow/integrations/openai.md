On this page
### 
​
Calling OpenAI
The standard way to call a third-party endpoint in your workflow is by using `context.call`. However, if you need to call the OpenAI endpoint for text generation (`/v1/chat/completions`), you can leverage the type-safe method `context.api.openai.call` method:
`context.api.openai.call` is not yet available in workflow-py. You can use `context.call` instead to work with OpenAI. See our Roadmap for feature parity plans and Changelog for updates.
OpenAI
Copy
Ask AI
```
const { status, body } = await context.api.openai.call(
  "Call OpenAI",
  {
    token: "<OPENAI_API_KEY>",
    operation: "chat.completions.create",
    body: {
      model: "gpt-4o",
      messages: [
        {
          role: "system",
          content: "Assistant says 'hello!'",
        },
        {
          role: "user",
          content: "User shouts back 'hi!'"
        }
      ],
    },
  }
);

// get text:
console.log(body.content[0].text)

```

The SDK provides predefined types for the body field in both the request parameters and the response, simplifying common use cases. If you need to customize these types, you can override them as shown below:
Copy
Ask AI
```
type ResponseBodyType = { ... }; // Define your response body type
type RequestBodyType = { ... };  // Define your request body type

const { status, body } = await context.api.openai.call<
  ResponseBodyType,
  RequestBodyType
>(
  "Call OpenAI",
  {
    ...
  }
);

```

### 
​
OpenAI Compatible Provider
If you want to call an OpenAI compatible provider, you can do so using the `baseURL` parameter:
Copy
Ask AI
```
const { status, body } = await context.api.openai.call(
  "Call Deepseek",
  {
    baseURL: "https://api.deepseek.com",
    token: process.env.DEEPSEEK_API_KEY,
    operation: "chat.completions.create",
    body: {
      model: "deepseek-chat",
      messages: [
        {
          role: "system",
          content: "Assistant says 'hello!'",
        },
        {
          role: "user",
          content: "User shouts back 'hi!'"
        }
      ],
    },
  }
);

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Bulk Resume Workflow RunsAnthropic
Assistant
Responses are generated using AI and may contain mistakes.
