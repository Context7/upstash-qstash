# Cloudflare Workers

This is a step by step guide on how to receive webhooks from QStash in your
Cloudflare Worker.

### Project Setup

We will use **C3 (create-cloudflare-cli)** command-line tool to create our functions. You can open a new terminal window and run C3 using the prompt below.

<CodeGroup>
  ```shell npm theme={"system"}
  npm create cloudflare@latest
  ```

  ```shell yarn theme={"system"}
  yarn create cloudflare@latest
  ```
</CodeGroup>

This will install the `create-cloudflare` package, and lead you through setup. C3 will also install Wrangler in projects by default, which helps us testing and deploying the projects.

```text  theme={"system"}
➜  npm create cloudflare@latest
Need to install the following packages:
  create-cloudflare@2.1.0
Ok to proceed? (y) y

using create-cloudflare version 2.1.0

╭ Create an application with Cloudflare Step 1 of 3
│
├ In which directory do you want to create your application?
│ dir ./cloudflare_starter
│
├ What type of application do you want to create?
│ type "Hello World" Worker
│
├ Do you want to use TypeScript?
│ yes typescript
│
├ Copying files from "hello-world" template
│
├ Do you want to use TypeScript?
│ yes typescript
│
├ Retrieving current workerd compatibility date
│ compatibility date 2023-08-07
│
├ Do you want to use git for version control?
│ yes git
│
╰ Application created
```

We will also install the **Upstash QStash library**.

```bash  theme={"system"}
npm install @upstash/qstash
```

### 3. Use QStash in your handler

First we import the library:

```ts src/index.ts theme={"system"}
import { Receiver } from "@upstash/qstash"
```

Then we adjust the `Env` interface to include the `QSTASH_CURRENT_SIGNING_KEY`
and `QSTASH_NEXT_SIGNING_KEY` environment variables.

```ts src/index.ts theme={"system"}
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string
  QSTASH_NEXT_SIGNING_KEY: string
}
```

And then we validate the signature in the `handler` function.

First we create a new receiver and provide it with the signing keys.

```ts src/index.ts theme={"system"}
const receiver = new Receiver({
  currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
  nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
})
```

Then we verify the signature.

```ts src/index.ts theme={"system"}
const body = await request.text()

const isValid = await receiver.verify({
  signature: request.headers.get("Upstash-Signature")!,
  body,
})
```

The entire file looks like this now:

```ts src/index.ts theme={"system"}
import { Receiver } from "@upstash/qstash"
export interface Env {
  QSTASH_CURRENT_SIGNING_KEY: string
  QSTASH_NEXT_SIGNING_KEY: string
}

export default {
  async fetch(request: Request, env: Env, ctx: ExecutionContext): Promise<Response> {
    const c = new Receiver({
      currentSigningKey: env.QSTASH_CURRENT_SIGNING_KEY,
      nextSigningKey: env.QSTASH_NEXT_SIGNING_KEY,
    })

    const body = await request.text()

    const isValid = await c
      .verify({
        signature: request.headers.get("Upstash-Signature")!,
        body,
      })
      .catch((err) => {
        console.error(err)
        return false
      })

    if (!isValid) {
      return new Response("Invalid signature", { status: 401 })
    }

    // signature is valid

    return new Response("Hello World!")
  },
}
```

### Configure Credentials

There are two methods for setting up the credentials for QStash. The recommended way is to use Cloudflare Upstash Integration. Alternatively, you can add the credentials manually.

#### Using the Cloudflare Integration

