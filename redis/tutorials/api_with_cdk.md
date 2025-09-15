On this page
## GitHub Repository
You can find the project source code on GitHub.
In this tutorial, we will implement a Serverless API using AWS Lambda and we will deploy it using AWS CDK. We will use Typescript as the CDK language. It will be a view counter where we keep the state in Redis.
### 
​
What is AWS CDK?
AWS CDK is an interesting project which allows you to provision and deploy AWS infrastructure with code. Currently TypeScript, JavaScript, Python, Java, C#/.Net and Go are supported. You can compare AWS CDK with following technologies:
  * AWS CloudFormation
  * AWS SAM
  * Serverless Framework

The above projects allows you to set up the infrastructure with configuration files (yaml, json) while with AWS CDK, you set up the resources with code. For more information about CDK see the related AWS Docs.
### 
​
Prerequisites
  * Complete all steps in Getting started with the AWS CDK


### 
​
Project Setup
Create and navigate to a directory named `counter-cdk`. The CDK CLI uses this directory name to name things in your CDK code, so if you decide to use a different name, don’t forget to make the appropriate changes when applying this tutorial.
Copy
Ask AI
```
mkdir counter-cdk && cd counter-cdk

```

Initialize a new CDK project.
Copy
Ask AI
```
cdk init app --language typescript

```

Install `@upstash/redis`.
Copy
Ask AI
```
npm install @upstash/redis

```

### 
​
Counter Function Setup
Create `/api/counter.ts`.
/api/counter.ts
Copy
Ask AI
```
import { Redis } from '@upstash/redis';

const redis = Redis.fromEnv();

export const handler = async function() {
    const count = await redis.incr("counter");
    return {
        statusCode: 200,
        body: JSON.stringify('Counter: ' + count),
    };
};

```

### 
​
Counter Stack Setup
Update `/lib/counter-cdk-stack.ts`.
/lib/counter-cdk-stack.ts
Copy
Ask AI
```
import * as cdk from 'aws-cdk-lib';
import { Construct } from 'constructs';
import * as lambda from 'aws-cdk-lib/aws-lambda';
import * as nodejs from 'aws-cdk-lib/aws-lambda-nodejs';

export class CounterCdkStack extends cdk.Stack {
  constructor(scope: Construct, id: string, props?: cdk.StackProps) {
    super(scope, id, props);

    const counterFunction = new nodejs.NodejsFunction(this, 'CounterFunction', {
      entry: 'api/counter.ts',
      handler: 'handler',
      runtime: lambda.Runtime.NODEJS_20_X,
      environment: {
        UPSTASH_REDIS_REST_URL: process.env.UPSTASH_REDIS_REST_URL || '',
        UPSTASH_REDIS_REST_TOKEN: process.env.UPSTASH_REDIS_REST_TOKEN || '',
      },
      bundling: {
        format: nodejs.OutputFormat.ESM,
        target: "node20",
        nodeModules: ['@upstash/redis'],
      },
    });

    const counterFunctionUrl = counterFunction.addFunctionUrl({
      authType: lambda.FunctionUrlAuthType.NONE,
    });

    new cdk.CfnOutput(this, "counterFunctionUrlOutput", {
      value: counterFunctionUrl.url,
    })
  }
}

```

### 
​
Database Setup
Create a Redis database using Upstash Console or Upstash CLI and export `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN` to your environment.
Copy
Ask AI
```
export UPSTASH_REDIS_REST_URL=<YOUR_URL>
export UPSTASH_REDIS_REST_TOKEN=<YOUR_TOKEN>

```

### 
​
Deploy
Run in the top folder:
Copy
Ask AI
```
cdk synth
cdk bootstrap
cdk deploy

```

Visit the output URL.
Was this page helpful?
YesNo
Suggest editsRaise issue
Building a URL Shortener with RedisAutocomplete API with Serverless Redis
Assistant
Responses are generated using AI and may contain mistakes.
