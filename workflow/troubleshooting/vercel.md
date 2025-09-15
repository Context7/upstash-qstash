On this page
# 
​
Common Issues and Solutions
### 
​
Preview Deployment Protection
**Problem:** When Deployment Protection setting is enabled on Vercel, it’s not possible to trigger and complete a workflow run on a preview deployment. **Solution:** Vercel provides a way to bypass this protection by using a bypass secret. To create one, follow these steps:
1
Settings
Go to **Deployment Protection** section under your Vercel project settings.
2
Find related section
Click on **Add Secret** under **Protection Bypass for Automation** section.
3
Generate a bypass token
Don’t forget to save it.
Now that you have a bypass token, you can add it to your workflow URL as a query parameter. Imagine that you have a Vercel Preview and there is a workflow endpoint at `https://vercel-preview.com/workflow`. You can call the workflow like this in preview:
Copy
Ask AI
```
curl -X POST \
  'https://vercel-preview.com/workflow?x-vercel-protection-bypass=<PROTECTION_BYPASS_SECRET>' \
  -d 'Hello world!'

```

Was this page helpful?
YesNo
Suggest editsRaise issue
GeneralChangelog
Assistant
Responses are generated using AI and may contain mistakes.