Access to the [Cloudflare Dashboard](https://dash.cloudflare.com) and login with the same account that you've used while setting up the Worker application. Then, navigate to **Workers & Pages > Overview** section on the sidebar. Here, you'll find your application listed.

<Frame>
  <img src="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=1202ef160c0747f858334710787f0dbf" data-og-width="1306" width="1306" data-og-height="930" height="930" data-path="img/cloudflare-integration/overview.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=280&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=aed1f88295c4d5c35457c32d8c155ec2 280w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=560&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=6befe5962800f89179cc9453b6346307 560w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=840&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=e8bd595b7bdc053e325306b84f819907 840w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=1100&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=c9cca8dad7609ea93ae5713f753c1b59 1100w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=1650&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=dde2a89e892994c7dc862b7099f0481e 1650w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/overview.png?w=2500&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=f9d20064c5798e64cdb13a84ceb53df0 2500w" />
</Frame>

Clicking on the application will direct you to the application details page, where you can perform the integration process. Switch to the **Settings** tab in the application details, and proceed to **Integrations** section. You will see various Worker integrations listed. To proceed, click the **Add Integration** button associated with the QStash.

<Frame>
  <img src="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=69c648aa2a83f3af9e347de0c031cba7" data-og-width="1303" width="1303" data-og-height="925" height="925" data-path="img/cloudflare-integration/qstash-add-integration.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=280&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=26012983abe8c68e153b7dd769d73158 280w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=560&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=001295f4dc194b91f512931495679887 560w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=840&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=66ba618b23be5a1b5aa6dfde87425076 840w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=1100&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=0506c769344d99d98ca693ae39299f93 1100w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=1650&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=67acc31c6886371839f3c9f0d449aab7 1650w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-add-integration.png?w=2500&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=5fdbb245665c1095b43d21716cfc37c9 2500w" />
</Frame>

On the Integration page, connect to your Upstash account. Then, select the related database from the dropdown menu. Finalize the process by pressing Save button.

<Frame>
  <img src="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=fd4127c9a8ba02473ecec823db2c486d" data-og-width="1303" width="1303" data-og-height="929" height="929" data-path="img/cloudflare-integration/qstash-credentials.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=280&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=a24a1f186f385ed21d019a3a2721ac42 280w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=560&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=594c5e240bf67a6a463dc9c45c41d208 560w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=840&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=5902bea42a60d3e06ee298ac465cf77e 840w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=1100&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=afdb96afc8edbd53b169709fac63712b 1100w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=1650&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=de7467eebc9f105ea0400714bd2c00e0 1650w, https://mintcdn.com/upstash/ZVIIe-nWA4-ORRYS/img/cloudflare-integration/qstash-credentials.png?w=2500&fit=max&auto=format&n=ZVIIe-nWA4-ORRYS&q=85&s=8e97e3ecb17bfdb19b86c8c8b462f233 2500w" />
</Frame>

#### Setting up Manually

Navigate to [Upstash Console](https://console.upstash.com) and copy/paste your QStash credentials to `wrangler.toml` as below.

```yaml  theme={"system"}
[vars]
QSTASH_URL="REPLACE_HERE"
QSTASH_TOKEN="REPLACE_HERE"
QSTASH_CURRENT_SIGNING_KEY="REPLACE_HERE"
QSTASH_NEXT_SIGNING_KEY="REPLACE_HERE"
```

### Test and Deploy

You can test the function locally with `npx wrangler dev`

Deploy your function to Cloudflare with `npx wrangler deploy`

The endpoint of the function will be provided to you, once the deployment is done.

### Publish a message

Open a different terminal and publish a message to QStash. Note the destination
url is the same that was printed in the previous deploy step.

```bash  theme={"system"}
curl --request POST "https://qstash.upstash.io/v2/publish/https://cloudflare-workers.upstash.workers.dev" \
     -H "Authorization: Bearer <QSTASH_TOKEN>" \
     -H "Content-Type: application/json" \
     -d "{ \"hello\": \"world\"}"
```

In the logs you should see something like this:

```bash  theme={"system"}
$ npx wrangler tail

⛅️ wrangler 2.0.17
--------------------
Retrieving cached values for account from node_modules/.cache/wrangler
Successfully created tail, expires at 2022-07-11T21:11:36Z
Connected to cloudflare-workers, waiting for logs...
POST https://cloudflare-workers.upstash.workers.dev/ - Ok @ 7/11/2022, 5:13:19 PM
  (log) The signature was valid
```

## Next Steps

That's it, you have successfully created a secure Cloudflare Worker, that
receives and verifies incoming webhooks from qstash.

Learn more about publishing a message to qstash [here](/qstash/howto/publishing).

You can find the source code [here](https://github.com/upstash/qstash-examples/tree/main/cloudflare-workers).
