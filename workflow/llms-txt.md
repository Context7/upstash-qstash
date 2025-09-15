```
================
CODE SNIPPETS
================
TITLE: Upstash Workflow SDK Quick Start
DESCRIPTION: A brief guide on how to get started with the Upstash Workflow SDK. It also provides links to quickstart guides for different frameworks like Next.js and Cloudflare Workers.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```
## Quick Start

Here, we will briefly showcase how you can get started with Upstash Workflow.
Alternatively, you can check [our quickstarts for different frameworks](https://upstash.com/docs/workflow/quickstarts/platforms), including [Next.js](https://upstash.com/docs/qstash/workflow/quickstarts/vercel-nextjs) and [Cloudflare](https://upstash.com/docs/workflow/quickstarts/cloudflare-workers).
```

--------------------------------

TITLE: Upstash Get Started: Redis
DESCRIPTION: Create a Redis database in seconds with Upstash Serverless Redis. This guide covers the initial setup and provides a link to the Redis get started documentation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```
## [Serverless Redis Create a Redis Database within seconds ](https://upstash.com/docs/redis/overall/getstarted)
```

--------------------------------

TITLE: QStash Development Server Output Example
DESCRIPTION: This output shows an example of what the QStash development server logs might look like when it starts. It provides the local server URL and authentication tokens necessary for configuring your application to use the local server.

SOURCE: https://upstash.com/docs/workflow/howto/local-development

LANGUAGE: text
CODE:
```
Upstash QStash development server is runnning at http://127.0.0.1:8080
A default user has been created for you to authorize your requests.
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7RvLjqfZBvP5KEUimQCE1pvpLuou
QSTASH_NEXT_SIGNING_KEY=sig_7W3ZNbfKWk5NWwEs3U4ixuQ7fxwE
Sample cURL request:
curl -X POST http://127.0.0.1:8080/v2/publish/https://example.com -H "Authorization: Bearer eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0="
Check out documentation for more details:
https://upstash.com/docs/qstash/howto/local-development

```

--------------------------------

TITLE: Install Upstash Workflow Packages
DESCRIPTION: Installs the necessary Upstash Workflow, AI, and Zod packages for a Next.js project using npm.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: bash
CODE:
```
npx create-next-app@latest [project-name] [options]
npm i @upstash/workflow ai zod
```

--------------------------------

TITLE: Next.js Workflow Quickstart
DESCRIPTION: Guide to building a Next.js application utilizing QStash Workflow. This quickstart covers the setup and integration process for developers using Next.js.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { Workflow } from '@upstash/workflow';

const workflow = new Workflow({
  // Configuration options
});

// Define workflow steps
workflow.step('step1', async (input) => {
  // ... logic ...
  return { output: 'processed' };
});

workflow.run('myWorkflow', { initialInput: 'data' });
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts the local QStash server using the Upstash CLI for local development of Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start QStash Development Server
DESCRIPTION: This command starts the local development server for Upstash QStash, which mimics QStash functionality for local testing and development. It requires the QStash CLI to be installed.

SOURCE: https://upstash.com/docs/workflow/howto/local-development

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev

```

--------------------------------

TITLE: Clone Upstash Workflow Next.js & Flask Example
DESCRIPTION: Clones the Upstash Workflow Python example repository and navigates into the Next.js & Flask example directory for project setup.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-flask
```

--------------------------------

TITLE: Upstash Get Started: Vector Database
DESCRIPTION: Provides a link to the Upstash Vector documentation for getting started with creating a vector database for AI and LLM projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```
## [Serverless Vector Create a Vector Database for AI & LLMs ](https://upstash.com/docs/vector/overall/getstarted)
```

--------------------------------

TITLE: Initial Vercel Project Setup
DESCRIPTION: This command initiates the project setup process for deployment on Vercel. It typically involves connecting to your Vercel account and configuring project settings.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
vercel
```

--------------------------------

TITLE: Clone Next.js & FastAPI Example
DESCRIPTION: Clones the Upstash workflow-py repository and navigates into the Next.js & FastAPI example directory. This is the first step to setting up the project.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-fastapi
```

--------------------------------

TITLE: Clone Next.js & Flask Workflow Example
DESCRIPTION: Clones the Upstash workflow-py repository and navigates into the Next.js & Flask example directory. This is the initial step to get the project structure for the tutorial.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-flask
```

--------------------------------

TITLE: Start Next.js Development Server
DESCRIPTION: Starts the Next.js development server. Requires Node.js and npm to be installed and project dependencies to be set up.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: shell
CODE:
```
npm run dev
```

--------------------------------

TITLE: Run Next.js App
DESCRIPTION: This command starts the Next.js development server, which is necessary before triggering the Upstash Workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Project Setup and Build with Bun
DESCRIPTION: Installs project dependencies and builds the project using Bun, a fast JavaScript runtime and toolkit.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun install
bun run build
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server using the Upstash CLI. This allows for local testing of workflows without impacting production or incurring costs.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server for development. This command provides QSTASH_URL and QSTASH_TOKEN values that should be added to your .env file for local testing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Configure Environment Variables
DESCRIPTION: Sets up essential environment variables in the .env.local file for Upstash Workflow, including QStash URL, Qstash Token, and OpenAI API Key.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: env
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
OPENAI_API_KEY=<OPENAI_API_KEY>
```

--------------------------------

TITLE: Project Setup and Build with Bun
DESCRIPTION: Provides commands for setting up the project using Bun, including installing dependencies and building the project. Bun is a required tool for this project.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: bash
CODE:
```
bun install
bun run build

```

--------------------------------

TITLE: Connect and Use Redis CLI
DESCRIPTION: Demonstrates how to connect to an Upstash Redis database using the redis-cli and execute basic commands like SET, GET, and INCR. This requires the redis-cli tool and your database credentials (password, endpoint, port).

SOURCE: https://upstash.com/docs/redis

LANGUAGE: redis-cli
CODE:
```
> redis-cli --tls -a PASSWORD -h ENDPOINT -p PORT
ENDPOINT:PORT> set counter 0
OK
ENDPOINT:PORT> get counter
"0"
ENDPOINT:PORT> incr counter
(int) 1
ENDPOINT:PORT> incr counter
(int) 2
```

--------------------------------

TITLE: Start Workflow - Result Example
DESCRIPTION: This snippet shows an example of the JSON result returned when starting a workflow, containing a workflowRunId. This ID is used to track the workflow's progress and view its details in the QStash workflow dashboard.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: json
CODE:
```
{
  "workflowRunId": "wfr_xxxxxx"
}
```

--------------------------------

TITLE: Start ngrok Tunnel for Local Server
DESCRIPTION: This snippet shows the command to start an ngrok tunnel, making a local server accessible publicly. Replace `<PORT>` with your server's actual port number. The example demonstrates using port 3000 for a Next.js application.

SOURCE: https://upstash.com/docs/workflow/howto/local-development

LANGUAGE: bash
CODE:
```
ngrok http <PORT>
```

LANGUAGE: bash
CODE:
```
ngrok http 3000
```

--------------------------------

TITLE: Next.js Quickstart with Upstash Workflow
DESCRIPTION: This quickstart guides you through building a Next.js application integrated with QStash Workflow. It demonstrates how to leverage Upstash Workflow for durable and reliable serverless functions within a Next.js environment.

SOURCE: https://upstash.com/docs/workflow/getstarted

LANGUAGE: TypeScript
CODE:
```
import { Workflow } from '@upstash/workflow';

// Example workflow definition
const myWorkflow = new Workflow({
  name: 'my-nextjs-workflow',
  steps: [
    {
      id: 'step1',
      handler: async ({ input }) => {
        console.log('Processing input:', input);
        return { message: 'Step 1 completed' };
      },
    },
    // Add more steps as needed
  ],
});

// To run the workflow (example):
// await myWorkflow.run({ data: 'initial data' });
```

--------------------------------

TITLE: Initialize Vercel Project Deployment (Bash)
DESCRIPTION: Initializes the Vercel project setup process, guiding the user through configuring the project for deployment on the Vercel platform.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Install Dependencies and Run Tests
DESCRIPTION: These commands outline the development setup for the Upstash Workflow project. They cover cloning the repository, installing dependencies using Poetry, setting up environment variables, running tests with pytest, and formatting/checking code with Ruff and mypy.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-py

LANGUAGE: Shell
CODE:
```
poetry install
```

LANGUAGE: Shell
CODE:
```
cp .env.example .env
```

LANGUAGE: Shell
CODE:
```
poetry run pytest
```

LANGUAGE: Shell
CODE:
```
poetry run ruff format .
```

LANGUAGE: Shell
CODE:
```
poetry run ruff check .
```

LANGUAGE: Shell
CODE:
```
poetry run mypy --show-error-codes .
```

--------------------------------

TITLE: Start Local QStash CLI
DESCRIPTION: Starts the local QStash command-line interface for development. This command provides QStash URL and Token for local testing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Initialize Vercel Project Deployment
DESCRIPTION: Initializes the Vercel project setup process, guiding users through configuring the project for deployment on the Vercel platform.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Install Node.js Dependencies
DESCRIPTION: Installs project dependencies using npm. This command should be run after setting up the Node.js environment.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
npm install
```

--------------------------------

TITLE: Clone Upstash Workflow Next.js & FastAPI Example Repository
DESCRIPTION: Clones the Upstash Workflow Next.js & FastAPI example repository from GitHub to your local machine and navigates into the example directory. This is the initial step to set up the project locally, providing access to the example application's source code.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-fastapi
```

LANGUAGE: shell
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-fastapi
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts the local QStash CLI in development mode. This provides QSTASH_URL and QSTASH_TOKEN for local testing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Development Server
DESCRIPTION: Starts the Next.js development server. The application will be accessible at http://localhost:3000, and FastAPI at http://localhost:8000.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK and Flask
DESCRIPTION: Installs the necessary Python packages for Upstash Workflow and Flask. This includes the Workflow SDK, Flask, and Uvicorn for running the application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Setup Flask Environment with Upstash Workflow
DESCRIPTION: Creates a virtual environment, activates it, and installs necessary packages (FastAPI, Uvicorn, Upstash Workflow) for a Flask-based Upstash Workflow project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate

pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Clone Upstash Workflow Next.js & FastAPI Example
DESCRIPTION: Clones the Upstash Workflow Python repository and navigates into the Next.js and FastAPI example directory. This is the initial step to set up the project locally.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-fastapi
```

--------------------------------

TITLE: Install FastAPI and Upstash Workflow SDK
DESCRIPTION: Installs the necessary Python packages for FastAPI and the Upstash Workflow SDK using pip. This is a prerequisite for building workflows with FastAPI.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Clone Next.js & Flask Upstash Workflow Example
DESCRIPTION: Clones the Upstash Workflow Next.js & Flask example repository from GitHub and navigates into the project directory, preparing your local environment for the example.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Shell
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-flask
```

--------------------------------

TITLE: Upstash Get Started: QStash Messaging
DESCRIPTION: Provides a link to the Upstash QStash documentation for publishing your first message and integrating messaging into applications.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```

```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK for Node.js projects using npm. This is the first step to integrate workflow capabilities into your application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow 
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server for development. Outputs QSTASH_URL and QSTASH_TOKEN values to be added to the .dev.vars file.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev

```

--------------------------------

TITLE: Install Node.js Project Dependencies (Bash)
DESCRIPTION: Installs all required Node.js packages and their dependencies from `package.json` for the Next.js frontend. Essential for project setup.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install
```

--------------------------------

TITLE: Deploy Project with Vercel CLI
DESCRIPTION: Initiates the deployment process for the project using the Vercel CLI. This command typically guides the user through project setup and configuration with Vercel for deployment.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Start Next.js Development Server
DESCRIPTION: Starts the Next.js development server, typically on http://localhost:3000. This command also implicitly starts the Flask backend if configured correctly.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: Installs the Upstash Workflow SDK for SolidJS projects using npm. This is the first step to integrating workflow capabilities into your application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Start SvelteKit Development Server
DESCRIPTION: Starts the SvelteKit development server to make the workflow endpoint accessible for testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Basic Webhook Endpoint Setup (TypeScript)
DESCRIPTION: Sets up a basic webhook endpoint using the `serve` function from `@upstash/workflow/nextjs`. This function handles incoming requests and allows for custom logic within the callback.

SOURCE: https://upstash.com/docs/workflow/howto/use-webhooks

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
export const { POST } = serve(
  async (context) => {
    // Your webhook handling logic here
  },
  {
    initialPayloadParser: (payload) => {
      return payload;
    },
  }
);

```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: Installs the `@upstash/workflow` SDK for your Next.js project using npm. This is the first step to integrating Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: New User Signup Step (TypeScript)
DESCRIPTION: This snippet shows the initial step in the Upstash Workflow for customer onboarding, which involves sending a welcome email to a newly signed-up user. It uses `context.run` to execute the email sending logic.

SOURCE: https://upstash.com/docs/workflow/examples/customerOnboarding

LANGUAGE: TypeScript
CODE:
```
await context.run("new-signup", async () => {
  await sendEmail("Welcome to the platform", email)
})
```

--------------------------------

TITLE: Configure Local QStash Server
DESCRIPTION: Starts a local QStash server for development and configures environment variables with the server URL and token.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev

```

LANGUAGE: dotenv
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>

```

--------------------------------

TITLE: Start Local QStash Server (Bash)
DESCRIPTION: Starts a local QStash development server using `npx` and `@upstash/qstash-cli`. Provides local `QSTASH_URL` and `QSTASH_TOKEN` for testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Local QStash Development Server
DESCRIPTION: Starts a local QStash development server for testing workflows locally. It provides `QSTASH_URL` and `QSTASH_TOKEN` environment variables.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start SvelteKit Development Server
DESCRIPTION: Starts the SvelteKit development server, which makes your application and its defined workflow endpoints accessible locally for testing and interaction.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: Installs the Upstash Workflow SDK package into your Nuxt.js project using npm.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: Start Local QStash CLI
DESCRIPTION: Starts the local QStash CLI in development mode. This command provides QSTASH_URL and QSTASH_TOKEN for local testing of Upstash Workflow without affecting billing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Setup Python Virtual Environment
DESCRIPTION: Creates and activates a Python virtual environment named 'venv'. This isolates project dependencies and ensures a clean development setup.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Install Node.js Dependencies
DESCRIPTION: Installs project dependencies using npm, typically for the Next.js frontend part of the application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
npm install
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local development server for QStash, which is used for testing Upstash Workflow locally without impacting production or billing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/svelte

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash development server. Provides QSTASH_URL and QSTASH_TOKEN for local workflow testing, to be added to .dev.vars.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Run SvelteKit Development Server
DESCRIPTION: Starts the SvelteKit development server, allowing you to test your application locally.

SOURCE: https://upstash.com/docs/workflow/quickstarts/svelte

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Run FastAPI Application
DESCRIPTION: Starts the FastAPI application using uvicorn, enabling hot-reloading for development. This command makes your workflow endpoint accessible.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
uvicorn main:app --reload
```

--------------------------------

TITLE: Start Local QStash CLI
DESCRIPTION: Starts the local QStash CLI in development mode. This command provides QSTASH_URL and QSTASH_TOKEN for local testing without using the Upstash Console.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Clone and Navigate Upstash Workflow Python Example
DESCRIPTION: Clones the Upstash Workflow Python repository and changes the directory to the Next.js & Flask example, preparing the project structure.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
git clone https://github.com/upstash/workflow-py.git
cd workflow-py/examples/nextjs-flask
```

--------------------------------

TITLE: Run SolidJS Development Server
DESCRIPTION: Starts the SolidJS development server using npm. This command is used to run the application locally after defining the workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server using the `@upstash/qstash-cli` for local development and testing of Upstash Workflows. This command outputs QSTASH_URL and QSTASH_TOKEN, essential for local testing without incurring costs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Execute User Creation Workflow
DESCRIPTION: This snippet demonstrates the initial steps of a user onboarding workflow. It includes creating a user in the database, setting up their account in Stripe, and sending a welcome email. The workflow uses asynchronous operations and time delays for managing the user's trial period.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { WorkflowContext } from '@upstash/qstash/workflow'
/**
 * This can be the payload of the user created webhook event coming from your
 * auth provider (e.g. Firebase, Auth0, Clerk etc.)
 */
type UserCreatedPayload = {
  name: string;
  email: string;
};
export const { POST } = serve<UserCreatedPayload>(async (context) => {
  const { name, email } = context.requestPayload;
  const { userid } = await context.run("sync user", async () => {
    return await createUserInDatabase({ name, email });
  });
  await context.run("create new user in stripe", async () => {
    await createNewUserInStripe(email);
  });
  await context.run("start trial in Stripe", async () => {
    await startTrialInStripe(email);
  });
  await context.run("send welcome email", async () => {
    await sendEmail(
      email,
      "Welcome to our platform!, You have 14 days of free trial."
    );
  });
  await context.sleep("wait", 7 * 24 * 60 * 60);
  // get user stats and send email with them
  const stats = await context.run("get user stats", async () => {
    return await getUserStats(userid);
  });
  await sendProblemSolvedEmail({context, email, stats});
  // wait until there are two days to the end of trial period
  // and check upgrade status
  await context.sleep("wait for trial warning", 5 * 24 * 60 * 60);
  const isUpgraded = await context.run("check upgraded plan", async () => {
    return await checkUpgradedPlan(email);
  });
  // end the workflow if upgraded
  if (isUpgraded) return;
  await context.run("send trial warning email", async () => {
    await sendEmail(
      email,
      "Your trial is about to end in 2 days. Please upgrade your plan to keep using our platform."
    );
  });
  await context.sleep("wait for trial end", 2 * 24 * 60 * 60);
  await context.run("send trial end email", async () => {
    await sendEmail(
      email,
      "Your trial has ended. Please upgrade your plan to keep using our platform."
    );
  });
});
async function sendProblemSolvedEmail({
  context: WorkflowContext<UserCreatedPayload>
  email: string,
  stats: { totalProblemsSolved: number }
}) {
  if (stats.totalProblemsSolved === 0) {
    await context.run("send no answers email", async () => {
      await sendEmail(
        email,
        "Hey, you haven't solved any questions in the last 7 days..."
      );
    });
  } else {
    await context.run("send stats email", async () => {
      await sendEmail(
        email,
        `You have solved ${stats.totalProblemsSolved} problems in the last 7 days. Keep it up!`
      );
    });
  }
}
async function createUserInDatabase({
  name,
  email,
}: {
  name: string;
  email: string;
}) {
  console.log("Creating a user in the database:", name, email);
  return { userid: "12345" };
}
async function createNewUserInStripe(email: string) {
  // Implement logic to create a new user in Stripe
  console.log("Creating a user in Stripe for", email);
}
async function startTrialInStripe(email: string) {
  // Implement logic to start a trial in Stripe
  console.log("Starting a trial of 14 days in Stripe for", email);
}
async function getUserStats(userid: string) {
  // Implement logic to get user stats
  console.log("Getting user stats for", userid);
  return {
    totalProblemsSolved: 10_000,
    mostInterestedTopic: "JavaScript",
  };
}
async function checkUpgradedPlan(email: string) {
  // Implement logic to check if the user has upgraded the plan
  console.log("Checking if the user has upgraded the plan", email);
  return false;
}
async function sendEmail(email: string, content: string) {
  // Implement logic to send an email
  console.log("Sending email to", email, content);
}
```

--------------------------------

TITLE: Install Upstash Workflow SDK with Bun
DESCRIPTION: Installs the `@upstash/workflow` package using Bun. This is an alternative installation method for migrating from the old SDK, allowing for separate Workflow development from the QStash SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Example Quantum Mechanics Explanation
DESCRIPTION: Presents an example of AI-generated text output explaining quantum mechanics, demonstrating the successful operation of a generator-evaluator workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: plain text
CODE:
```
Quantum mechanics is a branch of physics that describes the behavior of particles at the smallest scales, such as atoms and subatomic particles. It introduces the concept of quantized energy levels, wave-particle duality, and probabilistic nature of particles. In quantum mechanics, particles can exist in multiple states simultaneously until measured, and their behavior is governed by mathematical equations known as wave functions. This theory has revolutionized our understanding of the fundamental building blocks of the universe and has led to the development of technologies like quantum computing and quantum cryptography.
```

--------------------------------

TITLE: Start Stripe Trial
DESCRIPTION: This code initiates a trial period for a user within the Stripe payment system. It's typically followed by email notifications to inform the user about their trial status.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
await context.run("start trial in Stripe", async () => {
  await startTrialInStripe(email);
});
```

--------------------------------

TITLE: Install Upstash Workflow and Flask (pip)
DESCRIPTION: Installs the Upstash Workflow SDK and Flask using pip, also setting up a virtual environment for the project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pip install @upstash/workflow flask
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash development server. After execution, it outputs QSTASH_URL and QSTASH_TOKEN, which are needed for the .dev.vars file during local workflow testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Run Nuxt.js Development Server
DESCRIPTION: Starts the Nuxt.js development server to run the workflow endpoint locally.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: bash
CODE:
```
npm run dev

```

--------------------------------

TITLE: Start Stripe Trial
DESCRIPTION: Initiates a user's trial period in Stripe using 'context.run' to encapsulate 'startTrialInStripe'. Uses the 'email' parameter for trial activation. Examples are provided for both TypeScript and Python.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
await context.run("start trial in Stripe", async () => {
  await startTrialInStripe(email);
});
```

LANGUAGE: Python
CODE:
```
async def _start_trial_in_stripe() -> None:
    await start_trial_in_stripe(email)

```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts the local QStash development server for testing Upstash Workflows. This command is available via npx and pnpm dlx.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

LANGUAGE: bash
CODE:
```
pnpm dlx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Development Server
DESCRIPTION: Starts the development server for SolidJS, Next.js, or Nuxt.js applications. This command makes your application and workflow endpoints accessible locally.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts the local QStash CLI in development mode, providing necessary environment variables (QSTASH_URL, QSTASH_TOKEN) for local testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Development Server
DESCRIPTION: Executes the development script to start applications locally, such as Hono applications, typically at `http://localhost:8787`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK with Bun
DESCRIPTION: Installs the `@upstash/workflow` package using the Bun package manager. This is an alternative installation method, useful for managing dependencies separately from the QStash SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Run Next.js Development Server
DESCRIPTION: Starts the Next.js development server using npm. This command is used to run the application locally after setting up the workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: bash
CODE:
```
npm run dev

```

--------------------------------

TITLE: Starting Local QStash Server (npm)
DESCRIPTION: This command starts the local QStash server using the @upstash/qstash-cli tool, which is required for local development and testing of Upstash Workflow endpoints. It provides local QSTASH_URL and QSTASH_TOKEN values.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Python Customer Onboarding Workflow with Upstash
DESCRIPTION: A comprehensive Python workflow example using Upstash. It sends a welcome email, pauses for three days, generates a personalized message using OpenAI, and sends a follow-up email. Utilizes `context.run` for retries and `context.call` for external API integration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
class InitialData(TypedDict):
    user_id: str
    email: str
    name: str


@serve.post("/api/onboarding")
async def onboarding_workflow(context: AsyncWorkflowContext[InitialData]) -> None:
    data = context.request_payload
    user_id = data["user_id"]
    email = data["email"]
    name = data["name"]

    # Step 1: Send welcome email
    async def _send_welcome_email() -> None:
        await send_email(email, "Welcome to our service!")

    await context.run("send-welcome-email", _send_welcome_email)

    # Step 2: Wait for 3 days (in seconds)
    await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3)

    # Step 3: AI-generate personalized follow-up message
    ai_response: CallResponse[Dict[str, str]] = await context.call(
        "generate-personalized-message",
        url="https://api.openai.com/v1/chat/completions",
        method="POST",
        headers={...},
        body={
            "model": "gpt-3.5-turbo",
            "messages": [
                {
                    "role": "system",
                    "content": "You are an assistant creating personalized follow-up messages.",
                },
                {
                    "role": "user",
                    "content": f"Create a short, friendly follow-up message for {name} who joined our service 3 days ago.",
                }
            ]
        }
    )

    personalized_message = ai_response.body["choices"][0]["message"]["content"]

    # Step 4: Send personalized follow-up email
    async def _send_follow_up_email() -> None:
        await send_email(email, personalized_message)

    await context.run("send-follow-up-email", _send_follow_up_email)
```

--------------------------------

TITLE: Upstash Workflow Real World Examples Overview
DESCRIPTION: Provides practical implementations demonstrating the use of the Upstash Agents API in production scenarios. These examples serve as ready-to-use templates for common use cases, highlighting the API's capabilities.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: APIDOC
CODE:
```
RealWorldExamples:
  description: Practical implementations of the Upstash Agents API for production scenarios.
  purpose: Provide ready-to-use templates for common use cases.
```

--------------------------------

TITLE: Run Flask Application
DESCRIPTION: Starts the Flask development server on port 8000. This command is used to run the application defined in 'main.py'.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
flask --app main run -p 8000
```

--------------------------------

TITLE: Register User and Send Welcome Email (Python)
DESCRIPTION: Demonstrates registering a new user and sending a welcome email as the initial step in a customer onboarding workflow. It uses `context.run` to execute the email sending operation, ensuring it's tracked and retried by the workflow engine.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _new_signup() -> None:
    await send_email("Welcome to the platform", email)

await context.run("new-signup", _new_signup)
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Python (FastAPI)
DESCRIPTION: Sets up a Python virtual environment and installs the necessary packages for Upstash Workflow with FastAPI. This includes `fastapi`, `uvicorn` for the ASGI server, and the `upstash-workflow` SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Command to start the local QStash server for local development and testing of Upstash Workflows. This command requires the @upstash/qstash-cli package.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Initialize Vercel Project Deployment
DESCRIPTION: Initiates the Vercel deployment process for the current project. It guides the user through setting up the project on Vercel, which is a prerequisite before deploying to production.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Source Environment Variables
DESCRIPTION: Loads environment variables from the .env file into the current shell session. This is necessary before starting the development server.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
source .env
```

--------------------------------

TITLE: Trigger Upstash Workflow Endpoint with JavaScript
DESCRIPTION: This JavaScript code snippet demonstrates how to initialize the Upstash Workflow client and trigger a workflow. It requires environment variables for the Upstash URL and token, and specifies the endpoint URL and a JSON body for the request.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({
  baseUrl: process.env.QSTASH_URL,
  token: process.env.QSTASH_TOKEN!,
})
const workflowRunId = await client.trigger({
  url: "http://127.0.0.1:3000/workflow",
  body: { prompt: "Explain the future of space exploration" },
})
console.log(workflowRunId);
```

--------------------------------

TITLE: Run Express.js Application
DESCRIPTION: Starts the Express.js development server. Once running, you can send POST requests to the defined workflow endpoint to trigger workflow execution.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server for development. This command provides QSTASH_URL and QSTASH_TOKEN values to be added to your .env file for local testing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/astro

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Register User and Send Welcome Email (Python)
DESCRIPTION: Demonstrates user registration and sending a welcome email using `context.run` for asynchronous execution and workflow tracking.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _new_signup() -> None:
    await send_email("Welcome to the platform", email)

