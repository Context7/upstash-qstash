Skip to content
You signed in with another tab or window. Reload to refresh your session. You signed out in another tab or window. Reload to refresh your session. You switched accounts on another tab or window. Reload to refresh your session. Dismiss alert
{{ message }}
upstash  / **workflow-py ** Public
  * Notifications  You must be signed in to change notification settings
  * Fork 3
  * Star  19


Durable, Reliable and Performant Serverless Functions 
### License
MIT license 
19 stars  3 forks  Branches Tags Activity
Star 
Notifications  You must be signed in to change notification settings
# upstash/workflow-py
master
**9** Branches**6** Tags
Go to file
Code
Open more actions menu
## Folders and files
Name| Name| Last commit message| Last commit date  
---|---|---|---  
## Latest commit
CahidArdaDX-1914: Ignore render and cf loop headers (#34)Open commit detailssuccessJun 2, 202543360f0 · Jun 2, 2025
## History
121 CommitsOpen commit details  
.github/workflows| .github/workflows| feat: add release workflow| Jan 14, 2025  
examples| examples| fix: move nextjs-flask example from pnpm to npm (#28)| Jan 23, 2025  
tests| tests| DX-1791: Add Failure Function (#32)| Apr 15, 2025  
upstash_workflow| upstash_workflow| DX-1914: Ignore render and cf loop headers (#34)| Jun 2, 2025  
.env.example| .env.example| docs: add more detailed environment setup descriptions| Jan 15, 2025  
.gitignore| .gitignore| feat: formatting with ruff| Dec 6, 2024  
LICENSE| LICENSE| Initial commit| Nov 4, 2024  
README.md| README.md| docs: add more detailed environment setup descriptions| Jan 15, 2025  
pyproject.toml| pyproject.toml| DX-1914: Ignore render and cf loop headers (#34)| Jun 2, 2025  
View all files  
## Repository files navigation
# Upstash Workflow SDK
**Upstash Workflow** lets you write durable, reliable and performant serverless functions. Get delivery guarantees, automatic retries on failure, scheduling and more without managing any infrastructure.
See the documentation for more details
## Quick Start
Here, we will briefly showcase how you can get started with Upstash Workflow using FastAPI.
Alternatively, you can check our quickstarts for different frameworks, including FastAPI and Next.js & FastAPI.
### Install
First, create a new directory and set up a virtual environment:
```
python -m venv venv
source venv/bin/activate
```

Then, install the required packages:
```
pip install fastapi uvicorn upstash-workflow
```

### Get QStash token
Go to Upstash Console and copy the `QSTASH_TOKEN`, set it in the `.env` file.
```
export QSTASH_TOKEN=
```

### Define a Workflow Endpoint
To declare workflow endpoints, use the `@serve.post` decorator. Save the following code to `main.py`:
```
from fastapi import FastAPI
from upstash_workflow.fastapi import Serve
from upstash_workflow import AsyncWorkflowContext

app = FastAPI()
serve = Serve(app)

# mock function
def some_work(input: str) -> str:
    return f"processed '{input}'"

# serve endpoint which expects a string payload:
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

In the example, you can see that steps are declared through the `context` object.
The kinds of steps which are available are:
  * `context.run`: execute a function
  * `context.sleep`: sleep for some time
  * `context.sleep_until`: sleep until some timestamp
  * `context.call`: make a third party call without consuming any runtime


You can learn more about these methods from our documentation.
### Run the Server
Upstash Workflow needs a public URL to orchestrate the workflow. Check out our Local Development guide to learn how to set up a local tunnel.
Create the tunnel and set the `UPSTASH_WORKFLOW_URL` environment variable in the `.env` file with the public URL:
```
ngrok http localhost:8000
```

```
export UPSTASH_WORKFLOW_URL=
```

Then, set the environment variables:
```
source .env
```

Finally, run the server:
```
uvicorn main:app --reload
```

FastAPI server will be running at `localhost:8000`.
## Contributing
### Development
  1. Clone the repository
  2. Install Poetry
  3. Install dependencies with `poetry install`
  4. Create a .env file with `cp .env.example .env` and fill in the environment variables
  5. Run tests with `poetry run pytest`
  6. Format with `poetry run ruff format .`
  7. Check with `poetry run ruff check .`
  8. Type check with `poetry run mypy --show-error-codes .`


## About
Durable, Reliable and Performant Serverless Functions 
### Topics
workflow  upstash  qstash 
### Resources
Readme 
### License
MIT license 
###  Uh oh! 
There was an error while loading. Please reload this page.
Activity
Custom properties
### Stars
**19** stars
### Watchers
**6** watching
### Forks
**3** forks
Report repository 
##  Releases 6
Release v0.1.2 Latest 
Jun 2, 2025
+ 5 releases
##  Packages 0
No packages published   

###  Uh oh! 
There was an error while loading. Please reload this page.
##  Contributors 2
  * **yunusemreozdemir** Yunus Emre Özdemir
  * **CahidArda** Cahid Arda Öz


## Languages
  * Python 100.0%


You can’t perform that action at this time. 
