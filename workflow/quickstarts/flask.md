On this page
## GitHub Repository
You can find the project source code on GitHub.
This guide provides detailed, step-by-step instructions on how to use Upstash Workflow with Flask. You can also explore the source code for a detailed, end-to-end example and best practices.
## 
​
Prerequisites
  1. An Upstash QStash API key.
  2. Python and pip installed.

If you haven’t obtained your QStash API key yet, you can do so by signing up for an Upstash account and navigating to your QStash dashboard.
## 
​
Step 1: Installation
First, create a new directory and set up a virtual environment:
Copy
Ask AI
```
python -m venv venv
source venv/bin/activate

```

Then, install the Workflow SDK and Flask:
Copy
Ask AI
```
pip install fastapi uvicorn upstash-workflow

```

## 
​
Step 2: Configure Environment Variables
Create a `.env` file in your project root and add your QStash token. This token is used to authenticate your application with the QStash service.
Terminal
Copy
Ask AI
```
touch .env

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

Once the command runs successfully, you’ll see `QSTASH_URL` and `QSTASH_TOKEN` values in the console. Add these values to your `.env` file:
.env
Copy
Ask AI
```
export QSTASH_URL="http://127.0.0.1:8080"
export QSTASH_TOKEN=<QSTASH_TOKEN>

```

This approach allows you to test workflows locally without affecting your billing. However, runs won’t be logged in the Upstash Console.
### 
​
Option 2: Local Tunnel
Alternatively, you can set up a local tunnel. For this option:
  1. Copy the `QSTASH_TOKEN` from the Upstash Console.
  2. Update your `.env` file with the following:


.env
Copy
Ask AI
```
export QSTASH_TOKEN="***"
export UPSTASH_WORKFLOW_URL=<UPSTASH_WORKFLOW_URL>

```

  * Replace `***` with your actual QStash token.
  * Set `UPSTASH_WORKFLOW_URL` to the public URL provided by your local tunnel.

Here’s where you can find your QStash token:
Using a local tunnel connects your endpoint to the production QStash, enabling you to view workflow logs in the Upstash Console.
## 
​
Step 3: Create a Workflow Endpoint
A workflow endpoint allows you to define a set of steps that, together, make up a workflow. Each step contains a piece of business logic that is automatically retried on failure, with easy monitoring via our visual workflow dashboard. To define a workflow endpoint in a Flask project, create a `main.py` file that contains your workflow:
  * Example
  * Sleep
  * Call
  * Auth


main.py
Copy
Ask AI
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

## 
​
Step 4: Run the Workflow Endpoint
Don’t forget to source your environment file to set your environment variables:
Terminal
Copy
Ask AI
```
source .env

```

After setting your live URL as the environment variable or `base_url` option, trigger your workflow by first starting your Flask app:
Terminal
Copy
Ask AI
```
flask --app main run -p 8000

```

and then making a POST request to your workflow endpoint. For each workflow run, a unique workflow run ID is returned:
Terminal
Copy
Ask AI
```
curl -X POST https://localhost:8000/api/workflow

# result: {"workflowRunId":"wfr_xxxxxx"}

```

See the documentation on starting a workflow for other ways you can start your workflow.
If you are using a local tunnel, you can use this ID to track the workflow run and see its status in your QStash workflow dashboard. All steps are listed with their statuses, headers, and body for a detailed overview of your workflow from start to finish. Click on a step to see its detailed logs.
## 
​
Next Steps
  1. Learn how to protect your workflow endpoint from unauthorized access by securing your workflow endpoint.
  2. Explore our the source code for a detailed, end-to-end example and best practices.
  3. For setting up and testing your workflows in a local environment, check out our local development guide.


Was this page helpful?
YesNo
Suggest editsRaise issue
Next.js & FastAPINext.js & Flask
Assistant
Responses are generated using AI and may contain mistakes.