await context.run("new-signup", _new_signup)
```

--------------------------------

TITLE: Deploy Project with Vercel
DESCRIPTION: Initiates the Vercel deployment process for the current project. This command guides users through setting up the project on Vercel, a prerequisite for production deployment.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel
```

--------------------------------

TITLE: Example AI Response for Physics Q&A (Markdown)
DESCRIPTION: An example of synthesized output from worker agents, presenting a Q&A on quantum mechanics principles. This demonstrates agent collaboration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```

```

--------------------------------

TITLE: Workflow Setup with API Call Loop
DESCRIPTION: This TypeScript code snippet illustrates the initial setup for a workflow that includes a loop for making API calls. It defines the `POST` endpoint using Upstash Workflow's `serve` function and sets up a loop to attempt an API call up to 10 times.

SOURCE: https://upstash.com/docs/workflow/examples/customRetry

LANGUAGE: TypeScript
CODE:
```
export const { POST } = serve<{ userData: string }>(async (context) => {
  for (let attempt = 0; attempt < 10; attempt++) {
    // TODO: call API in here
  }
})
```

--------------------------------

TITLE: Start Trial in Stripe with Upstash Workflow
DESCRIPTION: This example shows how to initiate a trial for a user in Stripe using Upstash Workflow. It defines an asynchronous function `_start_trial_in_stripe` that calls `start_trial_in_stripe` with the user's email, and then executes this function within the workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _start_trial_in_stripe() -> None:
    await start_trial_in_stripe(email)

await context.run("start trial in Stripe", _start_trial_in_stripe)
```

--------------------------------

TITLE: Start SolidJS Development Server
DESCRIPTION: Starts the SolidJS development server, after which workflow endpoints can be triggered via POST requests.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Setting Up Basic Webhook Endpoint
DESCRIPTION: Demonstrates setting up a basic webhook endpoint using the `serve` function. This example shows how to initialize an endpoint that receives webhook payloads and uses `initialPayloadParser` for custom parsing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(
  async (context) => {
    // Your webhook handling logic here
  },
  {
    initialPayloadParser: (payload) => {
      return payload;
    },
  }
);
```

LANGUAGE: Python
CODE:
```
from fastapi import FastAPI
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext

app = FastAPI()
serve = Serve(app)


def initial_payload_parser(payload):
    return payload


@serve.post("/api/example", initial_payload_parser=initial_payload_parser)
async def example(context: AsyncWorkflowContext[str]) -> None:
    # Your webhook handling logic here


```

--------------------------------

TITLE: Install Upstash Workflow SDK - bun
DESCRIPTION: Installs the Upstash Workflow SDK using bun for Express.js and Nuxt.js projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Next.js
DESCRIPTION: Installs the `@upstash/workflow` SDK into a Next.js project, enabling the development of Upstash Workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Start SvelteKit Development Server
DESCRIPTION: Starts the SvelteKit development server, making the defined workflow endpoint accessible for local testing and interaction. This command is used to run the SvelteKit application locally.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Quantum Mechanics Explanation Example
DESCRIPTION: An example of generated text output from an AI agent, providing a concise explanation of quantum mechanics. This demonstrates the successful operation of a generator-evaluator workflow in producing refined content.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Plain Text
CODE:
```
Quantum mechanics is a branch of physics that describes the behavior of particles at the smallest scales, such as atoms and subatomic particles. It introduces the concept of quantized energy levels, wave-particle duality, and probabilistic nature of particles. In quantum mechanics, particles can exist in multiple states simultaneously until measured, and their behavior is governed by mathematical equations known as wave functions. This theory has revolutionized our understanding of the fundamental building blocks of the universe and has led to the development of technologies like quantum computing and quantum cryptography.
```

--------------------------------

TITLE: Trigger Workflow via HTTP Request (fetch - TypeScript)
DESCRIPTION: Illustrates triggering a workflow endpoint using the `fetch` API in TypeScript. This example shows how to make a POST request with custom headers and a JSON payload.

SOURCE: https://upstash.com/docs/workflow/howto/start

LANGUAGE: typescript
CODE:
```
fetch('https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'my-header': 'foo'
  },
  body: JSON.stringify({ foo: 'bar' })
});

```

--------------------------------

TITLE: Start Astro Development Server
DESCRIPTION: Starts the Astro development server, enabling local access to the workflow endpoint for testing purposes.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Browser Automation Example
DESCRIPTION: Demonstrates an autonomous web navigation and interaction system for content extraction and form handling using Upstash Agents.

SOURCE: https://upstash.com/docs/workflow/agents/examples

LANGUAGE: javascript
CODE:
```
/*
 * Example: Browser Automation
 * This example demonstrates how to automate web navigation and interaction.
 */

// Assume 'agent' is an instance of the Upstash Agent
// const agent = new UpstashAgent();

async function automateBrowser() {
  console.log('Starting browser automation...');

  // Example: Navigate to a website
  // await agent.navigate('https://example.com');

  // Example: Extract content from a page
  // const pageContent = await agent.extractContent('h1');
  // console.log('Page Title:', pageContent);

  // Example: Fill out a form
  // await agent.fillForm('input[name="username"]', 'testuser');
  // await agent.fillForm('input[name="password"]', 'password123');
  // await agent.submitForm('form');

  console.log('Browser automation finished.');
}

// automateBrowser();
```

--------------------------------

TITLE: Trigger Workflow via HTTP Request (requests - Python)
DESCRIPTION: Demonstrates how to trigger a workflow endpoint using the `requests` library in Python. This example shows sending a POST request with custom headers and a JSON body.

SOURCE: https://upstash.com/docs/workflow/howto/start

LANGUAGE: python
CODE:
```
import requests

response = requests.post(
    'https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>',
    headers={'my-header': 'foo'},
    json={'foo': 'bar'}
)

```

--------------------------------

TITLE: Trigger Workflow via HTTP Request (curl)
DESCRIPTION: Provides an example of how to trigger a workflow endpoint using a `curl` command. This method is suitable for quick testing and demonstrates sending a POST request with custom headers and a JSON body.

SOURCE: https://upstash.com/docs/workflow/howto/start

LANGUAGE: bash
CODE:
```
curl -X POST https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE> \
     -H "my-header: foo" \
     -d '{"foo": "bar"}'

```

--------------------------------

TITLE: Upstash Workflow Setup with Retry Loop (TypeScript)
DESCRIPTION: Initializes an Upstash Workflow endpoint and sets up a loop for retrying external API calls up to 10 times. This example uses TypeScript and the `serve` function.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<{ userData: string }>(async (context) => {
  for (let attempt = 0; attempt < 10; attempt++) {
    // TODO: call API in here
  }
})
```

--------------------------------

TITLE: Upstash Workflow Setup with Retry Loop (Python)
DESCRIPTION: Initializes an Upstash Workflow endpoint and sets up a loop for retrying external API calls up to 10 times. This example uses Python and the `serve.post` decorator.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/custom-retry-logic")
async def custom_retry_logic(context: AsyncWorkflowContext[InitialData]) -> None:
    for attempt in range(10):
        # TODO: call API in here
```

--------------------------------

TITLE: Start Local QStash Server (Bash)
DESCRIPTION: Initiates a local QStash development server using the `@upstash/qstash-cli`. This allows for local testing of Upstash Workflows without affecting production billing or logs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK using npm, pnpm, or bun. This is a prerequisite for using Upstash Workflow in your projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK into a project using different package managers (bun, pnpm). This makes the necessary libraries available for building workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

--------------------------------

TITLE: Install @upstash/workflow SDK
DESCRIPTION: Installs the new @upstash/workflow package using npm. If @upstash/qstash was only used for workflow, it can be uninstalled.

SOURCE: https://upstash.com/docs/workflow/migration

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: Define Upstash Workflow Endpoint in Next.js
DESCRIPTION: Defines a workflow endpoint in a Next.js application using Upstash Workflow, AI, and Zod. It sets up an agent with a communication tool and a background task to process a prompt.

SOURCE: https://upstash.com/docs/workflow/agents/getting-started

LANGUAGE: typescript
CODE:
```
import {
  z,
} from "zod";
import { tool } from "ai";
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<{ prompt: string }>(async (context) => {
  const prompt = context.requestPayload.prompt;
  const model = context.agents.openai('gpt-3.5-turbo');
  const communicatorAgent = context.agents.agent({
    model,
    name: 'communicatorAgent',
    maxSteps: 2,
    tools: {
      communicationTool: tool({
        description: 'A tool for informing the caller about your inner thoughts',
        parameters: z.object({ message: z.string() }),
        execute: async ({ message }) => {
          console.log("Inner thought:", message);
          return "success";
        },
      }),
    },
    background:
      'Answer questions directed towards you.' +
      ' You have access to a tool to share your inner thoughts'
      ' with the caller. Utilize this tool at least once before'
      ' answering the prompt. In your inner thougts, briefly'
      ' explain what you will talk about and why. Keep your' +
      ' answers brief.',
  });
  const task = context.agents.task({
    agent: communicatorAgent,
    prompt,
  });
  const { text } = await task.run();
  console.log("Final response:", text);
});

```

--------------------------------

TITLE: Start Next.js Development Server
DESCRIPTION: Starts the Next.js development server, making defined workflow endpoints accessible locally for testing and development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Write Durable Serverless Functions with Upstash Workflow
DESCRIPTION: Upstash Workflow allows you to write durable serverless functions. This section introduces the concept and provides guidance on getting started.

SOURCE: https://upstash.com/docs/workflow/basics/qstash/features/callbacks

LANGUAGE: General
CODE:
```
Upstash Workflow
Write durable serverless functions
```

--------------------------------

TITLE: Start Nuxt Development Server (Bash)
DESCRIPTION: Command to start the Nuxt.js development server, making the workflow endpoint accessible for testing and triggering.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Initiates a local QStash server for development purposes using the QStash CLI. This allows for local workflow testing without affecting production billing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Install Project Dependencies with Poetry
DESCRIPTION: Installs all project dependencies defined in the pyproject.toml file using Poetry. This is a crucial step for setting up the Python development environment.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
poetry install
```

--------------------------------

TITLE: Handling Webhook Events with context.run (TypeScript)
DESCRIPTION: Shows how to process webhook events within discrete, trackable steps using `context.run`. This example specifically handles a 'user.created' event, extracting user data like ID, email, and first name.

SOURCE: https://upstash.com/docs/workflow/howto/use-webhooks

LANGUAGE: TypeScript
CODE:
```
export const { POST } = serve(async (context) => {
  // ... Parse and validate the incoming request
  const user = await context.run<false | UserPayload>(
    "handle-webhook-event",
    async () => {
      if (event.type === "user.created") {
        const { id: clerkUserId, email_addresses, first_name } = event.data;
        const primaryEmail = email_addresses.find(
          (email) => (email.id = event.data.primary_email_address_id)
        );
        if (!primaryEmail) {
          return false;
        }
        return {
          event: event.type,
          userId: clerkUserId,
          email: primaryEmail.email_address,
          firstName: first_name,
        } as UserPayload;
      }
      return false;
    }
  );
});

```

--------------------------------

TITLE: Customer Onboarding Workflow (TypeScript)
DESCRIPTION: This TypeScript code defines a customer onboarding workflow using Upstash. It handles new user signups, sends welcome emails, includes a waiting period, and periodically checks user activity to send targeted emails. The workflow is designed to run indefinitely.

SOURCE: https://upstash.com/docs/workflow/examples/customerOnboarding

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
type InitialData = {
  email: string
}
export const { POST } = serve<InitialData>(async (context) => {
  const { email } = context.requestPayload
  await context.run("new-signup", async () => {
    await sendEmail("Welcome to the platform", email)
  })
  await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)
  while (true) {
    const state = await context.run("check-user-state", async () => {
      return await getUserState()
    })
    if (state === "non-active") {
      await context.run("send-email-non-active", async () => {
        await sendEmail("Email to non-active users", email)
      })
    } else if (state === "active") {
      await context.run("send-email-active", async () => {
        await sendEmail("Send newsletter to active users", email)
      })
    }
    await context.sleep("wait-for-1-month", 60 * 60 * 24 * 30)
  }
})
async function sendEmail(message: string, email: string) {
  // Implement email sending logic here
  console.log(`Sending ${message} email to ${email}`)
}
type UserState = "non-active" | "active"
const getUserState = async (): Promise<UserState> => {
  // Implement user state logic here
  return "non-active"
}
```

--------------------------------

TITLE: Start SolidJS Development Server
DESCRIPTION: Starts the SolidJS development server, typically accessible at `localhost:3000`. This command makes your SolidJS application and its workflow endpoints available for local testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK - npm
DESCRIPTION: Installs the Upstash Workflow SDK using npm for Express.js and Nuxt.js projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK - pnpm
DESCRIPTION: Installs the Upstash Workflow SDK using pnpm for Express.js and Nuxt.js projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

--------------------------------

TITLE: Install Project Dependencies
DESCRIPTION: Installs the necessary Node.js dependencies for the Next.js & Flask project using npm.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: shell
CODE:
```
npm install
```

--------------------------------

TITLE: Create Workflow Endpoint (Nuxt.js)
DESCRIPTION: Defines a workflow endpoint in a Nuxt.js project's server/api directory using the Upstash Workflow SDK. It includes two example steps.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/h3"
const { handler } = serve(
  async (context) => {
    await context.run("initial-step", () => {
      console.log("initial step ran")
    })
    await context.run("second-step", () => {
      console.log("second step ran")
    })
  },
)
export default handler;

```

--------------------------------

TITLE: Start Next.js Development Server
DESCRIPTION: Initiates the Next.js development server, which typically also starts the Flask application. This allows for local development and testing of frontend and backend components.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK with FastAPI
DESCRIPTION: Installs the necessary Python packages for Upstash Workflow and FastAPI, along with Uvicorn for running the application. It also shows how to set up a virtual environment and configure the QStash token.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-py

LANGUAGE: Shell
CODE:
```
python -m venv venv
source venv/bin/activate
pip install fastapi uvicorn upstash-workflow
```

LANGUAGE: Shell
CODE:
```
export QSTASH_TOKEN=
```

--------------------------------

TITLE: Setup FastAPI Workflow with Upstash (Python)
DESCRIPTION: Demonstrates the initial setup for integrating Upstash Workflow with a FastAPI application in Python. It imports necessary modules and initializes the FastAPI app and Upstash Workflow Serve instance.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
from fastapi import FastAPI
from typing import Dict, TypedDict
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext, CallResponse
from email_utils import send_email

app = FastAPI()
serve = Serve(app)
```

--------------------------------

TITLE: Install @upstash/workflow (Bash)
DESCRIPTION: Installs the `@upstash/workflow` package using npm. It also suggests uninstalling `@upstash/qstash` if it was only used for workflow purposes.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK (Bash)
DESCRIPTION: Installs the `@upstash/workflow` SDK using various package managers (pnpm, Bun, npm) for workflow development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Deploy Project on Vercel
DESCRIPTION: Command to initiate the deployment process for your project on Vercel. This typically involves setting up the project and its configurations.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Bash
CODE:
```
vercel
```

--------------------------------

TITLE: Register New User and Send Welcome Email
DESCRIPTION: Demonstrates registering a new user and sending a welcome email as the initial step in a customer onboarding workflow. It uses `context.run` to execute an asynchronous function for sending the email, ensuring tracking and retries by the workflow engine.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("new-signup", async () => {
  await sendEmail("Welcome to the platform", email)
})
```

--------------------------------

TITLE: Add Agent Examples
DESCRIPTION: This commit includes new examples demonstrating the use of agents within the workflow system, showcasing advanced use cases and integration patterns.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: JavaScript
CODE:
```
DX-1580: Add Agent Examples (#59)
```

--------------------------------

TITLE: Customer Onboarding Workflow - Python
DESCRIPTION: Implements a customer onboarding workflow in Python using FastAPI and Upstash Workflow. It handles user registration, welcome emails, and periodic activity checks with follow-up emails. Utilizes `context.run` for atomic operations and `context.sleep` for non-blocking delays.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from fastapi import FastAPI
from typing import Literal, TypedDict
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext

app = FastAPI()
serve = Serve(app)

UserState = Literal["non-active", "active"]


class InitialData(TypedDict):
    email: str


async def send_email(message: str, email: str) -> None:
    # Implement email sending logic here
    print(f"Sending {message} email to {email}")


async def get_user_state() -> UserState:
    # Implement user state logic here
    return "non-active"


@serve.post("/customer-onboarding")
async def customer_onboarding(context: AsyncWorkflowContext[InitialData]) -> None:
    email = context.request_payload["email"]

    async def _new_signup() -> None:
        await send_email("Welcome to the platform", email)

    await context.run("new-signup", _new_signup)

    await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)

    while True:

        async def _check_user_state() -> UserState:
            return await get_user_state()

        state: UserState = await context.run("check-user-state", _check_user_state)

        if state == "non-active":

            async def _send_email_non_active() -> None:
                await send_email("Email to non-active users", email)

            await context.run("send-email-non-active", _send_email_non_active)
        else:

            async def _send_email_active() -> None:
                await send_email("Send newsletter to active users", email)

            await context.run("send-email-active", _send_email_active)

        await context.sleep("wait-for-1-month", 60 * 60 * 24 * 30)
```

--------------------------------

TITLE: Social Media Manager Example
DESCRIPTION: Illustrates a multi-platform social media management system for content moderation and engagement automation using Upstash Agents.

SOURCE: https://upstash.com/docs/workflow/agents/examples

LANGUAGE: javascript
CODE:
```
/*
 * Example: Social Media Manager
 * This example demonstrates social media management automation.
 */

// Assume 'agent' is an instance of the Upstash Agent
// const agent = new UpstashAgent();

async function manageSocialMedia(postContent, platform) {
  console.log(`Managing social media on ${platform}...`);

  // Example: Post content to a platform
  // await agent.postContent(postContent, platform);
  // console.log('Content posted successfully.');

  // Example: Moderate comments
  // const comments = await agent.getComments(platform);
  // const moderatedComments = await agent.moderateContent(comments);
  // console.log('Moderated comments:', moderatedComments);

  // Example: Automate engagement
  // await agent.automateEngagement(platform);
  // console.log('Engagement automated.');

  console.log('Social media management complete.');
}

// manageSocialMedia('Check out our new blog post!', 'twitter');
```

--------------------------------

TITLE: Install Upstash Workflow SDK and FastAPI (pip)
DESCRIPTION: Installs essential Python packages for building web APIs with FastAPI and integrating Upstash Workflow. This includes `fastapi`, `uvicorn` for running the ASGI application, and the `upstash-workflow` SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Install Node.js Packages
DESCRIPTION: Installs all required Node.js packages and their dependencies from the 'package.json' file. This is crucial for Next.js applications to run correctly.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install
```

--------------------------------

TITLE: Install Upstash Workflow SDK with npm
DESCRIPTION: This command installs the `@upstash/workflow` SDK into your SolidJS project using npm, making the necessary libraries available for building workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install FastAPI and Upstash Workflow SDK (Bash)
DESCRIPTION: Installs the necessary Python packages for FastAPI and the Upstash Workflow SDK. It assumes a virtual environment is already activated.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: Installs the Upstash Workflow SDK for Node.js projects using npm. This is the first step to integrate workflow capabilities into your application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/svelte

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Start Next.js Development Server
DESCRIPTION: Starts the Next.js development server, typically on http://localhost:3000, enabling hot-reloading for frontend development interacting with Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Fetch Upstash Workflow Logs with cURL (Shell)
DESCRIPTION: Demonstrates how to retrieve workflow execution logs using a cURL command. This example shows the necessary GET request to the QStash API logs endpoint, including the required Authorization header with a bearer token.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/workflows/logs \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Deploy Project with Vercel CLI
DESCRIPTION: Initiates the deployment process for a project using the Vercel CLI. This command typically guides the user through project linking and configuration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: shell
CODE:
```
vercel
```

--------------------------------

TITLE: Install Upstash Workflow SDK with npm
DESCRIPTION: Installs the `@upstash/workflow` SDK using npm. This is part of the migration process to separate Workflow development from the QStash SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Customer Onboarding Workflow - TypeScript
DESCRIPTION: Initializes a customer onboarding workflow in TypeScript. It registers a new user, sends a welcome email, waits for three days, and then enters a loop to periodically check user activity and send follow-up emails. Uses `context.run` for atomic operations and `context.sleep` for delays.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"

type InitialData = {
  email: string
}

export const { POST } = serve<InitialData>(async (context) => {
  const { email } = context.requestPayload

  await context.run("new-signup", async () => {
    await sendEmail("Welcome to the platform", email)
  })

  await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)

  while (true) {
    const state = await context.run("check-user-state", async () => {
      return await getUserState()
    })

    if (state === "non-active") {
      await context.run("send-email-non-active", async () => {
        await sendEmail("Email to non-active users", email)
      })
    } else if (state === "active") {
      await context.run("send-email-active", async () => {
        await sendEmail("Send newsletter to active users", email)
      })
    }

    await context.sleep("wait-for-1-month", 60 * 60 * 24 * 30)
  }
})

async function sendEmail(message: string, email: string) {
  // Implement email sending logic here
  console.log(`Sending ${message} email to ${email}`)
}

type UserState = "non-active" | "active"

const getUserState = async (): Promise<UserState> => {
  // Implement user state logic here
  return "non-active"
}
```

--------------------------------

TITLE: Install Node.js Dependencies
DESCRIPTION: Installs all required Node.js packages and their dependencies from 'package.json'. This command is essential for the Next.js frontend application to run correctly.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install
```

--------------------------------

TITLE: Install Upstash Workflow SDK and Dependencies (Python/Bun)
DESCRIPTION: Installs necessary packages for building web APIs and integrating Upstash Workflow. This includes FastAPI and Uvicorn for Python, and the Upstash Workflow SDK for Node.js/Bun projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Get User Stats and Send Email with Upstash Workflow
DESCRIPTION: This example demonstrates fetching user statistics and sending an email containing these stats. It defines `_get_user_stats` to retrieve data using `get_user_stats`, runs it in the workflow, and then calls `send_problem_solved_email` with the retrieved stats.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
# get user stats and send email with them

async def _get_user_stats() -> UserStats:
    return await get_user_stats(userid)

stats: UserStats = await context.run("get user stats", _get_user_stats)

await send_problem_solved_email(context, email, stats)
```

--------------------------------

TITLE: Register User and Send Welcome Email (TypeScript)
DESCRIPTION: Demonstrates registering a new user and sending a welcome email as the initial step in a customer onboarding workflow. It uses `context.run` to execute the email sending operation, ensuring it's tracked and retried by the workflow engine.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("new-signup", async () => {
  await sendEmail("Welcome to the platform", email)
})
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash development server using 'npx @upstash/qstash-cli dev'. This is crucial for local testing of workflows, providing necessary environment variables like QSTASH_URL and QSTASH_TOKEN without affecting production environments.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server using the QStash CLI. This command is used for local development and testing of Upstash Workflows without affecting production billing. It outputs QSTASH_URL and QSTASH_TOKEN.

SOURCE: https://upstash.com/docs/workflow/quickstarts/hono

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Upstash Workflow Base Serve Method (TypeScript)
DESCRIPTION: Provides a foundational TypeScript example for the 'serve' method in Upstash Workflow, suitable for integration with custom platforms not explicitly detailed in the documentation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow";
```

--------------------------------

TITLE: Example DLQ Workflow Run Response (JSON)
DESCRIPTION: This JSON object represents a typical response when retrieving a failed workflow run from the DLQ. It includes details about the message, workflow, failure, and DLQ ID.

SOURCE: https://upstash.com/docs/workflow/rest/dlq/get

LANGUAGE: json
CODE:
```
{
  "messageId":"msg_26hZCxZCuWyyTWPmSVBrNC1RADwpgWxPcak2rQD51EMjFMuzcW7qYXpPiDyw8Gd",
  "url":"https://my.app/workflow",
  "method":"POST",
  "header":{
    "Content-Type":[
        "application/json"
    ]
  },
  "maxRetries":10,
  "notBefore":1752829294505,
  "createdAt":1752829294505,
  "failureCallback":"https://my.app/workflow",
  "callerIP":"88.240.188.2",
  "workflowRunId":"wfr_5XAx4IJergqkGK1v23VzR",
  "workflowCreatedAt":1752829293531,
  "workflowUrl":"https://my.app/workflow",
  "responseStatus":489,
  "responseHeader":{
    "Content-Type":[
        "text/plain;charset=UTF-8"
    ]
  },
  "responseBody":"{\"error\":\"WorkflowNonRetryableError\",\"message\":\"this workflow has stopped\"}",
  "failureCallbackInfo":{
    "state":"CALLBACK_SUCCESS",
    "responseStatus":200,
    "responseBody":"{\"workflowRunId\":\"wfr_Q_khHG-a414M-xKRh2kNI\"}",
    "responseHeaders":{
        "Content-Type":[
          "text/plain;charset=UTF-8"
        ]
    }
  },
  "dlqId":"1752829295505-0"
}
```

--------------------------------

TITLE: Define Researcher Agent with OpenAI and Wikipedia Tool
DESCRIPTION: Defines a `researcherAgent` using an OpenAI model and a Wikipedia tool, specifying its name, maximum steps, and a background prompt to guide its behavior. This setup allows the agent to perform research tasks using Wikipedia.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: ts
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
import { WikipediaQueryRun } from "@langchain/community/tools/wikipedia_query_run"

export const { POST } = serve(async (context) => {
  const model = context.agents.openai('gpt-3.5-turbo')

  const researcherAgent = context.agents.agent({
    model,
    name: 'academic',
    maxSteps: 2,
    tools: {
      wikiTool: new WikipediaQueryRun({
        topKResults: 1,
        maxDocContentLength: 500,
      })
    },
    background:
      'You are researcher agent with access to Wikipedia. '
      'Utilize Wikipedia as much as possible for correct information',
  })
})
```

LANGUAGE: ts
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { WikipediaQueryRun } from "@langchain/community/tools/wikipedia_query_run";

