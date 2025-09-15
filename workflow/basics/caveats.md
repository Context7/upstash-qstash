On this page
## 
​
Introduction
In this guide, we’ll look at best practices and caveats for using Upstash Workflow.
## 
​
Core Principles
### 
​
Execute business logic in `context.run`
Your workflow endpoint will be called multiple times during a workflow run. Therefore:
  * Place your business logic code inside the `context.run` function for each step
  * Code outside `context.run` only serves to connect steps

Example:
api/workflow/route.ts
main.py
Copy
Ask AI
```
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload

  const result = await context.run("step-1", () => {
    return { success: true }
  })

  console.log("This log will appear multiple times")

  await context.run("step-2", () => {
    console.log("This log will appear just once")
    console.log("Step 1 status is:", result.success)
  })
})

```

### 
​
Return Results from context.run for Later Use
Always return step results if needed in subsequent steps.
❌ Incorrect - TypeScript
✅ Correct - TypeScript
❌ Incorrect - Python
✅ Correct - Python
Copy
Ask AI
```
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload

  let result

  await context.run("step-1", async () => {
    result = await someWork(input)
  })
  await context.run("step-2", async () => {
    await someOtherWork(result)
  })
})

```

Because your workflow endpoint is called multiple times, `result` will be unitialized when the endpoint is called again to run `step-2`. If you are curious about why an endpoint is called multiple times, see how Workflow works.
## 
​
Avoiding Common Pitfalls
### 
​
Avoid Non-deterministic Code Outside `context.run`
A workflow endpoint should always produce the same results, even if it’s called multiple times. Avoid:
  * Non-idempotent functions
  * Time-dependent code
  * Randomness

Example of what to avoid:
❌ Non-idempotent functions - TypeScript
❌ Time-dependent code - TypeScript
❌ Random code - TypeScript
❌ Non-idempotent functions - Python
❌ Time-dependent code - Python
❌ Random code - Python
Copy
Ask AI
```
export const { POST } = serve<{ entryId: string }>(async (context) => {
  const { entryId } = context.requestPayload;

  // 👇 Problem: Non-idempotent function outside context.run:
  const result = await getResultFromDb(entryId);
  if (result.return) {
    return;
  }

  // ...
})

```

If you implement a non-idempotent code like the one shown above, you might encounter `Failed to authenticate Workflow request.` errors. This can happen if you `return` based on the result of the non-idempotent code before any workflow step. To prevent this, ensure that the non-idempotent code (such as `getResultFromDb` in the example) runs within `context.run`.
TypeScript
Python
Copy
Ask AI
```
const result = await context.run(async () => {
  await getResultFromDb(entryId)
});
if (result.return) {
  return;
}

```

### 
​
Ensure Idempotency in `context.run`
Business logic should be idempotent due to potential retries in distributed systems. In other words, **when a workflow runs twice with the same input, the end result should be the same as if the workflow only ran once**. In the example below, the `someWork` function must be idempotent:
api/workflow/route.ts
main.py
Copy
Ask AI
```
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload

  await context.run("step-1", async () => {
    return someWork(input)
  })
})

```

Imagine that `someWork` executes once and makes a change to a database. However, before the database had a chance to respond with the successful change, the connection is lost. Your Workflow cannot know if the database change was successful or not. The caller has no choice but to retry, which will cause `someWork` to run twice. If `someWork` is not idempotent, this could lead to unintended consequences. For example duplicated records or corrupted data. Idempotency is crucial to maintaining the integrity and reliability of your workflow.
### 
​
Don’t Nest Context Methods
Avoid calling `context.call`, `context.sleep`, `context.sleepFor`, or `context.run` within another `context.run`.
api/workflow/route.ts
main.py
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs"

export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload

  await context.run("step-1", async () => {
    await context.sleep(...) // ❌ INCORRECT
    await context.run(...) // ❌ INCORRECT
    await context.call(...) // ❌ INCORRECT
  })
})

```

### 
​
Include At Least One Step in Workflow
Every workflow must include at least one step execution with `context.run`. If no steps are defined, the workflow will throw a `Failed to authenticate Workflow request.` error.
❌ Missing steps - TypeScript
✅ Correct - TypeScript
❌ Missing steps - Python
✅ Correct - Python
Copy
Ask AI
```
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload
  
  // 👇 Problem: No context.run call
  console.log("Processing input:", input)
  
  // This workflow will fail with "Failed to authenticate Workflow request."
})

```

Even for the placeholder implementations, you must include one dummy step for the Workflow authentication mechanism to function properly.
### 
​
Avoid Promise.any
In workflow-js, you can use `Promise.all` to run steps in parallel. However, a similar method, `Promise.any`, is not supported for workflow steps. While `Promise.all` works seamlessly, `Promise.any` does not currently function with workflow steps. We are exploring the possibility of adding support for `Promise.any` in the future. If you have a specific use case that requires `Promise.any`, don’t hesitate to reach out to Upstash support.
Was this page helpful?
YesNo
Suggest editsRaise issue
How Workflow worksOverview
Assistant
Responses are generated using AI and may contain mistakes.
