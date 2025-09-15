On this page
## GitHub Repository
You can find the project source code on GitHub.
## Deploy With Vercel
Deploy the project to Vercel with a single click.
This guide provides detailed, step-by-step instructions on how to use and deploy Upstash Workflow with Next.js. You can also explore the source code for a detailed, end-to-end example and best practices.
## 
​
Prerequisites
  1. An Upstash QStash API key.
  2. Node.js and npm (another package manager) installed.

If you haven’t obtained your QStash API key yet, you can do so by signing up for an Upstash account and navigating to your QStash dashboard.
## 
​
Step 1: Installation
In October 2024, we released a new SDK, `@upstash/workflow`, for Upstash Workflow. If you were using `@upstash/qstash` for Upstash Workflow, you can refer to the migration guide for the transition.
First, install the Workflow SDK in your Next.js project:
  * npm
  * pnpm
  * bun


Copy
Ask AI
```
npm install @upstash/workflow

```

## 
​
Step 2: Configure Environment Variables
Create a `.env.local` file in your project root and add your QStash token. This token is used to authenticate your application with the QStash service.
Terminal
Copy
Ask AI
```
touch .env.local

```

Upstash Workflow is powered by QStash, which requires access to your endpoint to execute workflows. When your app is deployed, QStash will use the app’s URL. However, for local development, you have two main options: use a local QStash server or set up a local tunnel.
### 
​
Option 1: Local QStash Server
To start the local QStash server, run:
Copy
Ask AI
```
npx @upstash/qstash-cli dev

```

Once the command runs successfully, you’ll see `QSTASH_URL` and `QSTASH_TOKEN` values in the console. Add these values to your `.env.local` file:
Copy
Ask AI
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>

```

This approach allows you to test workflows locally without affecting your billing. However, runs won’t be logged in the Upstash Console.
### 
​
Option 2: Local Tunnel
Alternatively, you can set up a local tunnel. For this option:
  1. Copy the `QSTASH_TOKEN` from the Upstash Console.
  2. Update your `.env.local` file with the following:


Copy
Ask AI
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>

```

  * Replace `***` with your actual QStash token.
  * Set `UPSTASH_WORKFLOW_URL` to the public URL provided by your local tunnel.

Here’s where you can find your QStash token:
Using a local tunnel connects your endpoint to the production QStash, enabling you to view workflow logs in the Upstash Console.
## 
​
Step 3: Create a Workflow Endpoint
A workflow endpoint allows you to define a set of steps that, together, make up a workflow. Each step contains a piece of business logic that is automatically retried on failure, with easy monitoring via our visual workflow dashboard. To define a workflow endpoint in a Next.js project, navigate into the Next.js `app/api` directory and create a new folder, for example called `workflow`. Inside this folder, create a `route.ts` file that contains your workflow:
  * Minimal example
  * With request object
  * Minimal example (Pages Router)
  * With request object (Pages Router)


app/api/workflow/route.ts
Copy
Ask AI
```
import { serve } from "@upstash/workflow/nextjs"

export const { POST } = serve(
  async (context) => {
    await context.run("initial-step", () => {
      console.log("initial step ran")
    })

    await context.run("second-step", () => {
      console.log("second step ran")
    })
  }
)

```

## 
​
Step 4: Run the Workflow Endpoint
After defining the endpoint, you can trigger your workflow by starting your app:
Terminal
Copy
Ask AI
```
npm run dev

```

Then, make a POST request to your workflow endpoint. For each workflow run, a unique workflow run ID is returned:
Terminal
Copy
Ask AI
```
curl -X POST https://localhost:3000/api/workflow

# result: {"workflowRunId":"wfr_xxxxxx"}

```

In Nextjs Pages, always send `content-type: text/plain` header. See the documentation on starting a workflow for other ways you can start your workflow.
If you are using a local tunnel, you can use this ID to track the workflow run and see its status in your QStash workflow dashboard. All steps are listed with their statuses, headers, and body for a detailed overview of your workflow from start to finish. Click on a step to see its detailed logs.
## 
​
Step 5: Deploying to Production
When deploying your Next.js application with Upstash Workflow to production, there are a few key points to keep in mind:
  1. **Environment Variables** : Make sure that all necessary environment variables are set in your Vercel project settings. For example, your `QSTASH_TOKEN` and any other configuration variables your workflow might need.
  2. **Remove Local Development Settings** : In your production code, you can remove or conditionally exclude any local development settings. For example, if you used local tunnel for local development
  3. **Deployment** : Deploy your Next.js application to Vercel, AWS Amplify or other platforms as you normally would. These platforms will automatically detect and build your Next.js application.
  4. **Verify Workflow Endpoint** : After deployment, verify that your workflow endpoint is accessible by making a POST request to your production URL:
Terminal
Copy
Ask AI
```
curl -X POST https://<YOUR-PRODUCTION-URL>/api/workflow

```

  5. **Monitor in QStash Dashboard** : Use the QStash dashboard to monitor your production workflows. You can track workflow runs, view step statuses, and access detailed logs.
  6. **Set Up Alerts** : Consider setting up alerts in Sentry or other monitoring tools to be notified of any workflow failures in production.


## 
​
Next Steps
  1. Learn how to protect your workflow endpoint from unauthorized access by securing your workflow endpoint.
  2. Explore the source code for a detailed, end-to-end example and best practices.
  3. For setting up and testing your workflows in a local environment, check out our local development guide.


Was this page helpful?
YesNo
Suggest editsRaise issue
Supported PlatformsCloudflare Workers
Assistant
Responses are generated using AI and may contain mistakes.