export const { POST } = serve(async (context) => {

```

--------------------------------

TITLE: Start Local QStash Server (pnpm)
DESCRIPTION: Starts the local QStash server using pnpm dlx for users preferring pnpm. This provides the necessary local environment for Upstash Workflow development and testing, yielding local QSTASH_URL and QSTASH_TOKEN values.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm dlx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK package using npm. This is the first step to integrating Upstash Workflow into your project.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: Install Upstash Workflow SDK with pnpm
DESCRIPTION: Installs the Upstash Workflow SDK into your Hono project using the pnpm package manager.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

--------------------------------

TITLE: Configure .env.local for Local QStash Server (txt)
DESCRIPTION: Provides an example configuration for a `.env.local` file when using a local QStash server. It specifies the `QSTASH_URL` for the local server and `QSTASH_TOKEN` obtained from the CLI.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Install Upstash Workflow Packages (npm, pnpm, bun)
DESCRIPTION: Installs the necessary packages for integrating Vercel AI SDK with Upstash Workflow using npm, pnpm, or bun. These packages include `@ai-sdk/openai`, `ai`, and `zod`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @ai-sdk/openai ai zod
```

LANGUAGE: bash
CODE:
```
pnpm install @ai-sdk/openai ai zod
```

LANGUAGE: bash
CODE:
```
bun install @ai-sdk/openai ai zod
```

--------------------------------

TITLE: Create Virtual Environment and Activate
DESCRIPTION: Sets up a Python virtual environment named 'venv' and activates it. This isolates project dependencies and ensures a clean development environment.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Start Local Upstash QStash Server (npx)
DESCRIPTION: Initiates a local QStash server using the `@upstash/qstash-cli` tool. This provides a local endpoint for testing Upstash Workflow without interacting with the production service, yielding local QSTASH_URL and QSTASH_TOKEN.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Full Upstash Workflow Example: Data Processing and Reporting
DESCRIPTION: Illustrates a comprehensive workflow that includes downloading data, processing it in chunks using OpenAI, generating a report, and sending it. It utilizes Upstash's `serve` function and `context.run`/`context.call` for task management and external requests.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
import {
  downloadData,
  aggregateResults,
  generateReport,
  sendReport,
  getDatasetUrl,
  splitIntoChunks,
} from "./utils"
type OpenAiResponse = {
  choices: {
    message: {
      role: string,
      content: string
    }
  }[]
}
export const { POST } = serve<{ datasetId: string; userId: string }>
(
  async (context) => {
    const request = context.requestPayload
    // Step 1: Download the dataset
    const datasetUrl = await context.run("get-dataset-url", async () => {
      return await getDatasetUrl(request.datasetId)
    })
    // HTTP request with much longer timeout (2hrs)
    const { body: dataset } = await context.call("download-dataset", {
      url: datasetUrl,
      method: "GET"
    })
    // Step 2: Process data in chunks using OpenAI
    const chunkSize = 1000
    const chunks = splitIntoChunks(dataset, chunkSize)
    const processedChunks: string[] = []
    for (let i = 0; i < chunks.length; i++) {
      const { body: processedChunk } = await context.api.openai.call
        (`process-chunk-${i}`,
         {
          token: process.env.OPENAI_API_KEY,
          operation: "chat.completions.create",
          body: {
            model: "gpt-4",
            messages: [
              {
                role: "system",
                content:
                  "You are an AI assistant tasked with analyzing data chunks. Provide a brief summary and key insights for the given data.",
              },
              {
                role: "user",

```

--------------------------------

TITLE: Start Next.js Development Server (Bash)
DESCRIPTION: Starts the Next.js development server, usually on `http://localhost:3000`, enabling hot-reloading for frontend development interacting with FastAPI and Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK for SolidJS
DESCRIPTION: Installs the Upstash Workflow SDK using npm. This is the first step to integrate Upstash Workflows into a SolidJS project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Example Response from Multi-Agent Workflow
DESCRIPTION: An example of a response generated by a multi-agent workflow, detailing information about three Japanese cities and their combined populations.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: text
CODE:
```
Here is a brief overview of three cities in Japan:
### Tokyo
- **Official Name**: Tokyo Metropolis
- **Population**: Over 14 million in the city proper as of 2023.
- **Significance**: Capital of Japan and one of the most populous urban areas in the world.
### Osaka
- **Japanese Name**: å¤§éå¸ (Åsaka-shi)
- **Population**: 2.7 million as per the 2020 census.
- **Significance**: Capital and most populous city in Osaka Prefecture, third-most populous city in Japan.
### Kyoto
- **Japanese Name**: äº¬é½å¸ (KyÅto-shi)
- **Population**: 1.46 million as of 2020.
- **Significance**: Capital city of Kyoto Prefecture, ninth-most populous city in Japan.
The sum of their populations is approximately 18.16 million.

```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK using npm. This is the first step to integrate Upstash Workflow into your Hono project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: npm
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Node.js Project Dependencies
DESCRIPTION: Installs all required Node.js packages and their dependencies from the `package.json` file. This command is crucial for setting up frontend applications, such as those built with Next.js.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install
```

--------------------------------

TITLE: Start Local QStash Server (Bash)
DESCRIPTION: Starts the local QStash CLI in development mode, outputting QSTASH_URL and QSTASH_TOKEN for local testing. This command is useful for local development and testing workflows without incurring costs or affecting Upstash Console logs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Install Agent and Tool Packages
DESCRIPTION: Installs necessary npm packages for working with AI SDK, Agentic, and LangChain, which are prerequisites for using the Workflow Agents API.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i ai mathjs zod @agentic/ai-sdk @agentic/weather @langchain/core @langchain/community
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Express.js
DESCRIPTION: Installs the Upstash Workflow SDK using npm, which is the initial step for integrating Upstash Workflow into an Express.js project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Astro
DESCRIPTION: Installs the Upstash Workflow SDK for Astro projects using npm, enabling integration with Upstash Workflow services.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Run Upstash Workflow Server
DESCRIPTION: Instructions to run the Upstash Workflow server. This involves creating a public URL using a tool like ngrok, setting the UPSTASH_WORKFLOW_URL environment variable, and starting the server with uvicorn.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http localhost:8000
```

LANGUAGE: bash
CODE:
```
export UPSTASH_WORKFLOW_URL=
```

LANGUAGE: bash
CODE:
```
source .env
```

LANGUAGE: bash
CODE:
```
uvicorn main:app --reload
```

--------------------------------

TITLE: Start Hono Application Locally
DESCRIPTION: Executes the development script to start the Hono application locally, typically making the workflow endpoint accessible at `http://localhost:8787`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow Packages with npm
DESCRIPTION: Installs the Upstash Workflow, AI, and Zod packages using npm, which are essential for building workflows with Upstash.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i @upstash/workflow ai zod
```

--------------------------------

TITLE: Add Email Analyzer Example
DESCRIPTION: This commit adds an example for an email analyzer, demonstrating how to process and analyze email data within the workflow system.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: JavaScript
CODE:
```
add email analyzer example (#52)
```

--------------------------------

TITLE: Configure .env file for Upstash
DESCRIPTION: Creates a .env file and sets environment variables for QStash URL and token. This is crucial for authenticating with the QStash service during local development.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
touch .env
export QSTASH_URL="http://127.0.0.1:8080"
export QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Run Development Server (Bash)
DESCRIPTION: Starts the development server for Nuxt.js or Next.js applications.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Send Welcome Email
DESCRIPTION: This snippet is responsible for sending a welcome email to a new user. The email typically includes information about their trial and platform benefits.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
await context.run("send welcome email", async () => {
  await sendEmail(
    email,
    "Welcome to our platform!, You have 14 days of free trial."
  );
});
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK in a project using various package managers like npm, pnpm, or bun. This is the initial step for integrating Upstash Workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: npm
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: pnpm
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bun
CODE:
```
bun add @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Starting Next.js Development Server
DESCRIPTION: This command initiates the Next.js development server, which also typically triggers the Flask application. Once running, the application is accessible locally, allowing for development and testing of both the frontend and backend components.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Vercel AI SDK Packages
DESCRIPTION: Installs necessary packages for integrating Vercel AI SDK with Upstash Workflow, including '@ai-sdk/openai', 'ai', and 'zod'. Supports npm, pnpm, and bun.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @ai-sdk/openai ai zod
```

LANGUAGE: bash
CODE:
```
pnpm install @ai-sdk/openai ai zod
```

LANGUAGE: bash
CODE:
```
bun install @ai-sdk/openai ai zod
```

--------------------------------

TITLE: Install Upstash Workflow SDK in Next.js
DESCRIPTION: Installs the `@upstash/workflow` SDK in a Next.js project using npm. This is a foundational step for using Upstash Workflow features.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK for SvelteKit
DESCRIPTION: Installs the Upstash Workflow SDK into your SvelteKit project using npm. This is the first step to integrating Upstash Workflow capabilities into your application.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Shell
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Email Analyzer Example
DESCRIPTION: Showcases an intelligent email processing system for content analysis, classification, and automated responses using Upstash Agents.

SOURCE: https://upstash.com/docs/workflow/agents/examples

LANGUAGE: javascript
CODE:
```
/*
 * Example: Email Analyzer
 * This example demonstrates intelligent email processing.
 */

// Assume 'agent' is an instance of the Upstash Agent
// const agent = new UpstashAgent();

async function analyzeEmail(emailContent) {
  console.log('Analyzing email content...');

  // Example: Classify email content
  // const classification = await agent.classifyEmail(emailContent);
  // console.log('Email Classification:', classification);

  // Example: Extract key information
  // const extractedInfo = await agent.extractInformation(emailContent);
  // console.log('Extracted Information:', extractedInfo);

  // Example: Generate an automated response
  // const response = await agent.generateResponse(emailContent, classification);
  // console.log('Automated Response:', response);

  console.log('Email analysis complete.');
}

// const sampleEmail = "Subject: Meeting Reminder\n\nHi Team, just a reminder about our meeting tomorrow at 10 AM.";
// analyzeEmail(sampleEmail);
```

--------------------------------

TITLE: Get Failed Workflow Run from DLQ (curl)
DESCRIPTION: This snippet shows how to retrieve a specific failed workflow run from the Dead Letter Queue (DLQ) using the QStash API. It requires a GET request to the /v2/workflows/dlq/{dlqId} endpoint with an authorization token.

SOURCE: https://upstash.com/docs/workflow/rest/dlq/get

LANGUAGE: curl
CODE:
```
curl -X GET https://qstash.upstash.io/v2/workflows/dlq/my-dlq-id \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Coffee Shop Order Workflow Example
DESCRIPTION: A full example of an Upstash Workflow that handles a coffee shop order. It uses `Promise.all` to concurrently check inventory for coffee beans, cups, and milk. If all items are available, it proceeds to brew coffee and print a receipt.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { checkInventory, brewCoffee, printReceipt } from "@/utils";

export const { POST } = serve(async (ctx) => {
  const [coffeeBeansAvailable, cupsAvailable, milkAvailable] = await Promise.all([
    ctx.run("check-coffee-beans", () => checkInventory("coffee-beans")),
    ctx.run("check-cups", () => checkInventory("cups")),
    ctx.run("check-milk", () => checkInventory("milk")),
  ]);

  if (coffeeBeansAvailable && cupsAvailable && milkAvailable) {
    const price = await ctx.run("brew-coffee", async () => {
      return await brewCoffee({ style: "cappuccino" });
    });
    await printReceipt(price);
  }
});

```

--------------------------------

TITLE: Auth Provider Webhook Workflow
DESCRIPTION: This example demonstrates an authentication provider webhook process using Upstash Workflow. The workflow handles user creation, trial management, and email reminders and notifications.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: javascript
CODE:
```
/*
  This is a conceptual example and would require specific Upstash Workflow SDK implementation.
  The actual code would involve defining workflow steps, state management, and integrations.
*/

// Step 1: Sync User (Receive webhook event)
async function syncUser(event) {
  console.log('Received webhook event:', event);
  // Logic to extract user data from the event
  const userData = {
    email: event.data.email,
    name: event.data.name,
    authProviderId: event.data.id
  };
  return userData;
}

// Step 2: Create New User in Database (Conceptual)
async function createUserInDatabase(userData) {
  console.log('Creating user in database:', userData.email);
  // Replace with actual database interaction (e.g., Upstash Redis, PostgreSQL)
  // await db.createUser(userData);
  return { ...userData, userId: 'user-123' }; // Simulate user creation
}

// Step 3: Create New User in Stripe (Conceptual)
async function createUserInStripe(userData) {
  console.log('Creating user in Stripe:', userData.email);
  // Replace with actual Stripe API integration
  // await stripe.customers.create({
  //   email: userData.email,
  //   name: userData.name
  // });
  return { ...userData, stripeCustomerId: 'stripe-cust-456' }; // Simulate Stripe user creation
}

// Step 4: Start Trial in Stripe (Conceptual)
async function startTrialInStripe(userData) {
  console.log('Starting trial in Stripe for:', userData.email);
  // Replace with actual Stripe API integration for starting a trial
  // await stripe.subscriptions.create({
  //   customer: userData.stripeCustomerId,
  //   items: [{ price: 'price_trial' }], // Example trial price ID
  //   trial_period_days: 14
  // });
  return { ...userData, trialStatus: 'active', trialEndDate: new Date(Date.now() + 14 * 24 * 60 * 60 * 1000) }; // Simulate trial start
}

// Step 5: Send Welcome Email (Conceptual)
async function sendWelcomeEmail(userData) {
  console.log('Sending welcome email to:', userData.email);
  // Replace with actual email service integration (e.g., SendGrid, Nodemailer)
  // await emailService.send({
  //   to: userData.email,
  //   subject: 'Welcome!',
  //   body: 'Welcome to our platform!'
  // });
  return { ...userData, welcomeEmailSent: true };
}

// Step 6: Send Reminder Email (Conceptual)
async function sendReminderEmail(userData) {
  // This would typically be triggered by a scheduled event or a condition check
  console.log('Sending reminder email to:', userData.email);
  // Replace with actual email service integration
  // await emailService.send({
  //   to: userData.email,
  //   subject: 'Reminder',
  //   body: 'Don't forget to complete your questions!'
  // });
  return { ...userData, reminderEmailSent: true };
}

// Step 7: Send Trial Warning Email (Conceptual)
async function sendTrialWarningEmail(userData) {
  // This would typically be triggered by a scheduled event or a condition check
  console.log('Sending trial warning email to:', userData.email);
  // Replace with actual email service integration
  // await emailService.send({
  //   to: userData.email,
  //   subject: 'Your trial is ending soon!',
  //   body: 'Your trial will end in 2 days. Upgrade now!'
  // });
  return { ...userData, trialWarningEmailSent: true };
}

// Step 8: Send Trial Ended Email (Conceptual)
async function sendTrialEndedEmail(userData) {
  // This would typically be triggered by a scheduled event or a condition check
  console.log('Sending trial ended email to:', userData.email);
  // Replace with actual email service integration
  // await emailService.send({
  //   to: userData.email,
  //   subject: 'Your trial has ended',
  //   body: 'Your trial has ended. Please upgrade to continue.'
  // });
  return { ...userData, trialEndedEmailSent: true };
}

// Example of how a workflow might orchestrate these steps:
async function handleAuthWebhook(event) {
  let userState = await syncUser(event);
  userState = await createUserInDatabase(userState);
  userState = await createUserInStripe(userState);
  userState = await startTrialInStripe(userState);
  userState = await sendWelcomeEmail(userState);

  // Conditional or scheduled tasks would be handled by Upstash Workflow's scheduling/condition features
  // For example, checking if user has not solved questions in 7 days to send reminder
  // if (userState.daysSinceLastQuestion >= 7) {
  //   userState = await sendReminderEmail(userState);
  // }

  // Checking if trial ends in 2 days
  // if (userState.trialEndDate && userState.trialEndDate - Date.now() <= 2 * 24 * 60 * 60 * 1000) {
  //   userState = await sendTrialWarningEmail(userState);
  // }

  // Checking if trial has ended
  // if (userState.trialEndDate && userState.trialEndDate < Date.now()) {
  //   userState = await sendTrialEndedEmail(userState);
  // }

  return userState;
}

// To run this conceptually:
// const mockEvent = { data: { id: 'auth0|123', email: 'test@example.com', name: 'Test User' } };
// handleAuthWebhook(mockEvent).then(console.log).catch(console.error);

```

--------------------------------

TITLE: Install Workflow Packages
DESCRIPTION: Installs necessary packages for using the Upstash Workflow Agents API, including AI SDK and LangChain integrations.

SOURCE: https://upstash.com/docs/workflow/agents/features

LANGUAGE: bash
CODE:
```
npm i ai mathjs zod @agentic/ai-sdk @agentic/weather @langchain/core @langchain/community
```

--------------------------------

TITLE: Install Agent and Tool Packages
DESCRIPTION: Installs necessary npm packages for AI SDK, Agentic, and LangChain, which are required for using the Workflow Agents API and defining tools.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i ai mathjs zod @agentic/ai-sdk @agentic/weather @langchain/core @langchain/community
```

--------------------------------

TITLE: Send Welcome Email on Trial Initiation
DESCRIPTION: Sends a welcome email to a user when their trial begins, informing them about the 14-day free trial. This is executed using `context.run`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("send welcome email", async () => {
  await sendEmail(
    email,
    "Welcome to our platform!, You have 14 days of free trial."
  );
});
```

LANGUAGE: python
CODE:
```
async def _send_welcome_email() -> None:
    await send_email(
        email, "Welcome to our platform!, You have 14 days of free trial."
    )

await context.run("send welcome email", _send_welcome_email)
```

--------------------------------

TITLE: Start FastAPI Application with Uvicorn
DESCRIPTION: Starts a FastAPI application using Uvicorn, an ASGI server. The `--reload` flag enables automatic server reloading upon code changes, which is useful for development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
uvicorn main:app --reload
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK for your Astro project using npm. This is the first step to integrating workflow capabilities.

SOURCE: https://upstash.com/docs/workflow/quickstarts/astro

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Serve Method in Python for Upstash Workflow
DESCRIPTION: Illustrates the fundamental 'serve' method in Python for integrating Upstash Workflow with custom platforms. This method can be adapted for platforms not covered in the official quickstarts.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from upstash_workflow import serve
```

--------------------------------

TITLE: Start FastAPI Application with Uvicorn
DESCRIPTION: Starts the FastAPI application using Uvicorn, an ASGI server. The `--reload` flag enables automatic reloading of the server when code changes are detected, facilitating rapid development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
uvicorn main:app --reload
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK using npm. This is the first step to integrate Upstash Workflow into your project.

SOURCE: https://upstash.com/docs/workflow/quickstarts/cloudflare-workers

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Basic Webhook Endpoint Setup (Next.js)
DESCRIPTION: Sets up a basic webhook endpoint using `@upstash/workflow/nextjs`. The `serve` function handles incoming requests and allows for custom logic. Requires the Upstash Workflow SDK for Next.js.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
export const { POST } = serve(
  async (context) => {
    // Your webhook handling logic here
  },
  {
    initialPayloadParser: (payload) => {
      return payload;
    },
  }
);
```

--------------------------------

TITLE: Install Upstash Workflow and AI SDK Packages (npm)
DESCRIPTION: Installs the necessary npm packages for integrating Upstash Workflow with the Vercel AI SDK and Zod for schema validation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @ai-sdk/openai ai zod

```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: Installs the Upstash Workflow SDK using npm. This is a fundamental step for integrating Upstash Workflow into your Node.js projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Shell
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow Agent Dependencies
DESCRIPTION: Installs essential packages for defining tools in Upstash Workflow, including AI SDKs and utility libraries like mathjs and zod.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i ai mathjs zod @agentic/ai-sdk @agentic/weather @langchain/core @langchain/community
```

--------------------------------

TITLE: Install Upstash Workflow SDK
DESCRIPTION: Installs the Upstash Workflow SDK into your project using different package managers (npm, pnpm, bun). This SDK is essential for defining and managing workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Install @upstash/workflow with pnpm or bun
DESCRIPTION: Installs the Upstash Workflow SDK using either pnpm or bun package managers. This is the first step to integrating Upstash Workflow into your project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Nuxt.js
DESCRIPTION: Installs the Upstash Workflow SDK using npm. This is the first step to integrate Upstash Workflow into a Nuxt.js project.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: Start Local QStash Server
DESCRIPTION: Starts a local QStash server using the QStash CLI. This is an option for local development to test workflows without affecting billing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/cloudflare-workers

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Start Stripe Trial (TypeScript/Python)
DESCRIPTION: Initiates a user's trial period in Stripe using the Upstash Workflow context. The `startTrialInStripe` function is called within `context.run` for reliable execution. Requires the user's email.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
await context.run("start trial in Stripe", async () => {
  await startTrialInStripe(email);
});
```

LANGUAGE: Python
CODE:
```
async def _start_trial_in_stripe() -> None:
    await start_trial_in_stripe(email)

await context.run("start trial in Stripe", _start_trial_in_stripe)
```

--------------------------------

TITLE: Install Upstash Workflow SDK (npm)
DESCRIPTION: This command installs the Upstash Workflow SDK into your project using the npm package manager. It's the first step to integrate Upstash Workflow functionality.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow

```

--------------------------------

TITLE: Install Upstash Workflow SDK with pnpm
DESCRIPTION: Installs the '@upstash/workflow' package using the pnpm package manager. This method is useful for separating Workflow development from the QStash SDK.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

--------------------------------

TITLE: Configure Local QStash Server
DESCRIPTION: Sets up environment variables for a local QStash server, including the QSTASH_URL and QSTASH_TOKEN. This allows local testing without affecting billing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev

```

LANGUAGE: dotenv
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>

```

--------------------------------

TITLE: Create .env file
DESCRIPTION: Creates a .env file in the project root to store environment variables, specifically the QStash token required for authentication with the QStash service.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
touch .env
```

--------------------------------

TITLE: Install Upstash Workflow SDK with npm
DESCRIPTION: Installs the Upstash Workflow SDK for Node.js projects using npm. This is the first step to integrate Upstash Workflow into your application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/hono

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Initialize Next.js Project
DESCRIPTION: Initializes a new Next.js project with a specified name and options. This is the first step in setting up the application environment.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx create-next-app@latest [project-name] [options]
```

--------------------------------

TITLE: TypeScript: Upstash Workflow Customer Onboarding
DESCRIPTION: This TypeScript snippet demonstrates a multi-step customer onboarding workflow using Upstash Workflow. It includes sending an initial welcome email, pausing execution for three days using `context.sleep`, generating a personalized follow-up message via OpenAI's API, and finally sending that message as a follow-up email. The `context.run` function ensures individual steps are retried on failure, and `context.api.openai.call` integrates with external services.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";

// Type-safety for starting our workflow
interface InitialData {
  userId: string
  email: string
  name: string
}

export const { POST } = serve<InitialData>(async (context) => {
  const { userId, email, name } = context.requestPayload;

  // Step 1: Send welcome email
  await context.run("send-welcome-email", async () => {
    await sendEmail(email, "Welcome to our service!");
  });

  // Step 2: Wait for 3 days (in seconds)
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);

  // Step 3: AI-generate personalized follow-up message
  const { body: aiResponse } = await context.api.openai.call(
    "generate-personalized-message",
    {
      token: "<OPENAI_API_KEY>",
      operation: "chat.completions.create",
      body: {
        model: "gpt-3.5-turbo",
        messages: [
          { role: "system", content: "You are an assistant creating personalized follow-up messages." },
          { role: "user", content: `Create a short, friendly follow-up message for ${name} who joined our service 3 days ago.` }
        ]
      }
    }
  );

  const personalizedMessage = aiResponse.choices[0].message.content;

  // Step 4: Send personalized follow-up email
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, personalizedMessage);
  });
});
```

--------------------------------

TITLE: Install Upstash Workflow and AI SDK Packages
DESCRIPTION: Installs the necessary npm packages for Upstash Workflow and AI SDK integration, including `@ai-sdk/openai` and `ai`. This is a prerequisite for implementing AI features with Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/integrations/aisdk

LANGUAGE: bash
CODE:
```
npm install @ai-sdk/openai ai zod
```

--------------------------------

TITLE: Start Trial in Stripe Step (TypeScript)
DESCRIPTION: This code snippet represents the 'start trial in Stripe' step within the Upstash Workflow. It calls a function to initiate a 14-day free trial for the user in Stripe.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("start trial in Stripe", async () => {
  await startTrialInStripe(email);
});
```

--------------------------------

TITLE: Install Upstash Workflow SDK with pnpm
DESCRIPTION: Installs the new `@upstash/workflow` package using the pnpm package manager. This method is recommended for managing dependencies and migrating from older SDK versions.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

--------------------------------

TITLE: Bash: Configure QStash Environment Variables
DESCRIPTION: Sets up the .env file for local QStash development, including the QStash URL and token. It also shows how to start a local QStash server using the QStash CLI.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
touch .env

npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Trigger Workflow with client.trigger (JavaScript)
DESCRIPTION: Demonstrates how to use the Upstash Workflow client's `trigger` method to start a workflow. This method allows for specifying the request body, headers, workflow run ID, retries, delay, failure URL, and flow control settings.

SOURCE: https://upstash.com/docs/workflow/howto/start

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" })
const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: "hello there!",         // optional body
  headers: { ... },             // optional headers
  workflowRunId: "my-workflow", // optional workflow run id
  retries: 3,                   // optional retries in the initial request
  delay: "10s",                 // optional delay value
  failureUrl: "https://<YOUR_FAILURE_URL>", // optional failure url
  useFailureFunction: true,     // whether a failure function is defined in the endpoint
  flowControl: { ... }          // optional flow control
})
console.log(workflowRunId)
// prints wfr_my-workflow

```

--------------------------------

TITLE: Upstash Workflow Example: Parallel Inventory Check and Coffee Brewing (TypeScript)
DESCRIPTION: This complete workflow example, written in TypeScript for Next.js, shows how to run parallel checks for coffee beans, cups, and milk availability. If all ingredients are available, it proceeds to brew coffee and print a receipt. It utilizes `Promise.all` for parallel inventory checks and `ctx.run` for executing individual workflow steps.

SOURCE: https://upstash.com/docs/workflow/howto/parallel-runs

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { checkInventory, brewCoffee, printReceipt } from "@/utils";

export const { POST } = serve(async (ctx) => {
  const [coffeeBeansAvailable, cupsAvailable, milkAvailable] = await Promise.all([
    ctx.run("check-coffee-beans", () => checkInventory("coffee-beans")),
    ctx.run("check-cups", () => checkInventory("cups")),
    ctx.run("check-milk", () => checkInventory("milk")),
  ]);

  // If all ingedients available, brew coffee
  if (coffeeBeansAvailable && cupsAvailable && milkAvailable) {
    const price = await ctx.run("brew-coffee", async () => {
      return await brewCoffee({ style: "cappuccino" });
    });
    await printReceipt(price);
  }
});

```

--------------------------------

TITLE: TypeScript Workflow Example (Next.js)
DESCRIPTION: Example of a Next.js API route using the Upstash Workflow SDK to define and execute workflow steps. It includes running tasks like 'create-backup' and 'upload-backup' and a failure function for error handling.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { createBackup, uploadBackup } from "./utils";
export const { POST } = serve(
  async (ctx) => {
    const backup = await ctx.run("create-backup", async () => {
      return await createBackup();
    });
    await ctx.run("upload-backup", async () => {
      await uploadBackup(backup);
    });
  },
  {
    failureFunction({ context, failStatus, failResponse, failHeader }) {
      // immediately get notified for failed backups
      // i.e. send an email, log to Sentry
    },
  }
);

```

--------------------------------

TITLE: Initial Waiting Period Step (TypeScript)
DESCRIPTION: This code demonstrates how to pause the Upstash Workflow for a specified duration, in this case, 3 days, using `context.sleep`. This allows time for user interaction before proceeding with further steps.

SOURCE: https://upstash.com/docs/workflow/examples/customerOnboarding

LANGUAGE: TypeScript
CODE:
```
await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)
```

--------------------------------

TITLE: Set Up Python Virtual Environment
DESCRIPTION: Demonstrates creating and activating a Python virtual environment using the `venv` module. This is a best practice for managing project dependencies and avoiding conflicts in Python projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Install Upstash Workflow SDK with bun
DESCRIPTION: Installs the Upstash Workflow SDK into your Hono project using the bun package manager. This command ensures the SDK is correctly added to your project's dependencies.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Install Python Packages for Upstash Workflow and Flask
DESCRIPTION: Installs essential Python packages for Flask applications integrating with Upstash Workflow, including 'fastapi', 'uvicorn', and 'upstash-workflow'.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pip install fastapi uvicorn upstash-workflow
```

--------------------------------

TITLE: Install Upstash Workflow SDK (pnpm)
DESCRIPTION: This command installs the Upstash Workflow SDK into your project using the pnpm package manager. It's an alternative to npm for integrating Upstash Workflow functionality.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow

```

--------------------------------

TITLE: Install Upstash Workflow JS SDK
DESCRIPTION: Installs the Upstash Workflow JS package using npm. This is a fundamental step for integrating Upstash Workflow into your JavaScript projects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

--------------------------------

TITLE: Create New User in Stripe
DESCRIPTION: This snippet handles the integration with Stripe by creating a new user account. It's a crucial step in setting up payment and subscription management for new users.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
await context.run("create new user in stripe", async () => {
  await createNewUserInStripe(email);
});
```

--------------------------------

TITLE: Start Flask Application with Upstash Workflow
DESCRIPTION: Starts a Flask application using the Flask development server, making it accessible on port 8000. The `--app main` flag specifies the main application file.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Bash
CODE:
```
flask --app main run -p 8000
```

--------------------------------

TITLE: Start Astro Development Server
DESCRIPTION: This command starts the Astro development server, making the defined workflow endpoint accessible locally. It's a prerequisite for triggering and testing the workflow during local development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Install Upstash Workflow SDK in Astro
DESCRIPTION: Provides commands to install the Upstash Workflow SDK in an Astro project using different package managers: npm, pnpm, and bun. This is a foundational step for integrating Upstash Workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Configure Environment Variables
DESCRIPTION: Copies the example environment file to a new file named .env. This file is used to store sensitive information and configuration settings for the application.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
cp .env.example .env
```

--------------------------------

TITLE: Production Deployment to Vercel
DESCRIPTION: This command deploys the project to production on Vercel. It's crucial for ensuring the application functions correctly, as preview deployments require authentication.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
vercel --prod
```

--------------------------------

TITLE: Example Workflow API Request (Bash)
DESCRIPTION: Demonstrates how to send a POST request to an Upstash Workflow API endpoint using `curl`. The example includes a JSON payload with an ID and a question, illustrating a typical interaction with a workflow API.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
curl -XPOST https://qstash-workflow.vercel.app/api/example -d '{"id": "id_123", "question": "what is the meaning of life?"}'
```

--------------------------------

TITLE: Install Upstash Workflow Dependencies (npm)
DESCRIPTION: Installs necessary npm packages for Upstash Workflow, AI capabilities, and Zod for schema validation, essential for building workflow and agent functionalities.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i @upstash/workflow ai zod
```

--------------------------------

TITLE: Deploy Project to Production on Vercel
DESCRIPTION: Command to deploy the project to production on Vercel. This is necessary for the project to function correctly, as preview deployments require authentication.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Bash
CODE:
```
vercel --prod
```

--------------------------------

TITLE: Configure .env.local for Local QStash Server
DESCRIPTION: Example content for the `.env.local` file when using a local QStash server. It sets `QSTASH_URL` to the local server address and `QSTASH_TOKEN` to the token provided by the CLI.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Example Agent Output Logs
DESCRIPTION: Illustrates the expected console output from a running workflow agent, showing internal thought process and the final response.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: text
CODE:
```
Inner thought: I will discuss the future of space
exploration and the potential advancements in
technology and missions.
Final response: The future of space exploration
holds exciting possibilities with advancements
in technology, potential manned missions to
Mars, increased commercial space travel,
and exploration of distant celestial
bodies.
```

--------------------------------

TITLE: Install Upstash Workflow SDK for Node.js
DESCRIPTION: Installs the Upstash Workflow SDK into your Express.js project using different Node.js package managers. This SDK is required to define and manage workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Run Astro Development Server
DESCRIPTION: Starts the Astro development server to make the workflow endpoint accessible for testing.

SOURCE: https://upstash.com/docs/workflow/quickstarts/astro

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Run Project Tests with Bun (Bash)
DESCRIPTION: Steps to run tests for the project using Bun, which involves setting up environment variables via a `.env` file.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
bun run test
```

--------------------------------

TITLE: Create .env.local file
DESCRIPTION: Creates a `.env.local` file in your project's root directory to store environment variables, such as your QStash token, for local development.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: bash
CODE:
```
touch .env.local

```

--------------------------------

TITLE: Initialize Next.js Project
DESCRIPTION: Initializes a new Next.js project with specified name and options using npx create-next-app.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx create-next-app@latest [project-name] [options]
```

--------------------------------

TITLE: Start ngrok Tunnel for Local Access
DESCRIPTION: Starts an ngrok tunnel to make a local server running on a specified port publicly accessible. The output provides a public URL that can be used for external services to connect to the local development environment.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http <PORT>
```

LANGUAGE: bash
CODE:
```
ngrok http 3000
```

--------------------------------

TITLE: Start ngrok HTTP Tunnel for Port 3000
DESCRIPTION: Starts an ngrok HTTP tunnel for a local server running on port 3000, commonly used for Next.js applications. This exposes the local development server to the public internet for testing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http 3000
```

--------------------------------

TITLE: Python Virtual Environment Setup
DESCRIPTION: Commands to create and activate a Python virtual environment named 'venv'. This is essential for managing project dependencies in isolation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Run FastAPI Server
DESCRIPTION: This command starts the FastAPI application using `uvicorn`, enabling hot-reloading for development. The server will be accessible at `localhost:8000`.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-py

LANGUAGE: Shell
CODE:
```
uvicorn main:app --reload
```

--------------------------------

TITLE: Run Flask Application
DESCRIPTION: Starts the Flask development server on port 8000. Assumes the Flask application is defined in `main.py` and environment variables are sourced.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
flask --app main run -p 8000
```

--------------------------------

TITLE: Install Upstash Workflow SDK in Nuxt.js
DESCRIPTION: Instructions for installing the Upstash Workflow SDK using different package managers (npm, pnpm, bun) in a Nuxt.js project. This SDK is a prerequisite for defining and running workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
pnpm install @upstash/workflow
```

LANGUAGE: bash
CODE:
```
bun add @upstash/workflow
```

--------------------------------

TITLE: Configure Local QStash Server
DESCRIPTION: Sets up the `.dev.vars` file to include the local QStash URL and token for testing Upstash Workflows locally without incurring production costs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Run Next.js Development Server
DESCRIPTION: Starts the Next.js development server, making defined API endpoints accessible. This is a prerequisite for calling workflow endpoints.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Set Up Python Virtual Environment for FastAPI
DESCRIPTION: This snippet demonstrates how to create and activate a Python virtual environment, which is a best practice for managing project dependencies and avoiding conflicts with system-wide packages.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Configure Local QStash Environment Variables
DESCRIPTION: Sets the QSTASH_URL and QSTASH_TOKEN in the .env file for local development using a local QStash server.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Start ngrok HTTP Tunnel for Port 3000
DESCRIPTION: Starts an ngrok HTTP tunnel for a local server running on port 3000, commonly used for Next.js applications. It demonstrates how to expose a local development server to the public internet for testing and integration with services like Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http 3000
```

--------------------------------

TITLE: Start ngrok HTTP Tunnel (Bash)
DESCRIPTION: Initiates an ngrok HTTP tunnel to make a local server publicly accessible. The `<PORT>` parameter specifies the local application port.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http <PORT>
```

--------------------------------

TITLE: Run Upstash QStash CLI in Development Mode
DESCRIPTION: Starts a local QStash server for development, providing local QSTASH_URL and QSTASH_TOKEN for testing workflows without affecting billing. This command requires the @upstash/qstash-cli package.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npx @upstash/qstash-cli dev
```

--------------------------------

TITLE: Configure .env.local for Local Tunnel
DESCRIPTION: Example content for the `.env.local` file when using a local tunnel. It requires the actual `QSTASH_TOKEN` from the Upstash Console and the public URL provided by the local tunnel.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Example Notify Response Structure (JSON)
DESCRIPTION: A JSON example of a successful response from the notify endpoint. It contains an array with an object that includes a `waiter` object detailing the resumed workflow and a `messageId` for the sent message.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
[
  {
    "waiter": {
      "url": "https://my-workflow.com/path",
      "headers": {
        "Upstash-Workflow-Runid": [
          "wfr_melCHYvPkVhDqIhhk2"
        ],
        "Upstash-Workflow-Url": [
          "https://my-workflow.com/path"
        ]
      },
      "deadline": 1729869206
    },
    "messageId": "msg_26hZCxxbG2TT3AnHEr1w"
  }
]
```

--------------------------------

TITLE: Start Flask Application for Workflow Endpoints
DESCRIPTION: Starts the Flask application on port 8000, using `main.py` as the application file. This command is used to run workflow endpoints defined within a Flask application.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
flask --app main run -p 8000
```

--------------------------------

TITLE: Create Python Virtual Environment
DESCRIPTION: Creates a Python virtual environment named 'venv' and activates it. This isolates project dependencies.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Setup FastAPI Workflow with Upstash Workflow in Python
DESCRIPTION: Initializes a FastAPI application and integrates Upstash Workflow for defining and running workflows. It imports necessary modules for FastAPI and Upstash Workflow, setting up the application for workflow management.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
from fastapi import FastAPI
from typing import Dict, TypedDict
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext, CallResponse
from email_utils import send_email

app = FastAPI()
serve = Serve(app)
```

--------------------------------

TITLE: Payment Retries Workflow Example
DESCRIPTION: This example demonstrates a payment retry process using Upstash Workflow. It handles retrying a payment, sending emails, and suspending accounts based on payment success or failure after multiple attempts.

SOURCE: https://upstash.com/docs/workflow/llms-txt



--------------------------------

TITLE: Notify Workflows with Go HTTP Client
DESCRIPTION: This Go example demonstrates how to construct and send a POST request using the standard `net/http` package. It creates a new request, sets the `Authorization` header, and executes the request using the default HTTP client.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("POST", "https://qstash.upstash.io/v2/notify/myEvent", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
def resp.Body.Close()

```

--------------------------------

TITLE: Upstash Workflow Next.js Example
DESCRIPTION: This snippet shows a Next.js endpoint for Upstash Workflow, demonstrating a customer onboarding process. It includes sending welcome emails, sleeping for a duration, using OpenAI for personalized messages, and sending follow-up emails. The `context.api.openai.call` bypasses function timeouts and execution time limits.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";
// Type-safety for starting our workflow
interface InitialData {
  userId: string
  email: string
  name: string
}
export const { POST } = serve<InitialData>(async (context) => {
  const { userId, email, name } = context.requestPayload;
  // Step 1: Send welcome email
  await context.run("send-welcome-email", async () => {
    await sendEmail(email, "Welcome to our service!");
  });
  // Step 2: Wait for 3 days (in seconds)
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);
  // Step 3: AI-generate personalized follow-up message
  const { body: aiResponse } = await context.api.openai.call(
    "generate-personalized-message",
    {
      token: "<OPENAI_API_KEY>",
      operation: "chat.completions.create",
      body: {
        model: "gpt-3.5-turbo",
        messages: [
          { role: "system", content: "You are an assistant creating personalized follow-up messages." },
          { role: "user", content: `Create a short, friendly follow-up message for ${name} who joined our service 3 days ago.` }
        ]
      },
    }
  );
  // Step 4: Send follow-up email with AI message
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, aiResponse.choices[0].message.content);
  });
});

```

--------------------------------

TITLE: Get QStash Flow Control Info
DESCRIPTION: Performs a GET request to the Upstash QStash API to retrieve flow control key details, requiring a bearer token and the `flowControlKey`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: sh
CODE:
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Apply Filters to Images
DESCRIPTION: Applies multiple filters (grayscale, sepia, contrast) to a list of resized images. It uses `context.call` to invoke external services for each filter and image pair, collecting promises and running them in parallel using `Promise.all`.

SOURCE: https://upstash.com/docs/workflow/examples/imageProcessing

LANGUAGE: TypeScript
CODE:
```
const filters = ["grayscale", "sepia", "contrast"]
const processedImagePromises: Promise<string>[] = []
for (const resizedImage of resizedImages) {
  for (const filter of filters) {
    const processedImagePromise = context.call<ImageResult>(
      `apply-filter-${filter}`,
      {
        // endpoint which returns ImageResult type in response
        url: "https://image-processing-service.com/filter",
        method: "POST",
        body: {
          imageUrl: resizedImage.body.imageUrl,
          filter,
        }
      }
    )
    processedImagePromises.push(processedImagePromise)
  }
}
const processedImages: { body: ImageResult }[] = await Promise.all(processedImagePromises)
```

--------------------------------

TITLE: Create and Activate Virtual Environment
DESCRIPTION: Creates a Python virtual environment named 'venv' and activates it. This isolates project dependencies.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Fetch Workflow Logs with Go net/http (Go)
DESCRIPTION: Demonstrates fetching workflow logs using Go's `net/http` package. Includes building a GET request, setting authorization headers, and basic error handling.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/workflows/logs", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
def resp.Body.Close()
```

--------------------------------

TITLE: Run Project Tests with Bun
DESCRIPTION: Details the process for running project tests. It involves setting up environment variables by creating a `.env` file from the provided `.env.template` and then executing the test command using Bun.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: bash
CODE:
```
bun run test

```

--------------------------------

TITLE: Customer Onboarding Workflow with Email and Delays
DESCRIPTION: Defines a customer onboarding workflow. It includes user registration, welcome email, a 3-day sleep, and an infinite loop for activity checks with follow-up emails. Uses `context.run` for atomicity and `context.sleep` for delays.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"

type InitialData = {
  email: string
}

export const { POST } = serve<InitialData>(async (context) => {
  const { email } = context.requestPayload

  await context.run("new-signup", async () => {
    await sendEmail("Welcome to the platform", email)
  })

  await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)


```

--------------------------------

TITLE: Install Upstash Workflow Dependencies (npm)
DESCRIPTION: Installs essential npm packages for Upstash Workflow, including AI capabilities and Zod for schema validation. These packages are critical for developing and running workflow and agent functionalities.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm i @upstash/workflow ai zod
```

--------------------------------

TITLE: Upstash Workflow Image Processing Example (TypeScript)
DESCRIPTION: This TypeScript code defines an Upstash Workflow for image processing. It retrieves an image URL, resizes the image to multiple resolutions using an external service, applies various filters, and stores the processed images. The workflow is designed to be executed sequentially due to current limitations.

SOURCE: https://upstash.com/docs/workflow/examples/imageProcessing

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
import {
  resizeImage,
  applyFilters,
  storeImage,
  getImageUrl,
} from "./utils"
type ImageResult = {
  imageUrl: string
}
export const { POST } = serve<{ imageId: string; userId: string }>(
  async (context) => {
    const { imageId, userId } = context.requestPayload
    // Step 1: Retrieve the uploaded image
    const imageUrl = await context.run("get-image-url", async () => {
      return await getImageUrl(imageId)
    })
    // Step 2: Resize the image to multiple resolutions
    const resolutions = [640, 1280, 1920]
    const resizedImages: { body: ImageResult }[] = await Promise.all(resolutions.map(
      resolution => context.call<ImageResult>(
        `resize-image-${resolution}`,
        {
          // endpoint which returns ImageResult type in response
          url: "https://image-processing-service.com/resize",
          method: "POST",
          body: {
            imageUrl,
            width: resolution,
          }
        }
      )
    ))
    // Step 3: Apply filters to each resized image
    const filters = ["grayscale", "sepia", "contrast"]
    const processedImagePromises: Promise<string>[] = []
    for (const resizedImage of resizedImages) {
      for (const filter of filters) {
        const processedImagePromise = context.call<ImageResult>(
          `apply-filter-${filter}`,
          {
            // endpoint which returns ImageResult type in response
            url: "https://image-processing-service.com/filter",
            method: "POST",
            body: {
              imageUrl: resizedImage.body.imageUrl,
              filter,
            }
          }
        )
        processedImagePromises.push(processedImagePromise)
      }
    }
    const processedImages: { body: ImageResult }[] = await Promise.all(processedImagePromises)
    // Step 4: Store processed images in cloud storage
    const storedImageUrls: string[] = await Promise.all(
      processedImages.map(
        processedImage => context.run(`store-image`, async () => {
          return await storeImage(processedImage.body.imageUrl)
        })
      )
    )
  }
)

```

--------------------------------

TITLE: Upstash Redis: Create Serverless Redis Database
DESCRIPTION: Create a Redis database in seconds with Upstash's serverless offering. This service simplifies the setup and management of Redis instances, allowing for rapid deployment and scaling.

SOURCE: https://upstash.com/docs/introduction

LANGUAGE: text
CODE:
```
Serverless Redis
Create a Redis Database within seconds
```

--------------------------------

TITLE: Create .env.local file
DESCRIPTION: Creates a .env.local file in the project root to store environment variables, such as the QStash token.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: bash
CODE:
```
touch .env.local

```

--------------------------------

TITLE: Define and Execute Workflow Step (TypeScript)
DESCRIPTION: Shows how to define and execute a workflow step using `context.run`. This example illustrates serial execution of two steps, where the output of the first step is used as input for the second.

SOURCE: https://upstash.com/docs/workflow/basics/context

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload;
  const result1 = await context.run("step-1", async () => {
    return someWork(input);
  });
  await context.run("step-2", async () => {
    someOtherWork(result1);
  });
});

```

--------------------------------

TITLE: Run Express.js Workflow Endpoint
DESCRIPTION: Starts the Express.js development server. Once running, the application is ready to receive POST requests at its configured workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Customer Onboarding Workflow in Python with Upstash
DESCRIPTION: Demonstrates a customer onboarding workflow in Python using Upstash Workflow. It includes functions to get user state, send emails, and manage workflow steps like checking user status and sending targeted emails based on the state. It also includes a sleep function for delays.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
from fastapi import FastAPI
from typing import Literal, TypedDict
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext

app = FastAPI()
serve = Serve(app)

UserState = Literal["non-active", "active"]


class InitialData(TypedDict):
    email: str


async def send_email(message: str, email: str) -> None:
    # Implement email sending logic here
    print(f"Sending {message} email to {email}")


async def get_user_state() -> UserState:
    # Implement user state logic here
    return "non-active"


@serve.post("/customer-onboarding")
async def customer_onboarding(context: AsyncWorkflowContext[InitialData]) -> None:
    email = context.request_payload["email"]

    async def _new_signup() -> None:
        await send_email("Welcome to the platform", email)

    await context.run("new-signup", _new_signup)

    await context.sleep("wait-for-3-days", 60 * 60 * 24 * 3)

    while True:

        async def _check_user_state() -> UserState:
            return await get_user_state()

        state: UserState = await context.run("check-user-state", _check_user_state)

        if state == "non-active":

            async def _send_email_non_active() -> None:
                await send_email("Email to non-active users", email)

            await context.run("send-email-non-active", _send_email_non_active)
        else:

            async def _send_email_active() -> None:
                await send_email("Send newsletter to active users", email)

            await context.run("send-email-active", _send_email_active)

        await context.sleep("wait-for-1-month", 60 * 60 * 24 * 30)

```

--------------------------------

TITLE: Create .env File
DESCRIPTION: Creates an empty .env file in the project root. This file will store environment-specific variables like API keys and URLs.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Bash
CODE:
```
touch .env
```

--------------------------------

TITLE: Configure Local QStash Environment Variables
DESCRIPTION: Sets environment variables for the local QStash server. These variables are used for authentication and connection.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
export QSTASH_URL="http://127.0.0.1:8080"
export QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: TypeScript Customer Onboarding Workflow with Upstash
DESCRIPTION: Implements a customer onboarding workflow in TypeScript using Upstash Workflow. It sends a welcome email, pauses for three days, generates a personalized message using OpenAI's API, and sends a follow-up email. It utilizes `context.run` for retries and `context.api.openai.call` for external API integration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";

// Type-safety for starting our workflow
interface InitialData {
  userId: string
  email: string
  name: string
}

export const { POST } = serve<InitialData>(async (context) => {
  const { userId, email, name } = context.requestPayload;

  // Step 1: Send welcome email
  await context.run("send-welcome-email", async () => {
    await sendEmail(email, "Welcome to our service!");
  });

  // Step 2: Wait for 3 days (in seconds)
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);

  // Step 3: AI-generate personalized follow-up message
  const { body: aiResponse } = await context.api.openai.call(
    "generate-personalized-message",
    {
      token: "<OPENAI_API_KEY>",
      operation: "chat.completions.create",
      body: {
        model: "gpt-3.5-turbo",
        messages: [
          { role: "system", content: "You are an assistant creating personalized follow-up messages." },
          { role: "user", content: `Create a short, friendly follow-up message for ${name} who joined our service 3 days ago.` }
        ]
      }
    }
  );

  const personalizedMessage = aiResponse.choices[0].message.content;

  // Step 4: Send personalized follow-up email
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, personalizedMessage);
  });
});

```

--------------------------------

TITLE: List Message Logs with curl
DESCRIPTION: An example using curl to request the message logs for workflow runs from the Upstash QStash API.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl https://qstash.upstash.io/v2/workflows/messageLogs \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Python Virtual Environment Setup
DESCRIPTION: Creates and activates a Python virtual environment named 'venv' for managing project dependencies. This is a standard practice for isolating project environments.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Run Next.js Development Server
DESCRIPTION: Starts the Next.js application in development mode, making the defined API endpoints accessible. This is a prerequisite for calling the workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Configure Local QStash Environment Variables
DESCRIPTION: Adds QSTASH_URL and QSTASH_TOKEN to the .env.local file when using a local QStash server. This is a common setup step for local development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: dotenv
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Sending a Report (Python)
DESCRIPTION: This snippet demonstrates the Python equivalent of sending a report. It uses `context.run` to execute the `generateReport` and `sendReport` functions, similar to the TypeScript example.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
# Python equivalent would involve similar context.run calls if a Python SDK is used for workflow execution.
# Example placeholder:
# report = context.run("generate-report", lambda: generate_report(request.dataset_id))

```

--------------------------------

TITLE: Configure Local QStash Environment Variables
DESCRIPTION: Sets the QSTASH_URL and QSTASH_TOKEN environment variables in the .env file for local QStash server usage.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Shell
CODE:
```
export QSTASH_URL="http://127.0.0.1:8080"
export QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Send Welcome Email with Upstash Workflow
DESCRIPTION: This snippet illustrates sending a welcome email to a user upon their registration or trial start. It defines an asynchronous function `_send_welcome_email` that utilizes a `send_email` function with the user's email and a welcome message, then runs this within the workflow context.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _send_welcome_email() -> None:
    await send_email(
        email,
        "Welcome to our platform!, You have 14 days of free trial."
    )

await context.run("send welcome email", _send_welcome_email)
```

--------------------------------

TITLE: Waiting for Events Workflow Example (Python)
DESCRIPTION: An example workflow that waits for an external event to confirm order processing. It includes steps for requesting processing, handling timeouts, and confirming the order. Note: This specific feature is not yet available in workflow-py.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
# This feature is not yet available in [workflow-py](https://github.com/upstash/workflow-py).
# See our [Roadmap](https://upstash.com/docs/workflow/roadmap) for feature parity plans and [Changelog](https://upstash.com/docs/workflow/changelog) for updates.

# Workflow Steps:
# 1. Receive an order request.
# 2. Send an email to request order processing.
# 3. Wait for an external event that indicates the order has been processed.
# 4. Handle timeout scenarios if the event is not received in time.
```

--------------------------------

TITLE: FastAPI Workflow Endpoint
DESCRIPTION: Define a workflow endpoint in a FastAPI application. This example demonstrates how to create a workflow with two sequential steps using the `upstash_workflow.fastapi.Serve` class.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from fastapi import FastAPI
from upstash_workflow.fastapi import Serve

app = FastAPI()
serve = Serve(app)

@serve.post("/api/workflow")
async def workflow(context):
    async def _step1() -> None:
        print("initial step ran")
    await context.run("initial-step", _step1)

    async def _step2() -> None:
        print("second step ran")
    await context.run("second-step", _step2)
```

--------------------------------

TITLE: Next.js Workflow: Customer Onboarding
DESCRIPTION: This Next.js code snippet demonstrates a customer onboarding workflow using Upstash Workflow. It defines an initial data interface and uses the `serve` function to manage workflow steps: sending a welcome email, sleeping for three days, generating a personalized follow-up message using OpenAI, and sending the follow-up email. It highlights that external API calls via `context.api` do not count towards function execution time.

SOURCE: https://upstash.com/docs/workflow/getstarted

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { sendEmail } from "./emailUtils";
// Type-safety for starting our workflow
interface InitialData {
  userId: string
  email: string
  name: string
}
export const { POST } = serve<InitialData>(async (context) => {
  const { userId, email, name } = context.requestPayload;
  // Step 1: Send welcome email
  await context.run("send-welcome-email", async () => {
    await sendEmail(email, "Welcome to our service!");
  });
  // Step 2: Wait for 3 days (in seconds)
  await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3);
  // Step 3: AI-generate personalized follow-up message
  const { body: aiResponse } = await context.api.openai.call(
    "generate-personalized-message",
    {
      token: "<OPENAI_API_KEY>",
      operation: "chat.completions.create",
      body: {
        model: "gpt-3.5-turbo",
        messages: [
          { role: "system", content: "You are an assistant creating personalized follow-up messages." },
          { role: "user", content: `Create a short, friendly follow-up message for ${name} who joined our service 3 days ago.` }
        ]
      },
    }
  );
  const personalizedMessage = aiResponse.choices[0].message.content;
  // Step 4: Send personalized follow-up email
  await context.run("send-follow-up-email", async () => {
    await sendEmail(email, personalizedMessage);
  });
});

```

--------------------------------

TITLE: Create and Activate Python Virtual Environment (Bash)
DESCRIPTION: Commands to create a Python virtual environment named 'venv' and activate it. This isolates project dependencies for a clean development setup.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Periodic State Check Loop (TypeScript)
DESCRIPTION: This snippet implements an infinite loop for periodically checking a user's activity state (e.g., 'non-active' or 'active') every month. Based on the state, it sends different emails and then pauses for another month.

SOURCE: https://upstash.com/docs/workflow/examples/customerOnboarding

LANGUAGE: TypeScript
CODE:
```
while (true) {
  const state = await context.run("check-user-state", async () => {
    return await getUserState()
  })
  if (state === "non-active") {
    await context.run("send-email-non-active", async () => {
      await sendEmail("Email to non-active users", email)
    })
  } else if (state === "active") {
    await context.run("send-email-active", async () => {
      await sendEmail("Send newsletter to active users", email)
    })
  }
  await context.sleep("wait-for-1-month", 60 * 60 * 24 * 30)
}
```

--------------------------------

TITLE: Upstash Workflow JS API Reference
DESCRIPTION: Comprehensive API documentation for Upstash Workflow JS, detailing available methods, parameters, and usage examples for managing workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: APIDOC
CODE:
```
Workflow:
  __init__(workflow_id: str, api_key: str)
    workflow_id: The unique identifier for the workflow.
    api_key: The API key for authentication.

  create_step(step_data: dict)
    step_data: A dictionary containing the data for the new step.
    Returns: The created step object.

  get_step(step_id: str)
    step_id: The ID of the step to retrieve.
    Returns: The step object.

  update_step(step_id: str, step_data: dict)
    step_id: The ID of the step to update.
    step_data: A dictionary containing the updated step data.
    Returns: The updated step object.

  delete_step(step_id: str)
    step_id: The ID of the step to delete.
    Returns: A success message.

  list_steps(workflow_id: str)
    workflow_id: The ID of the workflow to list steps for.
    Returns: A list of step objects.

  execute_workflow(workflow_id: str, input_data: dict)
    workflow_id: The ID of the workflow to execute.
    input_data: The input data for the workflow execution.
    Returns: The result of the workflow execution.
```

--------------------------------

TITLE: Curl Request to List DLQ
DESCRIPTION: Example cURL command to list failed workflow runs from the DLQ, including the necessary authorization header.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl https://qstash.upstash.io/v2/workflows/dlq \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Next.js and FastAPI Integration with Upstash Workflow (Python)
DESCRIPTION: This example demonstrates using Upstash Workflow for Python with a Next.js frontend and a FastAPI backend. It shows how to orchestrate tasks across these technologies using Upstash Workflow.

SOURCE: https://upstash.com/docs/workflow/getstarted

LANGUAGE: Python
CODE:
```
from upstash_workflow import Workflow, Step

# Example workflow definition in Python
async def process_data(data):
    print(f"Processing: {data}")
    # Simulate some processing
    await asyncio.sleep(1)
    return {"result": f"processed_{data}"}

my_python_workflow = Workflow(
    name="my-python-fastapi-workflow",
    steps=[
        Step(id="process", handler=process_data)
    ]
)

# To run the workflow (example):
# await my_python_workflow.run(data="sample input")
```

--------------------------------

TITLE: Image Processing Workflow (Python)
DESCRIPTION: This Python example demonstrates a sequential image processing workflow. It covers uploading an image, resizing it to multiple resolutions, applying filters, and storing the processed images. Note that parallel steps are not yet available in workflow-py.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
# This is a placeholder for the actual Python code.
# The provided text describes the functionality but does not include the code itself.
# Example structure:
# def process_image_workflow(image_data):
#     # 1. Retrieve the image
#     retrieved_image = retrieve_image(image_data)
# 
#     # 2. Resize the image
#     resized_images = resize_image(retrieved_image)
# 
#     # 3. Apply filters
#     filtered_images = apply_filters(resized_images)
# 
#     # 4. Store processed images
#     stored_paths = store_images(filtered_images)
# 

```

--------------------------------

TITLE: Create Upstash Workflow Endpoint (Next.js)
DESCRIPTION: Defines an endpoint to serve a workflow using the `serve` method from `@upstash/workflow/nextjs`. It provides a context object to define workflow steps, with examples of running sequential steps.

SOURCE: https://upstash.com/docs/workflow/basics/serve

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
export const { POST } = serve(async (context) => {
  const result = await context.run("step-1", async () => {
    // define a piece of business logic as step 1
  });
  await context.run("step-2", async () => {
    // define another piece of business logic as step 2
  });
});

```

--------------------------------

TITLE: Configure Local Tunnel
DESCRIPTION: Configures environment variables for local development using a local tunnel, including the QStash token and the workflow URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: dotenv
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>

```

--------------------------------

TITLE: Configure Local QStash Environment
DESCRIPTION: Sets the QSTASH_URL and QSTASH_TOKEN environment variables for local development using the QStash CLI. These are essential for authenticating with the QStash service.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: dotenv
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Create .env File
DESCRIPTION: Creates an empty .env file in the project root. This file will store environment-specific variables, such as API keys and URLs.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
touch .env
```

--------------------------------

TITLE: Run Hono Development Server (Bash)
DESCRIPTION: A command to start the Hono application locally using npm. This command is essential for making the workflow endpoint accessible at a local URL during development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Implement Prompt Chaining with Upstash Workflow
DESCRIPTION: This code snippet demonstrates how to implement prompt chaining using Upstash Workflow. It sets up three agents: the first lists famous physicists, the second uses a Wikipedia tool to describe their work, and the third summarizes the descriptions. The output of each agent is passed as input to the next in the chain.

SOURCE: https://upstash.com/docs/workflow/agents/patterns/prompt-chaining

LANGUAGE: javascript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { WikipediaQueryRun } from "@langchain/community/tools/wikipedia_query_run";
export const { POST } = serve(async (context) => {
  const model = context.agents.openai('gpt-3.5-turbo');
  const agent1 = context.agents.agent({
    model,
    name: 'firstAgent',
    maxSteps: 1,
    background: 'You are an agent that lists famous physicists.',
    tools: {}
  });
  const agent2 = context.agents.agent({
    model,
    name: 'secondAgent',
    // set to 2 as this agent will first request tools
    // and then summarize them:
    maxSteps: 2,
    background:
      'You are an agent that describes the work of'
      + ' the physicists listed in the previous prompt.',
    tools: {
      wikiTool: new WikipediaQueryRun({
        topKResults: 1,
        maxDocContentLength: 500,
      })
    }
  });
  const agent3 = context.agents.agent({
    model,
    name: 'thirdAgent',
    maxSteps: 1,
    background:
      'You are an agent that summarizes the '
      + 'works of the physicists mentioned previously.',
    tools: {}
  });
  // Chaining agents
  const firstOutput = await context.agents.task({
    agent: agent1,
    prompt: "List 3 famous physicists."
  }).run();
  const secondOutput = await context.agents.task({
    agent: agent2,
    prompt: `Describe the work of: ${firstOutput.text}`
  }).run();
  const { text } = await context.agents.task({
    agent: agent3,
    prompt: `Summarize: ${secondOutput.text}`
  }).run();
  console.log(text);
});

```

--------------------------------

TITLE: Source Environment Variables
DESCRIPTION: Loads environment variables from the .env file into the current shell session. This makes variables like QSTASH_URL and QSTASH_TOKEN available to the application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
source .env
```

--------------------------------

TITLE: Set Up Basic Webhook Endpoint in FastAPI (Python)
DESCRIPTION: Demonstrates setting up a basic webhook endpoint using `Serve` from `upstash_workflow.fastapi`. It initializes an endpoint to receive and parse incoming webhook payloads.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from fastapi import FastAPI
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext

app = FastAPI()
serve = Serve(app)


def initial_payload_parser(payload):
    return payload


@serve.post("/api/example", initial_payload_parser=initial_payload_parser)
async def example(context: AsyncWorkflowContext[str]) -> None:
    # Your webhook handling logic here

```

--------------------------------

TITLE: Sync User with Database
DESCRIPTION: This code snippet focuses on the initial step of synchronizing user data. It calls a function to create a user in the database, returning a unique user ID.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
const { userid } = await context.run("sync user", async () => {
  return await createUserInDatabase({ name, email });
});
```

--------------------------------

TITLE: Create and Activate Python Virtual Environment (Bash)
DESCRIPTION: Creates a new Python virtual environment named 'venv' and activates it. This isolates project dependencies for a clean development setup.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Get Flow Control Info with cURL
DESCRIPTION: Retrieves flow control details from the Upstash QStash API using a cURL GET request. Requires authentication via a bearer token and the specific flow control key in the URL.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: sh
CODE:
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Example cURL Request for Bulk Cancel Workflows
DESCRIPTION: An example of how to use cURL to call the Bulk Cancel Workflows endpoint of the Upstash Workflow REST API. This includes setting the DELETE method, content type, authorization header, and the request body with a workflow URL.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -XDELETE https://qstash.upstash.io/v2/workflows/runs \
   -H "Content-Type: application/json" \
  -H "Authorization: Bearer <QSTASH_TOKEN>" \
  -d '{"workflowUrl": "https://example.com"}'
```

--------------------------------

TITLE: Source Environment File
DESCRIPTION: Loads environment variables defined in the '.env' file into the current shell session. This is necessary before running the Flask app or triggering workflows.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
source .env
```

--------------------------------

TITLE: Trigger Upstash Workflow via HTTP POST (JavaScript)
DESCRIPTION: Provides a JavaScript example using the Fetch API to trigger an Upstash workflow via an HTTP POST request. It includes examples for sending a JSON body and custom headers, but notes that this method is not suitable for secured endpoints.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: JavaScript
CODE:
```
await fetch("https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>", {
    method: "POST",
    body: JSON.stringify({ "foo": "bar" }),
    headers: {
      "my-header": "foo"
    }
  });

```

--------------------------------

TITLE: Initial context.requestPayload access in TypeScript
DESCRIPTION: Shows an example in TypeScript where accessing context.requestPayload directly before any steps might result in it being undefined, especially during context.call execution.

SOURCE: https://upstash.com/docs/workflow/troubleshooting/general

LANGUAGE: TypeScript
CODE:
```
export const { POST } = serve(async (context) => {
  // Will print undefined while executing context.call
  const payload = context.requestPayload
  console.log(payload)
  // ... steps or any other code
  context.call( ... )
})
```

--------------------------------

TITLE: Define Workflow Endpoint with Next.js (TypeScript)
DESCRIPTION: Demonstrates defining a workflow endpoint using the `serve` method in a Next.js application. Includes examples of running sequential steps and handling string payloads.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";

// mock function
const someWork = (input: string) => {

```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables
DESCRIPTION: Sets the QSTASH_TOKEN and UPSTASH_WORKFLOW_URL environment variables in the .env file for local tunnel usage.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-fastapi

LANGUAGE: Shell
CODE:
```
export QSTASH_TOKEN="***"
export UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Implement Workflow Step (Python)
DESCRIPTION: Demonstrates the correct way to implement a workflow step in Python using `context.run`. It includes a dummy step to ensure workflow authentication and successful execution.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    input = context.request_payload
    
    # 👇 At least one step is required
    async def _dummy_step():
        return
        
    await context.run("dummy-step", _dummy_step)
```

--------------------------------

TITLE: Run Express.js Application
DESCRIPTION: Starts the Express.js application, making the defined workflow endpoint accessible. This command assumes a `dev` script is configured in `package.json` to run the application.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Run Express.js Application
DESCRIPTION: Starts the Express.js application, making the defined workflow endpoint accessible. This command assumes a `dev` script is configured in `package.json` to run the application.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Define Multi-Step Onboarding Workflow (Python)
DESCRIPTION: Defines an asynchronous onboarding workflow using Upstash Workflow's AsyncWorkflowContext. It orchestrates steps like sending a welcome email, pausing, generating a personalized follow-up message via an AI API call, and sending the follow-up email. Demonstrates context.run, context.sleep, and context.call.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Python
CODE:
```
from typing import TypedDict, Dict
from upstash_workflow import AsyncWorkflowContext, serve, CallResponse


class InitialData(TypedDict):
    user_id: str
    email: str
    name: str


@serve.post("/api/onboarding")
async def onboarding_workflow(context: AsyncWorkflowContext[InitialData]) -> None:
    data = context.request_payload
    user_id = data["user_id"]
    email = data["email"]
    name = data["name"]

    # Step 1: Send welcome email
    async def _send_welcome_email() -> None:
        await send_email(email, "Welcome to our service!")

    await context.run("send-welcome-email", _send_welcome_email)

    # Step 2: Wait for 3 days (in seconds)
    await context.sleep("sleep-until-follow-up", 60 * 60 * 24 * 3)

    # Step 3: AI-generate personalized follow-up message
    ai_response: CallResponse[Dict[str, str]] = await context.call(
        "generate-personalized-message",
        url="https://api.openai.com/v1/chat/completions",
        method="POST",
        headers={...},
        body={
            "model": "gpt-3.5-turbo",
            "messages": [
                {
                    "role": "system",
                    "content": "You are an assistant creating personalized follow-up messages.",
                },
                {
                    "role": "user",
                    "content": f"Create a short, friendly follow-up message for {name} who joined our service 3 days ago.",
                }
            ]
        }
    )

    personalized_message = ai_response.body["choices"][0]["message"]["content"]

    # Step 4: Send personalized follow-up email
    async def _send_follow_up_email() -> None:
        await send_email(email, personalized_message)

    await context.run("send-follow-up-email", _send_follow_up_email)

```

--------------------------------

TITLE: Define Flask Workflow Endpoint
DESCRIPTION: Creates a Flask application and defines a workflow endpoint '/api/workflow'. This endpoint executes two sequential steps: '_step1' and '_step2'.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: python
CODE:
```
from flask import Flask
from upstash_workflow.flask import Serve

app = Flask(__name__)
serve = Serve(app)

@serve.route("/api/workflow")
def workflow(context) -> None:
    def _step1() -> None:
        print("initial step ran")
    context.run("initial-step", _step1)

    def _step2() -> None:
        print("second step ran")
    context.run("second-step", _step2)
```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables (.env)
DESCRIPTION: Sets environment variables for local tunnel setup, including QStash token and Upstash Workflow URL for logging.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
export QSTASH_TOKEN="***"
export UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Correct Workflow Step Definition (TypeScript)
DESCRIPTION: This TypeScript example demonstrates the correct way to define an Upstash workflow by ensuring at least one `context.run` call is included. This is necessary for the workflow's authentication and to prevent errors.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<string>(async (context) => {
  const input = context.requestPayload
  
  // 👇 At least one step is required
  await context.run("dummy-step", async () => {
    return
  })
})
```

--------------------------------

TITLE: Get Failed Workflow Run from DLQ (API)
DESCRIPTION: Retrieves a specific failed workflow run from the Dead Letter Queue (DLQ) using its DLQ ID. Requires an authorization token. The API endpoint is `GET /v2/workflows/dlq/{dlqId}`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: APIDOC
CODE:
```
GET /v2/workflows/dlq/{dlqId}

Description:
  Get a single failed workflow run from the Dead Letter Queue (DLQ).

Parameters:
  dlqId (string): The DLQ id of the failed workflow run you want to retrieve. This ID can be obtained from the [/v2/workflows/dlq](https://upstash.com/docs/workflow/rest/dlq/list) endpoint.

Request Example:
  curl -X GET https://qstash.upstash.io/v2/workflows/dlq/my-dlq-id \
    -H "Authorization: Bearer <token>"

Response Example (200 OK):
  {
    "messageId":"msg_26hZCxZCuWyyTWPmSVBrNC1RADwpgWxPcak2rQD51EMjFMuzcW7qYXpPiDyw8Gd",
    "url":"https://my.app/workflow",
    "method":"POST",
    "header":{
      "Content-Type":[
          "application/json"
      ]
    },
    "maxRetries":10,
    "notBefore":1752829294505,
    "createdAt":1752829294505,
    "failureCallback":"https://my.app/workflow",
    "callerIP":"88.240.188.2",
    "workflowRunId":"wfr_5XAx4IJergqkGK1v23VzR",
    "workflowCreatedAt":1752829293531,
    "workflowUrl":"https://my.app/workflow",
    "responseStatus":489,
    "responseHeader":{
      "Content-Type":[
          "text/plain;charset=UTF-8"
      ]
    },
    "responseBody":"{\"error\":\"WorkflowNonRetryableError\",\"message\":\"this workflow has stopped\"}",
    "failureCallbackInfo":{
      "state":"CALLBACK_SUCCESS",
      "responseStatus":200,
      "responseBody":"{\"workflowRunId\":\"wfr_Q_khHG-a414M-xKRh2kNI\"}",
      "responseHeaders":{
          "Content-Type":[
            "text/plain;charset=UTF-8"
          ]
      }
    },
    "dlqId":"1752829295505-0"
  }

```

--------------------------------

TITLE: Run Hono App Locally
DESCRIPTION: Starts the Hono application locally using the 'npm run dev' command. This command builds and serves the application, providing a local URL for the workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/quickstarts/hono

LANGUAGE: bash
CODE:
```
npm run dev
```

--------------------------------

TITLE: Set Environment Variables
DESCRIPTION: Configures environment variables in a .env.local file, including QStash URL and token, and OpenAI API key. These are typically obtained from local QStash server setup.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: env
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
OPENAI_API_KEY=<OPENAI_API_KEY>
```

--------------------------------

TITLE: Start ngrok HTTP Tunnel
DESCRIPTION: Initiates an ngrok HTTP tunnel to make a local server publicly accessible. The `<PORT>` parameter specifies the local port your application runs on, allowing ngrok to forward external requests.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
ngrok http <PORT>
```

--------------------------------

TITLE: Create Workflow Step (Python)
DESCRIPTION: Example of how to create a new step within a workflow using the Upstash Workflow Python SDK. It demonstrates defining an asynchronous step and running it within the workflow context.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    input = context.request_payload
    
    # 👇 At least one step is required
    async def _dummy_step():
        return
        
    await context.run("dummy-step", _dummy_step)
```

--------------------------------

TITLE: Configure Local Tunnel Environment
DESCRIPTION: Configures environment variables for local development using a local tunnel. It requires your QStash token and the public URL of your tunnelled application.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: dotenv
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Create Astro Workflow Endpoint
DESCRIPTION: Defines a workflow endpoint in an Astro project using the Upstash Workflow SDK. This example demonstrates a simple two-step workflow.

SOURCE: https://upstash.com/docs/workflow/quickstarts/astro

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/astro";

export const { POST } = serve<string>(async (context) => {
  const result1 = await context.run("initial-step", () => {
    console.log("initial step ran")
    return "hello world!"
  })
  await context.run("second-step", () => {
    console.log(`second step ran with value ${result1}`)
  })
}, {
  // env must be passed in astro.
  // for local dev, we need import.meta.env.
  // For deployment, we need process.env:
  env: {
    ...process.env,
    ...import.meta.env
  }
})

```

--------------------------------

TITLE: Create Hono Workflow Endpoint (TypeScript)
DESCRIPTION: Defines a workflow endpoint using Hono and the Upstash Workflow serve function. It includes two example steps that log messages to the console.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import {
  Hono
} from "hono"
import {
  serve
} from "@upstash/workflow/hono"
const app = new Hono()
app.post("/workflow",
  serve(async (context) => {
    await context.run("initial-step", () => {
      console.log("initial step ran")
    })
    await context.run("second-step", () => {
      console.log("second step ran")
    })
  })
)
export default app
```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables (.env.local)
DESCRIPTION: Sets up the necessary environment variables for a local tunnel setup with Upstash Workflow. Requires your QSTASH_TOKEN from the Upstash Console and the public URL from your local tunnel.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Generate and Send Report
DESCRIPTION: Generates a final report based on aggregated results and sends it to the user. Both report generation and sending are managed as distinct tasks using `context.run` for better control and potential error handling.

SOURCE: https://upstash.com/docs/workflow/examples/allInOne

LANGUAGE: typescript
CODE:
```
const report = await context.run("generate-report", async () => {
  return await generateReport(request.datasetId)
})
await context.run("send-report", async () => {
  await sendReport(report, request.userId)
})
```

--------------------------------

TITLE: Create Express.js Workflow Endpoint (TypeScript)
DESCRIPTION: Example of creating a workflow endpoint using Express.js and the @upstash/workflow library. This defines a '/workflow' POST route that executes a two-step workflow.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/express";
import express from 'express';
import { config } from 'dotenv';
config();
const app = express();
app.use(
  express.json()
);
app.post(
  '/workflow',
  serve<{ message: string }>(
    async (context) => {
      const res1 = await context.run("step1", async () => {
        const message = context.requestPayload.message;
        return message;
      })
      await context.run("step2", async () => {
          console.log(res1);
      })
    }
  )
);
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables (TXT)
DESCRIPTION: Sets environment variables for local tunnel setup, including the QStash token from Upstash Console and the public URL for production QStash integration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Define Minimal Workflow Endpoint (Next.js Pages Router - TypeScript)
DESCRIPTION: Sets up a minimal workflow endpoint for Next.js Pages Router using `servePagesRouter`. This example defines a basic workflow with two sequential steps.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { servePagesRouter } from "@upstash/workflow/nextjs";

const { handler } = servePagesRouter<string>(
  async (context) => {
    await context.run("initial-step", () => {
      console.log("initial step ran")
    })

    await context.run("second-step", () => {
      console.log("second step ran")
    })
  }
)
export default handler;
```

--------------------------------

TITLE: Upstash Serverless Concepts
DESCRIPTION: Explains Upstash's serverless architecture, which eliminates the need for infrastructure provisioning, allowing users to focus on creating and utilizing databases.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: markdown
CODE:
```

```

--------------------------------

TITLE: Upstash Workflow REST API Examples (APIDOC)
DESCRIPTION: Upstash Workflow provides a REST API for managing and interacting with workflows. This documentation outlines key endpoints for workflow execution and management.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: apidoc
CODE:
```
Workflow API:

POST /v1/workflows/{workflow_id}/execute
  Description: Executes a specified workflow.
  Headers:
    Authorization: Bearer <api_key>
    Content-Type: application/json
  Body:
    workflow_params: (object, optional) Parameters to pass to the workflow.
  Returns:
    200 OK: Workflow execution initiated successfully.
      {
        "execution_id": "<execution_id>"
      }
    400 Bad Request: Invalid request payload or parameters.
    401 Unauthorized: Invalid API key.
    404 Not Found: Workflow ID not found.

GET /v1/workflows/{workflow_id}/executions/{execution_id}
  Description: Retrieves the status and results of a specific workflow execution.
  Headers:
    Authorization: Bearer <api_key>
  Returns:
    200 OK: Execution details.
      {
        "execution_id": "<execution_id>",
        "workflow_id": "<workflow_id>",
        "status": "completed" | "running" | "failed",
        "result": (any, optional) The final result of the workflow if completed.
        "error": (string, optional) Error message if the execution failed.
      }
    401 Unauthorized: Invalid API key.
    404 Not Found: Workflow or execution ID not found.

GET /v1/workflows
```

--------------------------------

TITLE: Add ngrok Auth Token
DESCRIPTION: This command adds your ngrok authentication token to the ngrok configuration. This is a necessary step after signing up for ngrok and downloading the CLI to connect your account and enable tunneling.

SOURCE: https://upstash.com/docs/workflow/howto/local-development

LANGUAGE: bash
CODE:
```
ngrok config add-authtoken <YOUR-AUTH-TOKEN>

```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables
DESCRIPTION: Configures environment variables for using a local tunnel with Upstash Workflows. Requires your QStash token and the public URL from your local tunnel.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Configure Local Tunnel for Upstash Workflow
DESCRIPTION: Configures environment variables for using a local tunnel with Upstash Workflow. This involves setting the QSTASH_TOKEN and the UPSTASH_WORKFLOW_URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: dotenv
CODE:
```
QSTASH_TOKEN="***"
UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>

```

--------------------------------

TITLE: Python Workflow Endpoint Example
DESCRIPTION: Defines a Python API endpoint for an Upstash Workflow using `@serve.post`. It demonstrates running asynchronous steps within the workflow, logging, and accessing results from previous steps.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    input = context.request_payload

    async def _step_1() -> Dict:
        return {"success": True}

    result = await context.run("step-1", _step_1)

    print("This log will appear multiple times")

    async def _step_2() -> None:
        print("This log will appear just once")
        print("Step 1 status is:", result["success"])

    await context.run("step-2", _step_2)
```

--------------------------------

TITLE: Workflow Update Error Example (APIDOC)
DESCRIPTION: Illustrates the error message received when an in-progress workflow encounters an incompatible step name due to code changes.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: apidoc
CODE:
```
HTTP status 400. Incompatible step name. Expected <STEP_NAME>, got <STEP_NAME>
```

--------------------------------

TITLE: Create and Activate Python Virtual Environment
DESCRIPTION: Creates a Python virtual environment named 'venv' within the project directory and activates it. This isolates project dependencies, preventing conflicts with system-wide installations.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
python -m venv venv
source venv/bin/activate
```

--------------------------------

TITLE: Fetch Workflow Logs with Go
DESCRIPTION: Demonstrates fetching workflow logs using Go's standard `net/http` package. It constructs a GET request, sets the Authorization header, and executes the call with basic error handling for network operations.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/workflows/logs", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
```

--------------------------------

TITLE: Create Next.js Workflow Endpoint
DESCRIPTION: Defines a basic workflow endpoint in a Next.js `app/api/workflow/route.ts` file using the `@upstash/workflow/nextjs` serve function. It includes two simple steps.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: typescript
CODE:
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

--------------------------------

TITLE: Creating Stripe Customer after Webhook Event (TypeScript)
DESCRIPTION: Illustrates performing subsequent operations after validating a webhook event, such as creating a customer record in Stripe. This uses `context.run` to encapsulate the Stripe API call.

SOURCE: https://upstash.com/docs/workflow/howto/use-webhooks

LANGUAGE: TypeScript
CODE:
```
export const { POST } = serve(async (context) => {
  // ... Previous validation and user data extraction
  if (!user) {
    return;
  }
  const customer = await context.run("create-stripe-customer", async () => {
    return await stripe.customers.create({
      email: user.email,
      name: `${user.firstName} ${user.lastName}`,
      metadata: {
        userId: user.userId,
      },
    });
  });
  /// ... Additional steps
});

```

--------------------------------

TITLE: Set Up Basic Webhook Endpoint in Next.js (TypeScript)
DESCRIPTION: Demonstrates setting up a basic webhook endpoint using the `serve` function from `@upstash/workflow/nextjs`. It initializes an endpoint to receive and parse incoming webhook payloads.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(
  async (context) => {
    // Your webhook handling logic here
  },
  {
    initialPayloadParser: (payload) => {
      return payload;
    },
  }
);
```

--------------------------------

TITLE: FastAPI Workflow Endpoint Definition
DESCRIPTION: Defines a FastAPI application and a workflow endpoint using the Upstash Workflow SDK. This code outlines a simple two-step workflow that prints messages.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: python
CODE:
```
from fastapi import FastAPI
from upstash_workflow.fastapi import Serve

app = FastAPI()
serve = Serve(app)

@serve.post("/api/workflow")
async def workflow(context):
    async def _step1() -> None:
        print("initial step ran")
    await context.run("initial-step", _step1)

    async def _step2() -> None:
        print("second step ran")
    await context.run("second-step", _step2)
```

--------------------------------

TITLE: Configure .env for Local Tunnel
DESCRIPTION: Sets environment variables for Upstash Workflow URL and QStash token when using a local tunnel. This connects your local endpoint to the production QStash for logging.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
export QSTASH_TOKEN="***"
export UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Store Processed Images
DESCRIPTION: Stores processed images in cloud storage and retrieves their URLs. It maps over the processed images, using `context.run` to execute an asynchronous `storeImage` function for each, and then collects all resulting URLs using `Promise.all`.

SOURCE: https://upstash.com/docs/workflow/examples/imageProcessing

LANGUAGE: TypeScript
CODE:
```
const storedImageUrls: string[] = await Promise.all(
  processedImages.map(
    processedImage => context.run(`store-image`, async () => {
      return await storeImage(processedImage.body.imageUrl)
    })
  )
)
```

--------------------------------

TITLE: Define SolidJS Workflow Endpoint
DESCRIPTION: Defines a workflow endpoint in a SolidJS project using the Upstash Workflow SDK. This TypeScript code sets up two steps: 'initial-step' and 'second-step'.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/solidjs"
export const { POST } = serve(async (context) => {
  await context.run("initial-step", () => {
    console.log("initial step ran")
  })
  await context.run("second-step", () => {
    console.log("second step ran")
  })
})
```

--------------------------------

TITLE: Fetch Workflow Run Logs with cURL
DESCRIPTION: An example of how to fetch workflow run logs using cURL. This command includes the necessary authorization header for accessing the logs via the Upstash API.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```

```

--------------------------------

TITLE: Source Environment File (Bash)
DESCRIPTION: Loads environment variables defined in the .env file into the current shell session. This command is crucial before starting development servers to ensure that the application has access to the necessary configuration.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
source .env
```

--------------------------------

TITLE: Configure Upstash Workflow Retries
DESCRIPTION: Details the default retry counts for Upstash Workflows at different configuration points: Workflow Start, Context Call, and Serve Options.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: APIDOC
CODE:
```
Retry Configuration:

1. Workflow Start (publish/publishJSON or client.trigger):
   - Default retries: 3

2. Context Call:
   - Default retries: 0

3. Serve Options:
   - Default retries: 3
   - Covers all other requests except the above two.
```

--------------------------------

TITLE: Unsuspend User on Payment Success (TypeScript)
DESCRIPTION: Checks if a user is suspended and unsuspend them if the payment is successful. This function relies on `checkSuspension` and `unsuspendUser`.

SOURCE: https://upstash.com/docs/workflow/examples/paymentRetry

LANGUAGE: TypeScript
CODE:
```
const isSuspended = await context.run("check suspension", async () => {
  return await checkSuspension(email);
});
if (isSuspended) {
  await context.run("unsuspend user", async () => {
    await unsuspendUser(email);
  });
}
```

--------------------------------

TITLE: Initialize Upstash Workflow Endpoint (TypeScript)
DESCRIPTION: This TypeScript snippet shows the basic setup for an Upstash Workflow endpoint using `serve`. It initializes a loop intended to make API calls up to 10 times, forming the foundation for custom retry logic.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<{ userData: string }>(async (context) => {
  for (let attempt = 0; attempt < 10; attempt++) {
    // TODO: call API in here
  }
})
```

--------------------------------

TITLE: Upstash QStash: Publish Your First Message
DESCRIPTION: Publish your first message using QStash, Upstash's messaging service. QStash facilitates asynchronous communication and event-driven architectures.

SOURCE: https://upstash.com/docs/introduction

LANGUAGE: text
CODE:
```
QStash
Publish your first message
```

--------------------------------

TITLE: Create Workflow Endpoint in Next.js
DESCRIPTION: Defines a workflow endpoint within a Next.js application using the `@upstash/workflow/nextjs` library. This example includes two sequential steps: 'initial-step' and 'second-step'.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
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

--------------------------------

TITLE: Run Local Workflow Endpoint (npm)
DESCRIPTION: Starts your worker locally using npm. This command prints a local URL (defaulting to http://localhost:8787) for your workflow endpoint and ensures access to QStash bindings.

SOURCE: https://upstash.com/docs/workflow/quickstarts/cloudflare-workers

LANGUAGE: bash
CODE:
```
npm run wrangler dev
```

--------------------------------

TITLE: Update Workflow Step (JavaScript)
DESCRIPTION: Example of modifying an existing step in a workflow. It uses the Upstash Workflow SDK to update a specific step with new handler logic.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const workflow = new Workflow('your-workflow-id', 'your-api-key');

const updatedStepData = {
  handler: 'console.log(\'Updated message!\')'
};

workflow.update_step('your-step-id', updatedStepData)
  .then(step => {
    console.log('Step updated:', step);
  })
  .catch(error => {
    console.error('Error updating step:', error);
  });
```

--------------------------------

TITLE: Get Flow-Control Information
DESCRIPTION: Retrieves information about a specific flow control key, including its wait list size. This requires an authorization token.

SOURCE: https://upstash.com/docs/workflow/rest/flow-control/get

LANGUAGE: curl
CODE:
```
curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Send Welcome Email (Python)
DESCRIPTION: This snippet sends a welcome email to the user upon trial initiation using Python. It utilizes `context.run` to execute the `send_email` function, providing the user's email and a welcome message.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _send_welcome_email() -> None:
    await send_email(
        email, "Welcome to our platform!, You have 14 days of free trial."
    )

await context.run("send welcome email", _send_welcome_email)
```

--------------------------------

TITLE: Run Cloudflare Worker Locally
DESCRIPTION: Starts a Cloudflare worker locally using the 'wrangler dev' command. This command facilitates local testing by providing a local URL for the workflow endpoint.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run wrangler dev
```

--------------------------------

TITLE: Configure Local QStash Environment Variables
DESCRIPTION: Sets the QSTASH_URL and QSTASH_TOKEN environment variables in the .env file for local QStash server integration. Replace <QSTASH_TOKEN> with your actual token.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
export QSTASH_URL="http://127.0.0.1:8080"
export QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Performing Subsequent Operations After Webhook Event (Python)
DESCRIPTION: Following initial webhook event processing, this example demonstrates how to perform additional operations, such as creating a customer record in Stripe, using `context.run`. This ensures that each external API call or significant step is trackable and retryable within the Upstash Workflow, leveraging previously extracted user data.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    # ... Previous validation and user data extraction

    if not user:
        return

    async def _create_stripe_customer():
        return await stripe.customers.create(
            email=user["email"],
            name=f"{user['first_name']} {user['last_name']}",
            metadata={"user_id": user["user_id"]},
        )

    customer = await context.run("create-stripe-customer", _create_stripe_customer)

    # ... Additional steps



```

--------------------------------

TITLE: Process Order Data Step (JavaScript)
DESCRIPTION: Demonstrates a step in an Upstash Workflow where processed data from an event is handled. This example logs the received data, simulating backend operations like database updates.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
await context.run("process-order", async () => {
  console.log(`Order ${orderId} processed:`, processedData);
});

```

--------------------------------

TITLE: Monitor Workflow Execution (TypeScript)
DESCRIPTION: Example of monitoring workflow execution in TypeScript using Upstash Workflow. It demonstrates running tasks like retrieving emails and fetching data from an LLM concurrently.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { retrieveEmail, fetchFromLLm, UserRequest} from "../../../lib/util";
export const { POST } = serve<UserRequest>(
  async (context) => {
    const input = context.requestPayload;
    await context.sleep("sleep", 10);
    const p1 = context.run("retrieveEmail", async () => {
      return retrieveEmail(input.id);
    });
    const p2 = context.run("askllm", async () => {
      return fetchFromLLm(input.question);
    });
    await Promise.all([p1, p2])
  },
);

```

--------------------------------

TITLE: Cancel Workflow Runs (JavaScript)
DESCRIPTION: Cancels workflow runs. Supports canceling by specific run IDs or by a URL prefix to cancel all runs starting with that URL.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
// cancel a single workflow
await client.cancel({ ids: "<WORKFLOW_RUN_ID>" });
// cancel a set of workflow runs
await client.cancel({ ids: ["<WORKFLOW_RUN_ID_1>", "<WORKFLOW_RUN_ID_2>"] });
```

LANGUAGE: javascript
CODE:
```
await client.cancel({ urlStartingWith: "https://your-endpoint.com" });
```

--------------------------------

TITLE: Implement Image Processing Workflow with Upstash Workflow (TypeScript)
DESCRIPTION: This comprehensive TypeScript example defines an Upstash Workflow that orchestrates image processing. It handles retrieving an image, resizing it to multiple resolutions, applying various filters, and finally storing the processed images in cloud storage. It utilizes `context.run` for internal operations and `context.call` for interacting with external image processing services, demonstrating parallel execution with `Promise.all`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
import {
  resizeImage,
  applyFilters,
  storeImage,
  getImageUrl,
} from "./utils"

type ImageResult = {
  imageUrl: string
}

export const { POST } = serve<{ imageId: string; userId: string } }}(
  async (context) => {
    const { imageId, userId } = context.requestPayload

    // Step 1: Retrieve the uploaded image
    const imageUrl = await context.run("get-image-url", async () => {
      return await getImageUrl(imageId)
    })

    // Step 2: Resize the image to multiple resolutions
    const resolutions = [640, 1280, 1920]

    const resizedImages: { body: ImageResult }[] = await Promise.all(resolutions.map(
      resolution => context.call<ImageResult>(
        `resize-image-${resolution}`,
        {
          // endpoint which returns ImageResult type in response
          url: "https://image-processing-service.com/resize",
          method: "POST",
          body: {
            imageUrl,
            width: resolution,
          }
        }
      )
    ))

    // Step 3: Apply filters to each resized image
    const filters = ["grayscale", "sepia", "contrast"]
    const processedImagePromises: Promise<string>[] = []

    for (const resizedImage of resizedImages) {
      for (const filter of filters) {
        const processedImagePromise = context.call<ImageResult>(
          `apply-filter-${filter}`,
          {
            // endpoint which returns ImageResult type in response
            url: "https://image-processing-service.com/filter",
            method: "POST",
            body: {
              imageUrl: resizedImage.body.imageUrl,
              filter,
            }
          }
        )
        processedImagePromises.push(processedImagePromise)
      }
    }
    const processedImages: { body: ImageResult }[] = await Promise.all(processedImagePromises)

    // Step 4: Store processed images in cloud storage
    const storedImageUrls: string[] = await Promise.all(
      processedImages.map(
        processedImage => context.run(`store-image`, async () => {

```

--------------------------------

TITLE: Successful Bulk Cancel Response
DESCRIPTION: An example of a successful response (HTTP 202 Accepted) for a bulk workflow cancellation. It indicates the number of workflow runs processed for cancellation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
{
  "cancelled": 10
}
```

--------------------------------

TITLE: Define and Run Workflow Steps in Python
DESCRIPTION: This Python code defines an asynchronous FastAPI endpoint that processes a string payload. It demonstrates how to declare and execute sequential workflow steps using `context.run`, passing data between them. The example includes two steps, each performing a `some_work` operation and printing intermediate results.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-py

LANGUAGE: Python
CODE:
```
@serve.post("/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    # get request body:
    input = context.request_payload

    async def _step1() -> str:
        output = some_work(input)
        print("step 1 input", input, "output", output)
        return output

    # run the first step:
    result: str = await context.run("step1", _step1)

    async def _step2() -> None:
        output = some_work(result)
        print("step 2 input", result, "output", output)

    # run the second step:
    await context.run("step2", _step2)
```

--------------------------------

TITLE: Performing Subsequent Operations After Webhook Event (TypeScript)
DESCRIPTION: Following initial webhook event processing, this example demonstrates how to perform additional operations, such as creating a customer record in Stripe, using `context.run`. This ensures that each external API call or significant step is trackable and retryable within the Upstash Workflow, leveraging previously extracted user data.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve(async (context) => {
  // ... Previous validation and user data extraction

  if (!user) {
    return;
  }

  const customer = await context.run("create-stripe-customer", async () => {
    return await stripe.customers.create({
      email: user.email,
      name: `${user.firstName} ${user.lastName}`,
      metadata: {
        userId: user.userId,
      },
    });
  });

  /// ... Additional steps
});
```

--------------------------------

TITLE: Trigger Workflow Endpoint
DESCRIPTION: Makes a POST request to the local workflow endpoint to trigger a workflow run and returns a unique workflow run ID.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:3000/api/workflow
# result: {"workflowRunId":"wfr_xxxxxx"}

```

--------------------------------

TITLE: Minimal Workflow Endpoint (Next.js App Router - TypeScript)
DESCRIPTION: A minimal example of defining a workflow endpoint using `@upstash/workflow/nextjs` in a Next.js App Router `route.ts` file, demonstrating two sequential steps.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
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

--------------------------------

TITLE: Serve Upstash Workflow Endpoint in Next.js
DESCRIPTION: Demonstrates how to use the `serve` function from `@upstash/workflow/nextjs` to create a Next.js API route for handling workflow requests. It includes an example of waiting for an event with a specified timeout.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve<{ topic: string }>(async (context) => {
  const request = context.requestPayload;

  const {
    eventData, // data passed in notify
    timeout, // boolean denoting whether the step was notified or timed out
  } = await context.waitForEvent("wait for some event", "my-event-id", {
    timeout: "1000s", // 1000 second timeout
  });
});
```

--------------------------------

TITLE: Resize Image to Multiple Resolutions (TypeScript)
DESCRIPTION: This TypeScript code demonstrates resizing an image to multiple resolutions (640, 1280, 1920) using Upstash Workflow's `context.call` function. It sends POST requests to an external image processing service for each resolution and uses `Promise.all` to execute these calls concurrently.

SOURCE: https://upstash.com/docs/workflow/examples/imageProcessing

LANGUAGE: TypeScript
CODE:
```
const resolutions = [640, 1280, 1920]
const resizedImages: { body: ImageResult }[] = await Promise.all(resolutions.map(
  resolution => context.call<ImageResult>(
    `resize-image-${resolution}`,
    {
      // endpoint which returns ImageResult type in response
      url: "https://image-processing-service.com/resize",
      method: "POST",
      body: {
        imageUrl,
        width: resolution,
      }
    }
  )
))
```

--------------------------------

TITLE: Import Workflow serve Methods (Python)
DESCRIPTION: Imports the `serve` and `async_serve` methods from the `upstash_workflow` package. These methods provide the foundational integration points for using Upstash Workflow with custom Python platforms.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from upstash_workflow import serve, async_serve

```

--------------------------------

TITLE: Define Minimal Workflow Endpoint (Next.js Pages Router)
DESCRIPTION: A minimal example of defining a workflow endpoint using `servePagesRouter` for Next.js Pages Router (`src/pages/api/workflow.ts`). It sets up a basic workflow with two steps, `initial-step` and `second-step`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { servePagesRouter } from "@upstash/workflow/nextjs";

const { handler } = servePagesRouter<string>(
  async (context) => {
    await context.run("initial-step", () => {
      console.log("initial step ran")
    })

    await context.run("second-step", () => {
      console.log("second step ran")
    })
  }
)
export default handler;

```

--------------------------------

TITLE: Trigger Workflow with cURL
DESCRIPTION: Example using cURL to send a POST request to the Express.js workflow endpoint. This triggers the workflow and returns a unique workflow run ID.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -X POST http://localhost:3000/workflow \
    -H "Content-Type: application/json" \
    -d '{"message": "Hello from the workflow!"}'
```

--------------------------------

TITLE: List Workflow Runs in DLQ (cURL)
DESCRIPTION: This example shows how to list workflow runs currently in the Dead Letter Queue (DLQ) using a cURL request. It includes the necessary authorization header.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl https://qstash.upstash.io/v2/workflows/dlq \
  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Example Bulk Cancel Workflows Response
DESCRIPTION: The expected JSON response after successfully calling the Bulk Cancel Workflows API endpoint. It indicates the number of workflow runs that were canceled.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
{
  "cancelled": 10
}
```

--------------------------------

TITLE: Process Data Chunks with OpenAI GPT-4
DESCRIPTION: Iterates through data chunks and sends each to OpenAI's GPT-4 for analysis. It utilizes `context.api.openai.call` for non-blocking API requests, specifying the model, messages, and token. The response contains processed chunk data.

SOURCE: https://upstash.com/docs/workflow/examples/allInOne

LANGUAGE: typescript
CODE:
```
for (let i = 0; i < chunks.length; i++) {
  const { body: processedChunk } = await context.api.openai.call<OpenAiResponse>(
    `process-chunk-${i}`,
    {
      token: process.env.OPENAI_API_KEY!,
      operation: "chat.completions.create",
      body: {
        model: "gpt-4",
        messages: [
          {
            role: "system",
            content:
              "You are an AI assistant tasked with analyzing data chunks. Provide a brief summary and key insights for the given data.",
          },
          {
            role: "user",
            content: `Analyze this data chunk: ${JSON.stringify(chunks[i])}`,
          },
        ],
        max_completion_tokens: 150,
      },
    }
  )
}
```

--------------------------------

TITLE: Download Dataset with Upstash Context Call
DESCRIPTION: This code snippet demonstrates how to download a dataset using `context.call` within an Upstash workflow. This method is suitable for making HTTP requests that may exceed standard serverless execution time limits, providing a longer timeout.

SOURCE: https://upstash.com/docs/workflow/examples/allInOne

LANGUAGE: typescript
CODE:
```
const datasetUrl = await context.run("get-dataset-url", async () => {
  return await getDatasetUrl(request.datasetId)
})
const { body: dataset } = await context.call("download-dataset", {
  url: datasetUrl,
  method: "GET"
})
```

--------------------------------

TITLE: Verify Production Workflow Endpoint with cURL
DESCRIPTION: This snippet demonstrates how to verify that your deployed workflow endpoint is accessible in production. It uses the cURL command to send a POST request to your production URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
curl -X POST https://<YOUR-PRODUCTION-URL>/api/workflow
```

--------------------------------

TITLE: QStash CLI Development Server Output
DESCRIPTION: This snippet shows the typical output from the QStash CLI when its local development server is running. It provides the URL, default user credentials (QSTASH_TOKEN), and signing keys necessary for local testing. It also includes a sample cURL request for publishing messages.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
Upstash QStash development server is runnning at http://127.0.0.1:8080
A default user has been created for you to authorize your requests.
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7RvLjqfZBvP5KEUimQCE1pvpLuou
QSTASH_NEXT_SIGNING_KEY=sig_7W3ZNbfKWk5NWwEs3U4ixuQ7fxwE
Sample cURL request:
curl -X POST http://127.0.0.1:8080/v2/publish/https://example.com -H "Authorization: Bearer eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0="
Check out documentation for more details:
https://upstash.com/docs/qstash/howto/local-development
```

--------------------------------

TITLE: Get Waiters for an Event
DESCRIPTION: Retrieve a list of all workflow runs that are currently waiting for a specific event ID. This helps in understanding which workflows are pending a particular event.

SOURCE: https://upstash.com/docs/workflow/basics/client

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" });
const result = await client.getWaiters({
  eventId: "my-event-id",
});
```

--------------------------------

TITLE: Upstash Workflow AI Data Processing Example
DESCRIPTION: Demonstrates advanced AI data processing using Upstash Workflow. The workflow downloads a large dataset, processes it in chunks using OpenAI’s GPT-4 model, aggregates the results, and generates a report.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
/*
  This example demonstrates advanced AI data processing using Upstash Workflow.
  The following example workflow downloads a large dataset, processes it in chunks using OpenAI’s GPT-4 model, aggregates the results and generates a report.

  Use Case:
  Our workflow will:
    1. Receive a request to process a dataset
    2. Download the dataset from a remote source
    3. Process the data in chunks using OpenAI
    4. Aggregate results
    5. Generate and send a final report
*/

// Placeholder for actual workflow implementation
console.log('Upstash Workflow AI Generation Example');

```

--------------------------------

TITLE: Implement 'Ask AI' Tool with context.run() in JavaScript
DESCRIPTION: This snippet shows how to implement an 'Ask AI' tool by wrapping its execution logic within a `context.run()` call. It includes a placeholder for a weather API call and returns mock weather data.

SOURCE: https://upstash.com/docs/workflow/integrations/aisdk

LANGUAGE: JavaScript
CODE:
```
execute: ({ location }) => context.run("weather tool", () => {
  // Mock data, replace with actual weather API call
  return {
    location,
    temperature: 72 + Math.floor(Math.random() * 21) - 10,
  };
})
```

--------------------------------

TITLE: Trigger Workflow Endpoint
DESCRIPTION: Sends a POST request to the FastAPI workflow endpoint using curl. This initiates a workflow run, and a unique run ID is returned upon success.

SOURCE: https://upstash.com/docs/workflow/quickstarts/fastapi

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:8000/api/workflow
```

--------------------------------

TITLE: Create Workflow Step (JavaScript)
DESCRIPTION: Example of how to create a new step within a workflow using the Upstash Workflow JS library. It shows how to instantiate a Workflow object and use the `create_step` method with step data.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const workflow = new Workflow('your-workflow-id', 'your-api-key');

const stepData = {
  name: 'my-first-step',
  handler: 'console.log(\'Hello, Upstash!\')',
  next: 'another-step-id'
};

workflow.create_step(stepData)
  .then(step => {
    console.log('Step created:', step);
  })
  .catch(error => {
    console.error('Error creating step:', error);
  });
```

--------------------------------

TITLE: Trigger Local Workflow Endpoint (Curl)
DESCRIPTION: An example using `curl` to send a POST request to a locally running SolidJS workflow endpoint. A successful request returns a workflow run ID.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -X POST https://localhost:3000/api/workflow
```

--------------------------------

TITLE: AI Generation Workflow with Upstash
DESCRIPTION: This TypeScript code defines a workflow using Upstash. It handles downloading a dataset, processing it in chunks using OpenAI's GPT-4 API, aggregating intermediate results, and generating a final report. It utilizes Upstash's `serve` function for Next.js integration and `context.call` for long-running HTTP requests.

SOURCE: https://upstash.com/docs/workflow/examples/allInOne

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs"
import {
  downloadData,
  aggregateResults,
  generateReport,
  sendReport,
  getDatasetUrl,
  splitIntoChunks,
} from "./utils"
type OpenAiResponse = {
  choices: {
    message: {
      role: string,
      content: string
    }
  }[]
}
export const { POST } = serve<{ datasetId: string; userId: string } }}(
  async (context) => {
    const request = context.requestPayload
    // Step 1: Download the dataset
    const datasetUrl = await context.run("get-dataset-url", async () => {
      return await getDatasetUrl(request.datasetId)
    })
    // HTTP request with much longer timeout (2hrs)
    const { body: dataset } = await context.call("download-dataset", {
      url: datasetUrl,
      method: "GET"
    })
    // Step 2: Process data in chunks using OpenAI
    const chunkSize = 1000
    const chunks = splitIntoChunks(dataset, chunkSize)
    const processedChunks: string[] = []
    for (let i = 0; i < chunks.length; i++) {
      const { body: processedChunk } = await context.api.openai.call(
        `process-chunk-${i}`,
        {
          token: process.env.OPENAI_API_KEY,
          operation: "chat.completions.create",
          body: {
            model: "gpt-4",
            messages: [
              {
                role: "system",
                content:
                  "You are an AI assistant tasked with analyzing data chunks. Provide a brief summary and key insights for the given data.",
              },
              {
                role: "user",
                content: `Analyze this data chunk: ${JSON.stringify(chunks[i])}`,
              },
            ],
            max_completion_tokens: 150,
          },
        }
      )
      processedChunks.push(processedChunk.choices[0].message.content!)
      // Every 10 chunks, we'll aggregate intermediate results
      if (i % 10 === 9 || i === chunks.length - 1) {
        await context.run(`aggregate-results${i}`,
          async () => {
            await aggregateResults(processedChunks)
            processedChunks.length = 0
          }
        )
      }
    }
    // Step 3: Generate and send data report
    const report = await context.run("generate-report", async () => {
      return await generateReport(request.datasetId)
    })
    await context.run("send-report", async () => {
      await sendReport(report, request.userId)
    })
  }
)

```

--------------------------------

TITLE: Run Cloudflare Worker Locally with Wrangler (Bash)
DESCRIPTION: Starts a Cloudflare Worker locally using the `wrangler dev` command for local testing during development. This command makes the workflow endpoint accessible.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run wrangler dev
```

--------------------------------

TITLE: Send Trial Warning Email
DESCRIPTION: This workflow sends a warning email to users two days before their trial ends if they haven't upgraded. It first waits for 5 days, checks the upgrade status, and if not upgraded, sends the warning email using the Upstash context.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
await context.sleep("wait for trial warning", 5 * 24 * 60 * 60);
const isUpgraded = await context.run("check upgraded plan", async () => {
  return await checkUpgradedPlan(email);
});
if (isUpgraded) return;
await context.run("send trial warning email", async () => {
  await sendEmail(
    email,
    "Your trial is about to end in 2 days. Please upgrade your plan to keep using our platform."
  );
});
```

--------------------------------

TITLE: Social Media Manager Agent Example
DESCRIPTION: Illustrates a multi-platform social media management system for content moderation and engagement automation using Upstash Workflow Agents. It defines agents and tools for creating posts and moderating content.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { Agent } from '@upstash/workflow';

// Example agent for social media management
const socialMediaAgent = new Agent({
  name: 'social-media-manager',
  description: 'Manages social media posts, moderation, and engagement.',
  // ... other configurations
});

// Define tools for social media management
socialMediaAgent.addTool({
  name: 'createPost',
  description: 'Creates a new post on a social media platform.',
  parameters: {
    type: 'object',
    properties: {
      platform: { type: 'string', description: 'The social media platform (e.g., twitter, instagram)' },
      content: { type: 'string', description: 'The content of the post' },
    },
    required: ['platform', 'content'],
  },
  handler: async ({ platform, content }) => {
    // Implementation to create a post
    console.log(`Creating post on ${platform}: ${content}`);
    return `Post created successfully on ${platform}`;
  },
});

socialMediaAgent.addTool({
  name: 'moderateContent',
  description: 'Moderates content for policy violations.',
  parameters: {
    type: 'object',
    properties: {
      text: { type: 'string', description: 'The text content to moderate' },
    },
    required: ['text'],
  },
  handler: async ({ text }) => {
    // Implementation for content moderation
    console.log('Moderating content...');
    return { isViolating: false };
  },
});

// Example of using the agent
async function manageSocialMedia() {
  const postResult = await socialMediaAgent.run('Create an Instagram post with the text "Check out our new product!"');
  console.log(postResult);

  const moderationResult = await socialMediaAgent.call('moderateContent', { text: 'This is a harmful comment.' });
  console.log('Moderation result:', moderationResult);
}
```

--------------------------------

TITLE: Trigger Upstash Workflow (JavaScript)
DESCRIPTION: Provides an example of how to trigger a deployed Upstash Workflow using the `@upstash/workflow` client. It shows how to instantiate the client with a token and call the `trigger` method with the workflow endpoint URL and a request body.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: { "prompt": "How is the weather in San Francisco around this time?" },
});

```

--------------------------------

TITLE: Get Dataset URL and Download Content
DESCRIPTION: This TypeScript snippet demonstrates obtaining a dataset URL and then downloading the dataset content. It utilizes `context.run` for task management and `context.call` for making HTTP requests with extended timeouts.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
const datasetUrl = await context.run("get-dataset-url", async () => {
  return await getDatasetUrl(request.datasetId)
})
const { body: dataset } = await context.call("download-dataset", {
  url: datasetUrl,
  method: "GET"
})
```

--------------------------------

TITLE: JSON: Successful Bulk Cancel Response
DESCRIPTION: An example of a successful HTTP 202 Accepted response after a bulk workflow cancellation. It indicates the number of workflow runs processed for cancellation.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
{
  "cancelled": 10
}
```

--------------------------------

TITLE: QStash CLI Development Server Output
DESCRIPTION: Displays the startup output of the QStash local development server, including its address and default credentials. These are crucial for configuring applications to use the local server.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: plaintext
CODE:
```
Upstash QStash development server is runnning at http://127.0.0.1:8080

A default user has been created for you to authorize your requests.
QSTASH_TOKEN=eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0=
QSTASH_CURRENT_SIGNING_KEY=sig_7RvLjqfZBvP5KEUimQCE1pvpLuou
QSTASH_NEXT_SIGNING_KEY=sig_7W3ZNbfKWk5NWwEs3U4ixuQ7fxwE

Sample cURL request:
curl -X POST http://127.0.0.1:8080/v2/publish/https://example.com -H "Authorization: Bearer eyJVc2VySUQiOiJkZWZhdWx0VXNlciIsIlBhc3N3b3JkIjoiZGVmYXVsdFBhc3N3b3JkIn0="

Check out documentation for more details:
https://upstash.com/docs/qstash/howto/local-development
```

--------------------------------

TITLE: Trigger Workflow Endpoint
DESCRIPTION: Sends a POST request to the Flask application's workflow endpoint to initiate a workflow run. Returns a unique workflow run ID.

SOURCE: https://upstash.com/docs/workflow/quickstarts/flask

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:8000/api/workflow
# result: {"workflowRunId":"wfr_xxxxxx"}
```

--------------------------------

TITLE: Restart Workflow Run Example (cURL)
DESCRIPTION: Demonstrates how to restart a failed workflow run from the Dead Letter Queue (DLQ) using a cURL command. This includes setting the authorization header and specifying a new workflow run ID.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -X POST https://qstash.upstash.io/v2/dlq/restart/dlq_XYZ \
-H "Authorization: Bearer <token>" \
-H "Upstash-Workflow-RunId: my-restarted-workflow-XYZ"
```

--------------------------------

TITLE: Customize Initial Payload Parsing (TypeScript)
DESCRIPTION: Demonstrates how to define a custom function for processing the initial request payload when an Upstash Workflow starts in TypeScript. The parsed data is accessible via `context.requestPayload`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
type InitialPayload = {
  foo: string;
  bar: number;
};

// 👇 1: provide initial payload type
export const { POST } = serve<InitialPayload>(
  async (context) => {

```

--------------------------------

TITLE: Example Notify Response (JSON)
DESCRIPTION: This JSON snippet shows a successful response from the notify endpoint. It's an array containing an object with a `waiter` object (detailing the resumed workflow) and a `messageId` for the sent message.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
[
  {
    "waiter": {
      "url": "https://my-workflow.com/path",
      "headers": {
        "Upstash-Workflow-Runid": [
          "wfr_melCHYvPkVhDqIhhk2"
        ],
        "Upstash-Workflow-Url": [
          "https://my-workflow.com/path"
        ]
      },
      "deadline": 1729869206
    },
    "messageId": "msg_26hZCxxbG2TT3AnHEr1w"
  }
]
```

--------------------------------

TITLE: Correct Step Execution Order
DESCRIPTION: This example illustrates the correct way to structure a workflow step before calling `generateText`. It shows a step that retrieves the prompt from the request payload, ensuring `generateText` is not called first.

SOURCE: https://upstash.com/docs/workflow/integrations/aisdk

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<{ prompt: string }>(async (context) => {
  const openai = createWorkflowOpenAI(context);
  // Will throw "prompt is undefined"
  const result = await generateText({
    model: openai('gpt-3.5-turbo'),
    prompt: context.requestPayload.prompt
  });
});

```

--------------------------------

TITLE: Setting Up Environment Variables (Bash)
DESCRIPTION: Configures environment variables for QStash token and OpenAI API key, which are essential for authenticating with the respective services required by the Workflow Agents API.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
QSTASH_TOKEN="<QSTASH_TOKEN>"
OPENAI_API_KEY="<OPENAI_API_KEY>"
```

--------------------------------

TITLE: Define Python Onboarding Workflow
DESCRIPTION: Defines an asynchronous onboarding workflow in Python using Upstash Workflow. It includes sending welcome emails, pausing, calling an AI service, and sending follow-up emails. Dependencies include FastAPI and Upstash Workflow libraries.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from fastapi import FastAPI
from typing import Dict, TypedDict
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext, CallResponse
from email_utils import send_email

app = FastAPI()
serve = Serve(app)

class UserProfile(TypedDict):
    name: str
    email: str

async def onboarding_workflow(context: AsyncWorkflowContext, user_profile: UserProfile):
    await context.run(send_email(user_profile['email'], 'Welcome!', 'Welcome to our service!'))
    await context.sleep(days=3)
    ai_message = await context.call("ai_service", "generate_message", name=user_profile['name'])
    await context.run(send_email(user_profile['email'], 'Follow-up', ai_message))

serve.add_workflow(onboarding_workflow)
```

--------------------------------

TITLE: Upstash Workflow Logs API Response Example (JSON)
DESCRIPTION: Presents a sample successful response from the Upstash Workflow logs API. This JSON object details a single workflow run, including its ID, URL, state, timestamps, and a breakdown of its execution steps, both sequential and parallel.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: JSON
CODE:
```
{
  "cursor": "1686652644442-12",
  "runs": [
    {
      "workflowRunId": "wfr_rj0Upr1rvdzGfz96fXNHh",
      "workflowUrl": "https://feasible-eft-notably.ngrok-free.app/api/call",
      "workflowState": "RUN_SUCCESS",
      "workflowRunCreatedAt": 1736340463061,
      "workflowRunCompletedAt": 1736340464684,
      "steps": [
        {
          "steps": [
            {
              "stepName": "init",
              "stepType": "Initial",
              "callType": "step",
              "messageId": "msg_7YoJxFpwkEy5zBp378JgvD6YBDPBEqkBPje2JGTCEUiASMJQ1FwY9",
              "concurrent": 1,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340463064
            }
          ],
          "type": "sequential"
        },
        {
          "steps": [
            {
              "stepId": 1,
              "stepName": "external call",
              "stepType": "Run",
              "callType": "step",
              "messageId": "msg_26hZCxZCuWyyTWPmSVBrNCtiJGNsULmt63vFfcZxQ3sfYFKLZe2dKww4BSb2kVF",
              "out": "1",
              "concurrent": 2,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340464111
            },
            {
              "stepId": 2,
              "stepName": "external call 2",
              "stepType": "Run",
              "callType": "step",
              "messageId": "msg_26hZCxZCuWyyTWPmSVBrNB882AMRP1TsgzpygELRcLWep4ACNTTsCHhrZuaNLij",
              "out": "2",
              "concurrent": 2,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340463895
            }
          ],
          "type": "parallel"
        }
      ]
    }
  ]
}
```

--------------------------------

TITLE: Trigger Upstash Workflow with Client (TypeScript)
DESCRIPTION: This snippet demonstrates the recommended way to start an Upstash workflow using the `@upstash/workflow` client. It returns the workflow run ID and results in fewer QStash publishes. Parameters include the workflow URL, optional body, headers, a custom workflow run ID, and retries for the initial request.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
import { Client } from "@upstash/workflow";

const client = new Client({ token: "<QSTASH_TOKEN>" });

const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: "hello there!",         // Optional body
  headers: { ... },             // Optional headers
  workflowRunId: "my-workflow", // Optional workflow run ID
  retries: 3                    // Optional retries for the initial request
});
```

--------------------------------

TITLE: Minimal Workflow Endpoint (Next.js App Router)
DESCRIPTION: A minimal example of defining a workflow endpoint using `@upstash/workflow/nextjs` in a Next.js App Router `route.ts` file. It demonstrates two sequential steps, `initial-step` and `second-step`, executed within the `serve` function.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
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

--------------------------------

TITLE: Send Invoice Email on Payment Success (TypeScript)
DESCRIPTION: Sends an invoice email to the user after a successful payment, including invoice details. This function uses the `sendEmail` utility.

SOURCE: https://upstash.com/docs/workflow/examples/paymentRetry

LANGUAGE: TypeScript
CODE:
```
await context.run("send invoice email", async () => {
  await sendEmail(
    email,
    `Payment successful. Invoice: ${result.invoiceId}, Total cost: $${result.totalCost}`
  );
});
```

--------------------------------

TITLE: Workflow Run Details
DESCRIPTION: Example JSON response detailing a workflow run. It includes the workflow run ID, URL, state, creation and completion timestamps, and a breakdown of steps executed in sequential and parallel execution flows.

SOURCE: https://upstash.com/docs/workflow/rest/runs/logs

LANGUAGE: json
CODE:
```
{
  "cursor": "1686652644442-12",
  "runs": [
    {
      "workflowRunId": "wfr_rj0Upr1rvdzGfz96fXNHh",
      "workflowUrl": "https://feasible-eft-notably.ngrok-free.app/api/call",
      "workflowState": "RUN_SUCCESS",
      "workflowRunCreatedAt": 1736340463061,
      "workflowRunCompletedAt": 1736340464684,
      "steps": [
        {
          "steps": [
            {
              "stepName": "init",
              "stepType": "Initial",
              "callType": "step",
              "messageId": "msg_7YoJxFpwkEy5zBp378JgvD6YBDPBEqkBPje2JGTCEUiASMJQ1FwY9",
              "concurrent": 1,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340463064
            }
          ],
          "type": "sequential"
        },
        {
          "steps": [
            {
              "stepId": 1,
              "stepName": "external call",
              "stepType": "Run",
              "callType": "step",
              "messageId": "msg_26hZCxZCuWyyTWPmSVBrNCtiJGNsULmt63vFfcZxQ3sfYFKLZe2dKww4BSb2kVF",
              "out": "1",
              "concurrent": 2,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340464111
            },
            {
              "stepId": 2,
              "stepName": "external call 2",
              "stepType": "Run",
              "callType": "step",
              "messageId": "msg_26hZCxZCuWyyTWPmSVBrNB882AMRP1TsgzpygELRcLWep4ACNTTsCHhrZuaNLij",
              "out": "2",
              "concurrent": 2,
              "state": "STEP_SUCCESS",
              "createdAt": 1736340463895
            }
          ],
          "type": "parallel"
        }
      ]
    }
  ]
}
```

--------------------------------

TITLE: Configure Local QStash Server Environment
DESCRIPTION: Configures the .dev.vars file with the QSTASH_URL and QSTASH_TOKEN obtained from running the local QStash server. This allows the application to connect to the local QStash instance.

SOURCE: https://upstash.com/docs/workflow/quickstarts/hono

LANGUAGE: shell
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Validate Webhook Requests (TypeScript)
DESCRIPTION: Illustrates a TypeScript example for validating incoming webhook requests using a `validateRequest` function. This is a critical security measure to ensure the authenticity of webhook sources.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<string>(async (context) => {
	const payloadString = context.requestPayload;
	const headerPayload = context.headers;
    let event: WebhookEvent;
    try {
    	event = await validateRequest(payloadString, headerPayload);
    } catch {
    	return
    }
    // Next steps based on the event
})
```

--------------------------------

TITLE: Fetch Workflow Message Logs (Go)
DESCRIPTION: This Go snippet demonstrates how to make a GET request to the `/v2/workflows/messageLogs` endpoint using the standard `net/http` package. It constructs a new HTTP request, sets the `Authorization` header with a Bearer token, and executes the request to fetch workflow logs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: go
CODE:
```
req, err := http.NewRequest("GET", "https://qstash.upstash.io/v2/workflows/messageLogs", nil)
if err != nil {
  log.Fatal(err)
}
req.Header.Set("Authorization", "Bearer <token>")
resp, err := http.DefaultClient.Do(req)
if err != nil {
  log.Fatal(err)
}
def resp.Body.Close()
```

--------------------------------

TITLE: Python: Fetch Workflow Logs with Requests
DESCRIPTION: Uses the `requests` library to perform a GET request for workflow logs. It constructs the request with the appropriate authorization header containing the bearer token for authentication.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
import requests
headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/workflows/logs',
  headers=headers
)
```

--------------------------------

TITLE: Send Welcome Email (TypeScript)
DESCRIPTION: This snippet sends a welcome email to the user upon trial initiation using TypeScript. It utilizes `context.run` to execute the `sendEmail` function, providing the user's email and a welcome message.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("send welcome email", async () => {
  await sendEmail(
    email,
    "Welcome to our platform!, You have 14 days of free trial."
  );
});
```

--------------------------------

TITLE: Example Workflow Logs API Response
DESCRIPTION: A sample successful response from the workflow logs API, detailing a single workflow run with its ID, URL, state, timestamps, and execution steps. This JSON structure is useful for understanding how workflow execution data is reported.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
{
  "cursor": "1686652644442-12",
  "runs": [
    {
      "workflowRunId": "wfr_rj0Upr1rvdzGfz96fXNHh",
      "workflowUrl": "https://feasible-eft-notably.ngrok-free.app/api/call",
      "workflowState": "RUN_SUCCESS",
      "workflowRunCreatedAt": 1736340463061,

```

--------------------------------

TITLE: Bypassing Vercel Deployment Protection with cURL
DESCRIPTION: This `curl` command demonstrates how to trigger a workflow on a Vercel preview deployment while bypassing its deployment protection. It requires a previously generated `x-vercel-protection-bypass` secret, which is appended as a query parameter to the workflow URL. The command sends a POST request with 'Hello world!' as data.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
curl -X POST \ 
  -H "Content-Type: application/json" \ 
  -d '{"message": "Hello world!"}' \ 
  "https://your-workflow-url.vercel.app/api/workflow?x-vercel-protection-bypass=<your-secret>"
```

--------------------------------

TITLE: Configure Local Tunnel Environment Variables
DESCRIPTION: Sets the QSTASH_TOKEN and UPSTASH_WORKFLOW_URL environment variables in the .env file for local tunnel integration. Replace '***' with your QStash token and <UPSTASH_WORKFLOW_URL> with your tunnel URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nextjs-flask

LANGUAGE: Shell
CODE:
```
export QSTASH_TOKEN="***"
export UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>
```

--------------------------------

TITLE: Curl Request for Bulk Resume DLQ
DESCRIPTION: This example demonstrates how to use curl to send a POST request to the Upstash Workflow DLQ bulk resume endpoint. It includes necessary headers for authorization, flow control, and retries.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -X POST https://qstash.upstash.io/v2/workflows/dlq/resume \
  -H "Authorization: Bearer <token>" \
  -H "Upstash-Flow-Control-Key: custom-key" \
  -H "Upstash-Flow-Control-Value: parallelism=1" \
  -H "Upstash-Retries: 3"
```

--------------------------------

TITLE: Expose Multiple Workflows with serveMany in Next.js (TypeScript)
DESCRIPTION: Demonstrates using `serveMany` in a Next.js catch-all route to expose multiple workflows created with `createWorkflow`. It shows an example where `workflowOne` invokes `workflowTwo`, highlighting the need for both to be exposed in the same `serveMany` endpoint.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { WorkflowContext } from "@upstash/workflow";
import { createWorkflow, serveMany } from "@upstash/workflow/nextjs";

const workflowOne = createWorkflow(async (context) => {
  await context.run("say hi", () => {
    console.log("workflow one says hi!")
  })

  const { body, isCanceled, isFailed } = await context.invoke("invoking other", {
    workflow: workflowTwo,
    body: "hello from workflow one",
  })

  console.log(`received response from workflowTwo: ${body}`)
})

const workflowTwo = createWorkflow(async (context: WorkflowContext<string>) => {
  await context.run("say hi", () => {
    console.log("workflowTwo says hi!")
    console.log(`received: '${context.requestPayload}' in workflowTwo`)
  })

  return "Workflow two finished!"


```

--------------------------------

TITLE: Missing Workflow Step - Python
DESCRIPTION: This Python workflow illustrates an incorrect setup where `context.run` is omitted. Upstash workflows require at least one step execution to authenticate successfully; otherwise, they will result in a 'Failed to authenticate Workflow request.' error.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    input = context.request_payload
    
    # 👇 Problem: No context.run call
    print("Processing input:", input)
    
    # This workflow will fail with "Failed to authenticate Workflow request."

```

--------------------------------

TITLE: TypeScript: Upstash Workflow failureUrl Example
DESCRIPTION: Configures a `failureUrl` to redirect workflow errors to a specified external URL. This ensures error handling availability and receives a JSON callback body with failure details.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: TypeScript
CODE:
```
export const { POST } = serve<string>(
  async (context) => {
    // Your workflow logic...
  },
  {
    failureUrl: "https://<YOUR_FAILURE_URL>/workflow-failure",
  }
);
```

--------------------------------

TITLE: Store Processed Images and Get URLs (TypeScript)
DESCRIPTION: Stores processed images in cloud storage and retrieves their URLs. This code snippet utilizes `Promise.all` for parallel processing and `context.run` for executing the `storeImage` function.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
const storedImageUrls: string[] = await Promise.all(
  processedImages.map(
    processedImage => context.run(`store-image`, async () => {
      return await storeImage(processedImage.body.imageUrl)
    })
  )
)
```

--------------------------------

TITLE: Cancel Workflow Runs by URL Prefix
DESCRIPTION: Cancel all workflow runs that start with a given URL prefix. This method is effective for stopping all runs associated with a particular endpoint or service.

SOURCE: https://upstash.com/docs/workflow/basics/client

LANGUAGE: javascript
CODE:
```
await client.cancel({ urlStartingWith: "https://your-endpoint.com" });
```

--------------------------------

TITLE: Running Cloudflare Worker Locally with Wrangler
DESCRIPTION: This command starts your Cloudflare Worker locally using `wrangler dev`. It makes your workflow endpoint accessible, typically at `http://localhost:8787`, allowing you to test your workflow during development.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
npm run wrangler dev
```

--------------------------------

TITLE: Fetch Workflow Logs with Node.js Fetch API
DESCRIPTION: Retrieves workflow logs using the native Fetch API by sending a GET request to the QStash API's logs endpoint with an authorization token.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/workflows/logs", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

--------------------------------

TITLE: APIDOC: Get Flow Control Information
DESCRIPTION: Retrieves information about a specific flow control key, including its size in the wait list. This is useful for monitoring and managing message processing parallelism.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: APIDOC
CODE:
```
GET /v2/flowControl/{flowControlKey}

Description:
  Get Information on Flow-Control

Parameters:
  - flowControlKey (string, required): The key of the flow control. See the flow control documentation for more details.

Response (200 OK):
  {
    "flowControlKey": "<string>",
    "waitListSize": 123
  }
  - flowControlKey (string): The key of of the flow control.
  - waitListSize (integer): The number of messages in the wait list that waits for `parallelism` set in the flow control.

Example Request:
  curl -X GET https://qstash.upstash.io/v2/flowControl/YOUR_FLOW_CONTROL_KEY  -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Verify Production Workflow Endpoint
DESCRIPTION: This snippet demonstrates how to verify that your deployed Nuxt.js application's workflow endpoint is accessible in production. It uses `curl` to send a POST request to your production URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/nuxt

LANGUAGE: Bash
CODE:
```
curl -X POST https://<YOUR-PRODUCTION-URL>/api/workflow

```

--------------------------------

TITLE: Pause Workflow Until Timestamp (TypeScript)
DESCRIPTION: Demonstrates pausing a workflow until a specific future timestamp using `context.sleepUntil`. This example pauses execution until one week from the current date before sending an email.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";

export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;

  const user = await context.run("sign-in", async () => {
    return signIn(userData);
  });

  // 👇 Calculate the date for one week from now
  const oneWeekFromNow = new Date();
  oneWeekFromNow.setDate(oneWeekFromNow.getDate() + 7);

  // 👇 Wait until the calculated date

```

--------------------------------

TITLE: Fetch Workflow Logs with Node.js Fetch API
DESCRIPTION: Retrieves workflow logs using the native Fetch API in Node.js. It sends a GET request to the QStash API logs endpoint with an authorization token.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const response = await fetch("https://qstash.upstash.io/v2/workflows/logs", {
  headers: {
    Authorization: "Bearer <token>",
  },
});
```

--------------------------------

TITLE: Configure .dev.vars for Local QStash Server
DESCRIPTION: Adds the local QStash URL and token to the `.dev.vars` file, enabling local workflow testing without incurring production billing.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: txt
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Aggregate Processed Data Chunks
DESCRIPTION: Aggregates results from processed data chunks every 10 chunks or at the end of the dataset. This is done using `context.run` to manage the aggregation task, ensuring that processed chunks are reset after aggregation.

SOURCE: https://upstash.com/docs/workflow/examples/allInOne

LANGUAGE: typescript
CODE:
```
if (i % 10 === 9 || i === chunks.length - 1) {
  await context.run(`aggregate-results${i}`, async () => {
    await aggregateResults(processedChunks)
    processedChunks.length = 0
  })
}
```

--------------------------------

TITLE: Bash: Trigger Workflow Endpoint (Nuxt.js)
DESCRIPTION: Makes a POST request to a Nuxt.js workflow endpoint to initiate a workflow run. This command is used to start a workflow and expects to receive a workflow run ID in response.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:3000/api/workflow
```

--------------------------------

TITLE: Configure QStash Environment Variables for Local Development
DESCRIPTION: Sets up essential environment variables for connecting to a local QStash server. This includes the local URL and a placeholder for the authentication token, enabling local testing and development of workflows.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: text
CODE:
```
QSTASH_URL="http://127.0.0.1:8080"
QSTASH_TOKEN=<QSTASH_TOKEN>
```

--------------------------------

TITLE: Trigger Workflow Endpoint with cURL
DESCRIPTION: Triggers the defined workflow endpoint using cURL. This POST request sends a request to the local endpoint and returns a unique workflow run ID.

SOURCE: https://upstash.com/docs/workflow/quickstarts/solidjs

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:3000/api/workflow
# result: {"workflowRunId":"wfr_xxxxxx"}
```

--------------------------------

TITLE: E-commerce Order Fulfillment Workflow (JavaScript)
DESCRIPTION: An example of an e-commerce order fulfillment workflow implemented using the Upstash Workflow SDK. This workflow automates steps like verifying stock, processing payments, dispatching orders, and sending customer notifications, with simulated external service calls.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
import { workflow } from '@upstash/workflow'

// Define the order fulfillment workflow
export const orderFulfillment = workflow('order-fulfillment', {
  // Input: order details
  input: { 
    orderId: String,
    items: Array<{ productId: String, quantity: Number }>
  },
  // Output: fulfillment status
  output: {
    status: String,
    message: String
  },
  // Define the steps of the workflow
  steps: {
    verifyStock: {
      // Call an external service to check stock availability
      run: async ({ input }) => {
        // Replace with actual stock verification logic
        console.log(`Verifying stock for order ${input.orderId}...`);
        const stockAvailable = Math.random() > 0.1; // Simulate stock availability
        return { stockAvailable, items: input.items };
      },
      next: 'processPayment'
    },
    processPayment: {
      // Call an external service to process payment
      run: async ({ input }) => {
        // Replace with actual payment processing logic
        console.log(`Processing payment for order ${input.orderId}...`);
        const paymentSuccess = Math.random() > 0.05; // Simulate payment success
        return { paymentSuccess, orderId: input.orderId };
      },
      next: 'dispatchOrder'
    },
    dispatchOrder: {
      // Call an external service to dispatch the order
      run: async ({ input }) => {
        // Replace with actual order dispatch logic
        console.log(`Dispatching order ${input.orderId}...`);
        const dispatchSuccess = true; // Simulate dispatch success
        return { dispatchSuccess, orderId: input.orderId };
      },
      next: 'sendNotifications'
    },
    sendNotifications: {
      // Call external services to send confirmation and notification emails
      run: async ({ input }) => {
        // Replace with actual email sending logic
        console.log(`Sending notifications for order ${input.orderId}...`);
        const notificationSuccess = true; // Simulate notification success
        return { notificationSuccess, orderId: input.orderId };
      },
      // End of the workflow
      end: true
    }
  }
});

// Example of how to run the workflow (for demonstration purposes)
// async function runExample() {
//   const result = await orderFulfillment.run({
//     orderId: 'ORD123',
//     items: [
//       { productId: 'PROD456', quantity: 2 },
//       { productId: 'PROD789', quantity: 1 }
//     ]
//   });
//   console.log('Fulfillment Result:', result);
// }

// runExample();

```

--------------------------------

TITLE: Email Analyzer Agent Example (TypeScript)
DESCRIPTION: Showcases the creation and usage of an email analysis agent using Upstash Workflow. This agent can analyze email content, classify it, and generate suggested responses, demonstrating a practical application of workflow agents.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { Agent } from '@upstash/workflow';

// Example agent for email analysis
const emailAnalyzerAgent = new Agent({
  name: 'email-analyzer',
  description: 'Analyzes email content, classifies it, and suggests responses.',
  // ... other configurations
});

// Define tools for email analysis
emailAnalyzerAgent.addTool({
  name: 'analyzeEmailContent',
  description: 'Analyzes the content of an email.',
  parameters: {
    type: 'object',
    properties: {
      emailBody: { type: 'string', description: 'The body of the email' },
    },
    required: ['emailBody'],
  },
  handler: async ({ emailBody }) => {
    // Implementation for email content analysis
    console.log('Analyzing email content...');
    return { classification: 'Inquiry', sentiment: 'Positive' };
  },
});

emailAnalyzerAgent.addTool({
  name: 'generateResponse',
  description: 'Generates a response to an email.',
  parameters: {
    type: 'object',
    properties: {
      analysis: { type: 'object', description: 'The analysis result of the email' },
    },
    required: ['analysis'],
  },
  handler: async ({ analysis }) => {
    // Implementation for generating response
    console.log('Generating response...');
    return 'Thank you for your inquiry. We will get back to you shortly.';
  },
});

// Example of using the agent
async function processEmail() {
  const emailContent = 'Hello, I have a question about your product.';
  const analysis = await emailAnalyzerAgent.call('analyzeEmailContent', { emailBody: emailContent });
  const response = await emailAnalyzerAgent.call('generateResponse', { analysis });
  console.log('Response:', response);
}
```

--------------------------------

TITLE: Parallel Inventory Checks in TypeScript
DESCRIPTION: An Upstash Workflow example demonstrating parallel execution. It concurrently checks inventory for coffee beans, cups, and milk using `ctx.run` within `Promise.all`. If all ingredients are available, it proceeds to brew coffee and print a receipt.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { checkInventory, brewCoffee, printReceipt } from "@/utils";

export const { POST } = serve(async (ctx) => {
  const [coffeeBeansAvailable, cupsAvailable, milkAvailable] =
    await Promise.all([
      ctx.run("check-coffee-beans", () => checkInventory("coffee-beans")),
      ctx.run("check-cups", () => checkInventory("cups")),

```

--------------------------------

TITLE: Python: Get Image URL with context.run
DESCRIPTION: This Python snippet demonstrates how to retrieve an image URL using the `context.run` function. It defines an asynchronous helper function `_get_image_url` to fetch the URL and then executes it within the workflow context.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
async def _get_image_url() -> str:
    return await get_image_url(image_id)

image_url: str = await context.run("get-image-url", _get_image_url)
```

--------------------------------

TITLE: Bulk Restart Workflow Runs Request (cURL)
DESCRIPTION: Provides an example cURL request for the Upstash Workflow REST API to bulk restart failed workflow runs from the DLQ. It specifies necessary headers for authorization, flow control, and retries.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: curl
CODE:
```
curl -X POST https://qstash.upstash.io/v2/workflows/dlq/restart \
  -H "Authorization: Bearer <token>" \
  -H "Upstash-Flow-Control-Key: custom-key" \
  -H "Upstash-Flow-Control-Value: parallelism=1" \
  -H "Upstash-Retries: 3" \

```

--------------------------------

TITLE: Implement Evaluator-Optimizer Workflow Pattern (JavaScript)
DESCRIPTION: Provides a JavaScript example of the Evaluator-Optimizer pattern in Upstash Workflow. It sets up generator and evaluator agents to iteratively refine content generation based on feedback, aiming to improve output quality through multiple cycles.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";

export const { POST } = serve(async (context) => {
  const model = context.agents.openai('gpt-3.5-turbo');
  
  // Generator agent that generates content
  const generator = context.agents.agent({
    model,
    name: 'generator',
    maxSteps: 1,
    background: 'You are an agent that generates text based on a prompt.',
    tools: {}
  });
  
  // Evaluator agent that evaluates the text and gives corrections
  const evaluator = context.agents.agent({
    model,
    name: 'evaluator',
    maxSteps: 1,
    background: 'You are an agent that evaluates the generated text and provides corrections if needed.',
    tools: {}
  });
  
  let generatedText = '';
  let evaluationResult = '';
  const prompt = "Generate a short explanation of quantum mechanics.";
  let nextPrompt = prompt;
  
  for (let i = 0; i < 3; i++) {
    // Construct prompt for generator:
    // - If there's no evaluation, use the original prompt
    // - If there's an evaluation, provide the prompt, the last generated text, and the evaluator's feedback
    if (evaluationResult && evaluationResult !== "PASS") {
      nextPrompt = `Please revise the answer to the question "${prompt}". Previous answer was: "${generatedText}", which received this feedback: "${evaluationResult}".`;
    }
    
    // Generate content
    const generatedResponse = await context.agents.task({ agent: generator, prompt: nextPrompt }).run();
    generatedText = generatedResponse.text
    
    // Evaluate the generated content
    const evaluationResponse = await context.agents.task({ agent: evaluator, prompt: `Evaluate and provide feedback for the following text: ${generatedText}` }).run();
    evaluationResult = evaluationResponse.text
    
    // If the evaluator accepts the content (i.e., "PASS"), stop
    if (evaluationResult.includes("PASS")) {
      break;
    }
  }
  
  console.log(generatedText);
});

```

--------------------------------

TITLE: Send Trial Ended Email
DESCRIPTION: This workflow sends an email to users whose trial has ended and they have not upgraded. It waits for 2 days after the trial ends and then sends the 'trial ended' email via the Upstash context.

SOURCE: https://upstash.com/docs/workflow/examples/authWebhook

LANGUAGE: TypeScript
CODE:
```
await context.sleep("wait for trial end", 2 * 24 * 60 * 60);
await context.run("send trial end email", async () => {
  await sendEmail(
    email,
    "Your trial has ended. Please upgrade your plan to keep using our platform."
  );
});
```

--------------------------------

TITLE: Cloudflare Workers Integration with Upstash Workflow
DESCRIPTION: This guide explains how to use and deploy Upstash Workflow on Cloudflare Workers. It covers setting up the environment and integrating Upstash Workflow's capabilities within a Cloudflare Workers application.

SOURCE: https://upstash.com/docs/workflow/getstarted

LANGUAGE: TypeScript
CODE:
```
import { Workflow } from '@upstash/workflow';

// Example workflow definition for Cloudflare Workers
const cfWorkflow = new Workflow({
  name: 'my-cloudflare-workflow',
  steps: [
    {
      id: 'worker-step',
      handler: async ({ input }) => {
        console.log('Cloudflare Worker received:', input);
        // Perform actions specific to Cloudflare Workers
        return { message: 'Cloudflare Worker step done' };
      },
    },
  ],
});

// Example of triggering the workflow from a worker route
// export default {
//   async fetch(request) {
//     await cfWorkflow.run({ data: 'trigger data' });
//     return new Response('Workflow triggered!');
//   },
// };
```

--------------------------------

TITLE: Retrieve Image URL (TypeScript)
DESCRIPTION: This snippet shows how to retrieve the URL of an uploaded image within an Upstash Workflow using the `context.run` function. It calls an asynchronous function `getImageUrl` with the image ID.

SOURCE: https://upstash.com/docs/workflow/examples/imageProcessing

LANGUAGE: TypeScript
CODE:
```
const imageUrl = await context.run("get-image-url", async () => {
  return await getImageUrl(imageId)
})
```

--------------------------------

TITLE: Deploy Project to Production with Vercel CLI
DESCRIPTION: Deploys the project to production using the Vercel CLI. This command should be run after configuring necessary environment variables on the Vercel platform.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: shell
CODE:
```
vercel --prod
```

--------------------------------

TITLE: Fetch Workflow Message Logs with cURL
DESCRIPTION: Demonstrates retrieving workflow message logs using `curl`. It sends a GET request to the `/v2/workflows/messageLogs` endpoint, requiring an Authorization header with a Bearer token for authentication.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: sh
CODE:
```
curl https://qstash.upstash.io/v2/workflows/messageLogs \
    -H "Authorization: Bearer <token>"
```

--------------------------------

TITLE: Pause Workflow Execution with context.sleep (TypeScript)
DESCRIPTION: Demonstrates pausing workflow execution for a specified duration using `context.sleep` in TypeScript. The example includes signing in a user and then waiting for one day before sending a welcome email.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";

export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;

  const user = await context.run("sign-in", async () => {
    const signedInUser = await signIn(userData);
    return signedInUser;
  });

  // 👇 Wait for one day (in seconds)
  await context.sleep("wait-until-welcome-email", "1d");

  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});
```

--------------------------------

TITLE: Implement Custom Authorization in Workflow (TypeScript)
DESCRIPTION: Secure your workflow endpoint using a custom authorization mechanism by checking the 'authorization' header. This example demonstrates how to extract and validate a bearer token.

SOURCE: https://upstash.com/docs/workflow/howto/security

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
export const { POST } = serve(
  async (context) => {
    const authHeader = context.headers.get("authorization");
    const bearerToken = authHeader?.split(" ")[1];
    if (!isValid(bearerToken)) {
      console.error("Authentication failed.");
      return;
    }
    // Your workflow steps..
  },
  {
    failureFunction: async () => {
      const authHeader = context.headers.get("authorization");
      const bearerToken = authHeader?.split(" ")[1];
      if (!isValid(bearerToken)) {
        // ...
      }
    },
  }
);

```

--------------------------------

TITLE: Create Express.js Workflow Endpoint
DESCRIPTION: Defines a workflow endpoint in an Express.js application using the Upstash Workflow SDK. This endpoint handles incoming requests, executes defined workflow steps, and logs results.

SOURCE: https://upstash.com/docs/workflow/quickstarts/express

LANGUAGE: javascript
CODE:
```
import { serve } from "@upstash/workflow/express";
import express from 'express';
import { config } from 'dotenv';
config();
const app = express();
app.use(
  express.json()
);
app.post(
  '/workflow',
  serve<{ message: string }>(
    async (context) => {
      const res1 = await context.run("step1", async () => {
        const message = context.requestPayload.message;
        return message;
      })
      await context.run("step2", async () => {
          console.log(res1);
      })
    }
  )
);
app.listen(3000, () => {
  console.log('Server running on port 3000');
});

```

--------------------------------

TITLE: Enable Workflow Verbose Logging (TypeScript)
DESCRIPTION: Enables detailed logging for Upstash Workflows by setting the `verbose` option to `true`. This provides structured log entries for debugging and understanding the execution flow, including endpoint starts and step executions.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
export const { POST } = serve<string>(
  async (context) => { ... },
  {
    verbose: true
  }
);
```

--------------------------------

TITLE: Get Upstash Workflow Logs with JavaScript Client
DESCRIPTION: Shows how to fetch workflow logs using the Upstash Workflow JavaScript client. It includes initializing the client with a token and making a `logs` call with optional parameters for filtering by workflow run ID, count, state, and URL.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" })
const { runs, cursor } = await client.logs({
  // Id of the workflow run to get
  workflowRunId,
  // Number of workflows to get
  count,
  // Workflow state to filter for.
  // One of "RUN_STARTED", "RUN_SUCCESS", "RUN_FAILED", "RUN_CANCELED"
  state,
  // Workflow url to search for. should be an exact match
  workflowUrl,
```

--------------------------------

TITLE: Import Workflow Serve Methods (Python)
DESCRIPTION: Imports `serve` and `async_serve` from `upstash_workflow` for integrating Upstash Workflow with custom Python platforms.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
from upstash_workflow import serve, async_serve
```

--------------------------------

TITLE: Avoid Non-Idempotent Functions Outside context.run (TypeScript)
DESCRIPTION: Shows an incorrect example of calling a non-idempotent function (`getResultFromDb`) outside `context.run`. This can lead to inconsistent behavior or authentication errors if the workflow endpoint is re-executed.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
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

--------------------------------

TITLE: Upstash Workflow Client Operations
DESCRIPTION: Shows how to use the Upstash Workflow client to interact with running workflows. It includes examples for canceling a workflow, notifying waiting workflows with data, and retrieving workflows waiting for a specific event.

SOURCE: https://upstash.com/docs/workflow/sdk/workflow-js

LANGUAGE: typescript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" });

// cancel workflow:
await client.cancel({ workflowRunId: "<WORKFLOW_RUN_ID>" });

// notify workflows:
await client.notify({
  eventId: "my-event-id",
  eventData: "my-data", // data passed to the workflow run
});

// get waiters:
const result = await client.getWaiters({
  eventId: "my-event-id",
});

```

--------------------------------

TITLE: Upstash Workflow Next.js Example
DESCRIPTION: This snippet demonstrates how to implement a workflow endpoint using the Upstash SDK for Next.js. It defines a 'serve' function that takes a request payload and executes asynchronous tasks like 'retrieveEmail' and 'fetchFromLLm' in parallel. The workflow includes a 'sleep' function for pausing execution.

SOURCE: https://upstash.com/docs/workflow/howto/monitor

LANGUAGE: javascript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { retrieveEmail, fetchFromLLm, UserRequest} from "../../../lib/util";
export const { POST } = serve<UserRequest>(
  async (context) => {
    const input = context.requestPayload;
    await context.sleep("sleep", 10);
    const p1 = context.run("retrieveEmail", async () => {
      return retrieveEmail(input.id);
    });
    const p2 = context.run("askllm", async () => {
      return fetchFromLLm(input.question);
    });
    await Promise.all([p1, p2])
  },
);

```

--------------------------------

TITLE: Upstash Workflow: Request Order Processing Step
DESCRIPTION: This code segment represents the first step in an Upstash Workflow, responsible for initiating the order processing. It calls an asynchronous function `requestProcessing` with the `orderId`.

SOURCE: https://upstash.com/docs/workflow/examples/waitForEvent

LANGUAGE: TypeScript
CODE:
```
await context.run("request order processing", async () => {
  await requestProcessing(orderId)
})

```

--------------------------------

TITLE: Pause Workflow Execution with Sleep (TypeScript)
DESCRIPTION: Illustrates how to pause workflow execution for a specified duration using `context.sleep`. This example demonstrates waiting for one day before sending a welcome email after a user signs in.

SOURCE: https://upstash.com/docs/workflow/basics/context

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";
export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;
  const user = await context.run("sign-in", async () => {
    const signedInUser = await signIn(userData);
    return signedInUser;
  });
  // 👇 Wait for one day (in seconds)
  await context.sleep("wait-until-welcome-email", "1d");
  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});

```

--------------------------------

TITLE: Get Waiters of Event (JavaScript)
DESCRIPTION: Retrieves a list of waiters for a specified event ID using the Upstash Workflow client. Requires an event ID as input and returns a list of Waiter objects.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" });
const result = await client.getWaiters({
  eventId: "my-event-id",
});

```

--------------------------------

TITLE: Verify Production Workflow Endpoint
DESCRIPTION: This snippet demonstrates how to verify that your workflow endpoint is accessible after deploying your Next.js application with Upstash Workflow to production. It uses a curl command to make a POST request to your production URL.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: shell
CODE:
```
curl -X POST https://<YOUR-PRODUCTION-URL>/api/workflow
```

--------------------------------

TITLE: TypeScript Orchestrator-Workers Example
DESCRIPTION: This TypeScript code demonstrates the Orchestrator-Workers pattern using Upstash Workflow and Langchain. It sets up an orchestrator that directs three worker agents, each specialized in different physics topics (advanced physics, quantum mechanics, relativity), to answer questions. The orchestrator then synthesizes the responses from these workers into a Q&A format.

SOURCE: https://upstash.com/docs/workflow/agents/patterns/orchestrator-workers

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { WikipediaQueryRun } from "@langchain/community/tools/wikipedia_query_run";
const wikiTool = new WikipediaQueryRun({
  topKResults: 1,
  maxDocContentLength: 500,
})
export const { POST } = serve(async (context) => {
  const model = context.agents.openai('gpt-4o');
  // Worker agents
  const worker1 = context.agents.agent({
    model,
    name: 'worker1',
    tools: { wikiTool },
    maxSteps: 3,
    background: 'You are a worker agent that answers general questions about advanced physics.'
  });
  const worker2 = context.agents.agent({
    model,
    name: 'worker2',
    tools: { wikiTool },
    maxSteps: 3,
    background: 'You are a worker agent that answers questions about quantum mechanics.'
  });
  const worker3 = context.agents.agent({
    model,
    name: 'worker3',
    tools: { wikiTool },
    maxSteps: 3,
    background: 'You are a worker agent that answers questions about relativity.'
  });
  // Synthesizing results
  const task = context.agents.task({
    model,
    prompt: `Create a Q&A for advanced topics in physics`,
    agents: [worker1, worker2, worker3],
    maxSteps: 3,
  })
  const { text } = await task.run();
  console.log(text);
});

```

--------------------------------

TITLE: TypeScript SDK: Triggering Upstash Workflow
DESCRIPTION: This TypeScript code snippet demonstrates how to trigger an Upstash Workflow using the Upstash Workflow SDK. It initializes a `Client` with a token and then uses the `trigger` method to start a workflow. The `trigger` method allows specifying the workflow endpoint URL, an optional request body, headers, a workflow run ID, and the number of retries for the initial request.

SOURCE: https://upstash.com/docs/workflow/getstarted

LANGUAGE: TypeScript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QSTASH_TOKEN>" });
const { workflowRunId } = await client.trigger({
  url: "https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE>",
  body: "hello there!",         // Optional body
  headers: { ... },             // Optional headers
  workflowRunId: "my-workflow", // Optional workflow run ID
  retries: 3                    // Optional retries for the initial request
});

```

--------------------------------

TITLE: Deploying Project to Vercel Production (Bash)
DESCRIPTION: This command deploys the project to Vercel's production environment. It's crucial for making the application publicly accessible, as preview deployments require authentication and may not function as expected without it.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
vercel --prod
```

--------------------------------

TITLE: Python: Avoid Non-Idempotent Functions Outside context.run
DESCRIPTION: Illustrates an incorrect example where a non-idempotent function (`get_result_from_db`) is called outside `context.run`. This can result in inconsistent behavior or authentication errors if the workflow endpoint is re-executed.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
@serve.post("/api/example")
async def example(context: AsyncWorkflowContext[str]) -> None:
    entry_id = context.request_payload["entry_id"]

    # 👇 Problem: Non-idempotent function outside context.run:
    result = await get_result_from_db(entry_id)
    if result.should_return:
        return

    # ...
```

--------------------------------

TITLE: Python: User Creation and Stripe Integration
DESCRIPTION: Handles the creation of a user in the database and Stripe, initiating a trial, and sending a welcome email. It also includes a webhook endpoint for authentication provider events.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
class UserCreatedPayload(TypedDict):
    name: str
    email: str

async def create_user_in_database(name: str, email: str) -> Dict[str, str]:
    print("Creating a user in the database:", name, email)
    return {"userid": "12345"}

async def create_new_user_in_stripe(email: str) -> None:
    print("Creating a user in Stripe for", email)

async def start_trial_in_stripe(email: str) -> None:
    print("Starting a trial of 14 days in Stripe for", email)

async def send_email(email: str, content: str) -> None:
    print("Sending email to", email, content)

@serve.post("/auth-provider-webhook")
async def auth_provider_webhook(
    context: AsyncWorkflowContext[UserCreatedPayload],
) -> None:
    payload = context.request_payload
    name = payload["name"]
    email = payload["email"]

    async def _sync_user() -> str:
        return await create_user_in_database(name, email)

    result = await context.run("sync user", _sync_user)
    userid = result["userid"]

    async def _create_new_user_in_stripe() -> None:

```

--------------------------------

TITLE: Pause Workflow Until Timestamp (TypeScript)
DESCRIPTION: Shows how to pause a workflow until a precise future timestamp using `context.sleepUntil`. This example calculates a date one week from now and pauses the workflow until that exact time before sending an email.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";

export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;

  const user = await context.run("sign-in", async () => {
    return signIn(userData);
  });

  // 👇 Calculate the date for one week from now
  const oneWeekFromNow = new Date();
  oneWeekFromNow.setDate(oneWeekFromNow.getDate() + 7);

  // 👇 Wait until the calculated date
  await context.sleepUntil("wait-for-one-week", oneWeekFromNow);

  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});

```

--------------------------------

TITLE: Configure Flow Control in Trigger Method
DESCRIPTION: This example shows how to set rate limiting for triggering a workflow using the 'flowControl' parameter in the client. It includes the 'key' and 'parallelism' settings to manage concurrent executions when initiating a workflow run.

SOURCE: https://upstash.com/docs/workflow/howto/flow-control

LANGUAGE: javascript
CODE:
```
import { Client } from "@upstash/workflow";
const client = new Client({ token: "<QStash_TOKEN>" });
const { workflowRunId } = await client.trigger({
  url: "https://workflow-endpoint.com",
  body: "hello there!",
  flowControl: { key: "app1", parallelism: 3, rate: 10 }
});

```

--------------------------------

TITLE: List Workflow Steps (JavaScript)
DESCRIPTION: Demonstrates how to initialize the Upstash Workflow SDK and list all steps associated with a specific workflow ID. It includes error handling for the API call.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const workflow = new Workflow('your-workflow-id', 'your-api-key');

workflow.list_steps('your-workflow-id')
  .then(steps => {
    console.log('Workflow steps:', steps);
  })
  .catch(error => {
    console.error('Error listing steps:', error);
  });
```

--------------------------------

TITLE: Send HTTP POST Request to Upstash Workflow (curl)
DESCRIPTION: Triggers an Upstash workflow via HTTP POST using 'curl'. Includes examples for JSON body and custom headers. Does not work for secured endpoints.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: bash
CODE:
```
curl -X POST https://<YOUR_WORKFLOW_ENDPOINT>/<YOUR-WORKFLOW-ROUTE> \
       -H "my-header: foo" \
       -d '{"foo": "bar"}'
```

--------------------------------

TITLE: Trigger Workflow Endpoint with cURL
DESCRIPTION: Makes a POST request to the locally hosted workflow endpoint using cURL to trigger a workflow run. A unique run ID is returned upon successful execution.

SOURCE: https://upstash.com/docs/workflow/quickstarts/vercel-nextjs

LANGUAGE: bash
CODE:
```
curl -X POST https://localhost:3000/api/workflow

```

--------------------------------

TITLE: Fetch Workflow Message Logs (Node.js)
DESCRIPTION: This Node.js snippet uses the `fetch` API to send a GET request to the `/v2/workflows/messageLogs` endpoint. It includes an `Authorization` header with a Bearer token for secure access to the workflow logs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: javascript
CODE:
```
const response = await fetch(
  "https://qstash.upstash.io/v2/workflows/messageLogs",
  {
    headers: {
      Authorization: "Bearer <token>",
    },
  }
);

```

--------------------------------

TITLE: Workflow Message Logs JSON Response Example
DESCRIPTION: A sample JSON response from the workflow message logs API, indicating a successful event (HTTP 200 OK). It includes pagination cursor and details about a workflow run, such as state, IDs, and timestamps.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: json
CODE:
```
{
    "cursor": "",
    "events": [
      {
        "time": 1738788333107,
        "state": "CREATED",
        "workflowRunId": "wfr_6MXE3GfddpBMWJM7s5WSRPqwcFm8",
        "workflowUrl": "http://my-workflow-server.com/workflowEndpoint",
        "workflowCreatedAt": 1738788333105,
        "stepInfo": {
          "stepName": "init",
          "stepType": "Initial",
          "callType": "step",
          "messageId": "msg_2KxeAKGVEjwDjNK1TVPormoRf7shRyNBpPThVbpvkuZNqri4cXp5nwSajNzAs6UWakvbco3qEPvtjQU3qxqjWarm2kisK",
          "concurrent": 1,
          "createdAt": 1738788333106
        },
        "nextDeliveryTime": 1738788333106
      },
      {

}
```

--------------------------------

TITLE: Send Welcome Email in Workflow
DESCRIPTION: This TypeScript snippet represents the initial step in a customer onboarding workflow, where a welcome email is sent to a newly signed-up user. It uses `context.run` to manage the task and `sendEmail` to dispatch the email.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
await context.run("new-signup", async () => {
  await sendEmail("Welcome to the platform", email)
})
```

--------------------------------

TITLE: Pause Workflow Until Timestamp (TypeScript)
DESCRIPTION: Demonstrates using `context.sleepUntil` to pause workflow execution until a specific timestamp. This example calculates a date one week from now and waits until that time to send a welcome email.

SOURCE: https://upstash.com/docs/workflow/basics/context

LANGUAGE: TypeScript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { signIn, sendEmail } from "@/utils/onboarding-utils";
export const { POST } = serve<User>(async (context) => {
  const userData = context.requestPayload;
  const user = await context.run("sign-in", async () => {
    return signIn(userData);
  });
  // 👇 Calculate the date for one week from now
  const oneWeekFromNow = new Date();
  oneWeekFromNow.setDate(oneWeekFromNow.getDate() + 7);
  // 👇 Wait until the calculated date
  await context.sleepUntil("wait-for-one-week", oneWeekFromNow);
  await context.run("send-welcome-email", async () => {
    return sendEmail(user.name, user.email);
  });
});

```

--------------------------------

TITLE: TypeScript: Use Custom OpenAI Client for Text Generation
DESCRIPTION: Shows how to use a custom-created OpenAI client within an Upstash Workflow endpoint to generate text based on a provided prompt. It includes running steps for getting the prompt and logging the generated text, with error handling for WorkflowAbort.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: typescript
CODE:
```
import { serve } from "@upstash/workflow/nextjs";
import { WorkflowAbort } from '@upstash/workflow';
import { generateText, ToolExecutionError } from 'ai';
import { createWorkflowOpenAI } from './model';

export const { POST } = serve<{ prompt: string }>(async (context) => {
  const openai = createWorkflowOpenAI(context);
  // Important: Must have a step before generateText
  const prompt = await context.run("get prompt", async () => {
    return context.requestPayload.prompt;
  });
  try {
    const result = await generateText({
      model: openai('gpt-3.5-turbo'),
      maxTokens: 2048,
      prompt,
    });
    await context.run("text", () => {
      console.log(`TEXT: ${result.text}`);
      return result.text;
    });
  } catch (error) {
    if (error instanceof ToolExecutionError && error.cause instanceof WorkflowAbort) {
      throw error.cause;
    } else {
      throw error;
    }
  }
});

```

--------------------------------

TITLE: Bash: Invoke Workflow Endpoint via cURL
DESCRIPTION: Provides a cURL command example to trigger a workflow exposed via `serveMany` at a specific route. The route name is inferred from the key provided when defining workflows within `serveMany`.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: Bash
CODE:
```
curl -X POST https://your-app/serve-many/workflow-one-route
```

--------------------------------

TITLE: Restart Failed Workflows from DLQ
DESCRIPTION: Restart a failed workflow run from the beginning, using its DLQ ID. Similar to resume, it allows setting flow control and retry counts, but starts execution from the initial payload.

SOURCE: https://upstash.com/docs/workflow/basics/client

LANGUAGE: javascript
CODE:
```
const { messages } = await client.dlq.list();
const response = await client.dlq.restart({
  dlqId: messages[0].dlqId, // Use the dlqId from the message
  flowControl: {
    key: "my-flow-control-key",
    value: "my-flow-control-value",
  },
  retries: 3,
});
```

--------------------------------

TITLE: Fetch Workflow Message Logs (Python)
DESCRIPTION: This Python snippet utilizes the `requests` library to perform a GET request to the `/v2/workflows/messageLogs` endpoint. It sets the `Authorization` header with a Bearer token to authenticate the request and retrieve workflow logs.

SOURCE: https://upstash.com/docs/workflow/llms-txt

LANGUAGE: python
CODE:
```
import requests
headers = {
    'Authorization': 'Bearer <token>',
}

response = requests.get(
  'https://qstash.upstash.io/v2/workflows/messageLogs',
  headers=headers
)

```
```

