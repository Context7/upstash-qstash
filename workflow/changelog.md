On this page
Qstash changelogs are here
​
August 2025
  * **TypeScript SDK (`qstash-js`):**
    * Added `retryDelay` option to dynamicaly program the retry duration. It can be configured on trigger , context.call or serve


​
July 2025
  * **TypeScript SDK (`qstash-js`):**
    * Restart/Resume for DLQ is added to allow more options to handle failed runs. See here
    * Added `WorkflowNonRetryableError` to fail a workflow without causing any retries. See here
    * For additional bug fixes, see the full changelog here.


​
June 2025
  * **TypeScript SDK (`workflow-js`):**
    * Added `useFailureFunction` and `failureFunction` to `client.trigger`. See here.
    * Added batch triggering support to `client.trigger`. See here.
    * For additional bug fixes, see the release notes here.
  * **Python SDK (`workflow-py`):**
    * Failure function is implemented. This feature enables to act on a failure of a workflow on the code. See docs here
    * For other bug fixes, see the full changelog here.
  * **Console:**
    * A major redesign is coming next month to improve Workflow usability.
  * **Workflow Server:**
    * An issue causing Workflows not usable with `CloudFront` is fixed.


​
May 2025
  * **TypeScript SDK (`workflow-js`):**
    * Added a `workflow` parameter to `context.call`, enabling type-safe workflow calls. See here.
    * Enabled passing `context.call` settings when defining an Agent. See here.
    * Added `delay` support to `client.trigger`. See here.
    * Introduced `period` and improved `rate` support in flow control. See here.  
Previously, `period` was fixed at 1 second. For example, `rate: 3 period: 1d` throttles publishes to 3 per day.
    * For additional bug fixes, see the release notes here.
  * **Workflow Server:**
    * Added support for custom `period` in flow control, allowing users to set a period of up to 1 week.  
Previously, `period` was fixed at 1 second. For example, `rate: 3 period: 1d` throttles publishes to 3 per day.
    * Implemented **Workflow Resume** and **Restart** features (SDK and Console support in progress): 
      * **Resume** allows users to retry a workflow run from the point it stopped.
      * **Restart** allows users to retry a workflow run from the beginning.
  * **Console:**
    * A major redesign is coming to improve Workflow usability.


​
April 2025
  * **Python SDK (`workflow-py`):**
    * Minor bug fixes.  
See the full changelog here.
  * **Workflow Server:**
    * Prevented intermediate Workflow calls from failing due to request/message quota limits.
    * Fixed handling of `RUN_STARTED` so that it correctly returns unfinished Workflow Runs as documented.  
Previously, some Workflow Runs could be skipped if internal state was logged after `RUN_STARTED`.
    * Applied several performance optimizations.


​
March 2025
  * **TypeScript SDK (`workflow-js`):**
    * Added `onError` support to `serve` by the community. See here.
    * Enabled support for all fetch-compatible models in Agents. See more details here.
    * For additional bug fixes, see the full changelog here.


​
February 2025
  * **TypeScript SDK (`workflow-js`):**
    * Fixed a Unicode issue in `context.call` where binary responses from endpoints could break. See here.
    * Introduced `WorkflowTool`, allowing Workflow Agents to define multi-step workflows as a tool. See here.
    * Added `context.invoke` to call one workflow from another with full type-safety. See the guide here.
    * Introduced flow control parameters to limit the rate or concurrency of workflow runs. Learn more here.
    * For additional bug fixes, see the full changelog here.
  * **Workflow Server:**
    * Added RateLimit and Parallelism controls to manage the frequency and concurrency of workflow runs. Learn more here.


​
January 2025
  * **TypeScript SDK (`workflow-js`):**
    * Added the Agents API to workflows. You can now create AI agents to run workflows on your own infrastructure with all the benefits of workflows: reduced environment costs, fault tolerance, and scalability. Learn more about agents here.
    * For other bug fixes, see the full changelog here.
  * **Python SDK (workflow-py):**
    * Released `workflow-py`.
  * **Local Development Server:**
    * The local development server is now available for public use. This server allows you to test your workflows locally. Learn more about the local development server here.
  * **Console:**
    * Separated Workflow and QStash consoles for a better user experience.
    * Separated their DLQ messages as well.
  * **Workflow Server:**
    * The core team focused on RateLimit and Parallelism features. These features are ready on the server and will be announced next month after the documentation and SDKs are completed.


​
December 2024
  * **TypeScript SDK (`workflow-js`):**
    * Introduced third-party integrations, starting with Anthropic, Resend, and OpenAI. These integrations are automatically offloaded to workflows, ensuring long-running calls do not consume user environment time. See the related documentation here.
    * Added a `timeout` parameter to `context.call`. Learn more in the documentation.
    * Improved support for workflows in Express and SvelteKit by adding the `useJSONContent` option.
    * Resolved loop detection issues on Cloudflare and Render.
    * Full changelog, including all fixes, is available here.
  * **Workflow Server:**
    * Added the `WorkflowCreatedAt` filter for Dead Letter Queue (DLQ) and Events.
    * Prepared the local development server for public release (coming soon).
    * Enhanced `context.SleepUntil` to support float values.
    * Increased the event retention period from 10,000 events to up to 14 days. Learn more on the Pricing page.


​
November 2024
  * **Python SDK (workflow-py):**
    * Began development of the Python SDK.
  * **TypeScript SDK (workflow-js):**
    * Added support for string durations (e.g., `1d`, `30s`) in `context.sleep` and `context.waitForEvent`.
    * Introduced integrations for Astro and Express.
    * Added `client.trigger`, enabling workflows to start and return the workflow run ID. See the documentation.
    * Added a retry option for `context.call`. See the documentation.
    * Introduced a lazy fetch feature to support longer and larger workflows on resource-limited platforms.
    * Added `context.cancel` to cancel the current workflow. See the documentation.
    * Full changelog, including fixes, is available here.
  * **Workflow Server:**
    * Added bulk cancel functionality for workflow runs. See the REST API.
    * Introduced content-based deduplication for workflows and retry-until-success functionality. This will allow workflows to be used in areas with unstable network connection.


​
October 2024
  * Optimized the console by trimming event bodies, reducing resource usage and enabling efficient querying of events with large payloads.
  * Began development on a new architecture to deliver faster event processing on the server.
  * Added Wait Notify feature.


​
September 2024
  * Bug fixes and internal logging improvements.


​
August 2024
  * Released Upstash Workflow.


Was this page helpful?
YesNo
Suggest editsRaise issue
VercelRoadmap
Assistant
Responses are generated using AI and may contain mistakes.
