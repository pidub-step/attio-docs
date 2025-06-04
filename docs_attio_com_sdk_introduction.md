---
title: Introduction to the App SDK - Attio Docs
url: https://docs.attio.com/sdk/introduction
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Introduction to the App SDK - Attio Docs

**Source:** [https://docs.attio.com/sdk/introduction](https://docs.attio.com/sdk/introduction)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Using the App SDK
Introduction to the App SDK
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Using the App SDK
  * [Introduction to the App SDK](https://docs.attio.com/sdk/introduction)
  * [Creating an app](https://docs.attio.com/sdk/creating-an-app)
  * [Sharing your app](https://docs.attio.com/sdk/sharing-your-app)
  * [Shipping updates](https://docs.attio.com/sdk/shipping-updates)
  * [Design guidelines](https://docs.attio.com/sdk/design-guidelines)


##### Actions
  * [RecordAction](https://docs.attio.com/sdk/actions/record-action)
  * [BulkRecordAction](https://docs.attio.com/sdk/actions/bulk-record-action)


##### Notifications
  * [Notifying the user](https://docs.attio.com/sdk/notifications/notifications)
  * [alert()](https://docs.attio.com/sdk/notifications/alert)
  * [confirm()](https://docs.attio.com/sdk/notifications/confirm)
  * [showToast()](https://docs.attio.com/sdk/notifications/show-toast)


##### Dialogs
  * [showDialog()](https://docs.attio.com/sdk/dialogs/show-dialog)


##### Components
  * [<Button />](https://docs.attio.com/sdk/components/button)
  * [<Checkbox />](https://docs.attio.com/sdk/components/checkbox)
  * [<Column />](https://docs.attio.com/sdk/components/column)
  * [<Combobox />](https://docs.attio.com/sdk/components/combobox)
  * [<Form />](https://docs.attio.com/sdk/components/form)
  * [<Link />](https://docs.attio.com/sdk/components/link)
  * [<NumberInput />](https://docs.attio.com/sdk/components/number-input)
  * [<Row />](https://docs.attio.com/sdk/components/row)
  * [<Section />](https://docs.attio.com/sdk/components/section)
  * [<SubmitButton />](https://docs.attio.com/sdk/components/submit-button)
  * [<TextBlock />](https://docs.attio.com/sdk/components/text-block)
  * [<TextInput />](https://docs.attio.com/sdk/components/text-input)
  * [<Toggle />](https://docs.attio.com/sdk/components/toggle)
  * [<Typography />](https://docs.attio.com/sdk/components/typography)
  * [<WithState />](https://docs.attio.com/sdk/components/with-state)


##### Forms
  * [Form schema](https://docs.attio.com/sdk/form-schema)


##### GraphQL
  * [Using GraphQL](https://docs.attio.com/sdk/graphql/graphql)
  * [runQuery()](https://docs.attio.com/sdk/graphql/run-query)


##### Hooks
  * [useAsyncCache()](https://docs.attio.com/sdk/hooks/use-async-cache)
  * [useForm()](https://docs.attio.com/sdk/hooks/use-form)
  * [useQuery()](https://docs.attio.com/sdk/hooks/use-query)


##### Server
  * [Server functions](https://docs.attio.com/sdk/server/server-functions)
  * [attioFetch()](https://docs.attio.com/sdk/server/attio-fetch)
  * Connections
  * Events
  * Webhooks


##### System
  * [platform](https://docs.attio.com/sdk/system/platform)


Using the App SDK
# Introduction to the App SDK
An overview of the functionality provided by the App SDK
This only covers apps from the perspective of the App SDK, apps can also use the REST API
**An app is a way to extend the existing functionality of Attio** , typically by pulling data into Attio from a third party source, or of extracting data out of Attio to use with some tool. Apps can provide custom UI _directly inside of Attio’s user interface_ using custom React components.
Specifically you can add custom actions (buttons) to record pages inside Attio. When clicked you can trigger a server function, and/or display a modal to users with custom UI to complete a form or view information.
Let’s look at an example.
Let’s imagine a hypothetical service called **Acme Lead Checker** (ALC) that has an API to receive potential leads, an AI agent initiates an SMS chat with the lead, and then needs to update the lead’s record in Attio about how interested the person is in whatever product we are selling.
Our app needs:
  * A button inside Attio that will call a server function
  * A server function to actually send the data to ALC
  * A webhook to receive the lead status back from ALC sometime in the future


App UI components cannot directly communicate with the outside world. They can only call custom app server functions, which _can_ communicate with the outside world via [`fetch()`](https://docs.attio.com/sdk/server/available-globals#server-only), and communicate with Attio’s REST API via [`attioFetch()`](https://docs.attio.com/sdk/server/attio-fetch).
## 
[​](https://docs.attio.com/sdk/introduction#sequence)
Sequence
The general sequence of how the app will work is:
### 
[​](https://docs.attio.com/sdk/introduction#installation)
Installation
  1. User clicks to install the app.
  2. User is prompted to add a [connection](https://docs.attio.com/sdk/server/connections) to Acme Lead Checker
  3. User logs into Acme Lead Checker to complete the OAuth flow.
  4. User is redirected back to Attio. The app is now installed.
  5. The [`connection-added`](https://docs.attio.com/sdk/server/events/connection-added) event handler the app registered is fired.
  6. Event Handler calls [`createWebhookHandler()`](https://docs.attio.com/sdk/server/webhooks/create-webhook-handler) to register a [webhook handler](https://docs.attio.com/sdk/server/webhooks/update-webhook-handler).
  7. Event Handler registers the new webhook with Acme Lead Checker.


[`Attio Server SDKEvent HandlerAcme Lead CheckerAttio UIAttio Server SDKEvent HandlerAcme Lead CheckerAttio UIUserClicks to install appPrompts to add connection to ALCLogs in (OAuth flow)Redirects back with auth tokenShows app is now installedFires 'connection-added' eventCalls createWebhookHandler()Returns webhook handler detailsRegisters webhookUser`](https://docs.attio.com/diagrams/app-install-sequence)
### 
[​](https://docs.attio.com/sdk/introduction#usage)
Usage
  1. App provides a [record action](https://docs.attio.com/sdk/actions/record-action) which will manifest itself in Attio’s UI as - a button on the People record page - in the CMD-K quick action palette.
  2. User views the record page
  3. User clicks button
  4. Attio’s UI fires the `onTrigger()` function provided by the record action
  5. Record Action notifies the user that async things are happening with [`showToast()`](https://docs.attio.com/sdk/notifications/show-toast).
  6. Record Action loads the phone number of the person whose record page we are on asynchronously via [GraphQL](https://docs.attio.com/sdk/graphql) using [`runQuery()`](https://docs.attio.com/sdk/graphql/run-query). - If no phone numbers are found, the user is notified via an [`alert()`](https://docs.attio.com/sdk/notifications/alert). Otherwise…
  7. Record Action calls a [server function](https://docs.attio.com/sdk/server/server-functions) called `sendToALC()`.
  8. Server function uses [`fetch()`](https://docs.attio.com/sdk/server/available-globals#server-only) to send a `POST` request to `api.acmeleadchecker.ai`.
  9. Server function uses [`attioFetch()`](https://docs.attio.com/sdk/server/attio-fetch) to mark the record as “Pending”.
  10. Server function returns success.
  11. Record Action hides first toast with [`hideToast()`](https://docs.attio.com/sdk/notifications/show-toast#hidetoast-promise-void).
  12. Record Action notifies the user that the process was successful with [`showToast()`](https://docs.attio.com/sdk/notifications/show-toast).


…some time later…
  1. Acme Lead Checker’s server calls a webhook provided by the app.
  2. Webhook Handler uses [`attioFetch()`](https://docs.attio.com/sdk/server/attio-fetch) to mark the record as “Complete”.


[`Attio APIWebhookapi.acmeleadchecker.aiServer FunctionGraphQLRecord ActionAttio UIAttio APIWebhookapi.acmeleadchecker.aiServer FunctionGraphQLRecord ActionAttio UISome time later...UserClicks buttonFires onTrigger()showToast()Shows "Loading" toastLoad phone numbersQuery resultCalls sendToALC()POST requestattioFetch() to mark record "Pending"Returns successhideToast()Hides "Loading" toastshowToast()Shows "Success" toastCalls the app's webhookattioFetch() to mark record "Complete"User`](https://docs.attio.com/diagrams/app-usage-sequence)
## 
[​](https://docs.attio.com/sdk/introduction#implementation)
Implementation
### 
[​](https://docs.attio.com/sdk/introduction#record-action)
Record action
[Record action](https://docs.attio.com/sdk/actions/record-action) files can have any name, but they _MUST_ have a _named_ export called `recordAction`.
send-to-alc-record-action.ts
Copy
```
import type {RecordAction} from "attio/client"
import {runQuery, showToast, alert} from "attio/client"
import getPersonPhoneNumbersQuery from "./get-person-phone-numbers.graphql"
import sendToAlc from "./send-to-alc.server"
// This must be a named export called "recordAction"
export const recordAction: RecordAction = {
    id: "send-to-alc", // internal unique identifier
    label: "Send to ALC", // user-facing label
    onTrigger: async ({recordId}) => {
        const {hideToast} = await showToast({
            title: "Preparing to send to ALC...",
            variant: "neutral",
        })
        const {person} = await runQuery(getPersonPhoneNumbersQuery, {recordId})
        // `person` is strongly typed here as:
        // {
        //   name: {
        //     full_name: string | null
        //   } | null
        //   phone_numbers: string[]
        // } | null
        // ...so TypeScript will help us know the checks we need to perform.
        if (!person) {
            await hideToast()
            await alert({
                title: "Failed to load person data",
                text: "Please try again.",
            })
            return
        }
        const firstPhoneNumber = person.phone_numbers[0] ?? null
        if (!firstPhoneNumber) {
            await hideToast()
            await alert({
                title: "No phone number found",
                text: "Please add a phone number to the person and try again.",
            })
            return
        }
        try {
            await sendToAlc(recordId, person.name?.full_name ?? "Unknown", firstPhoneNumber)
        } catch {
            await hideToast()
            await alert({
                title: "Failed to send to ALC",
                text: "Please try again.",
            })
            return
        }
        await hideToast()
        await showToast({
            title: "Successfully sent to ALC!",
            variant: "success",
        })
    },
    objects: "person", // only show this action on person records
}
```

### 
[​](https://docs.attio.com/sdk/introduction#graphql-query)
GraphQL query
Now let’s write that [GraphQL](https://docs.attio.com/sdk/graphql) query we’re importing.
get-person-phone-numbers.graphql
Copy
```
query getPersonPhoneNumbers($recordId: String!) {
    person(id: $recordId) {
        name {
            full_name
        }
        phone_numbers
    }
}
```

### 
[​](https://docs.attio.com/sdk/introduction#server-function)
Server function
[Server function](https://docs.attio.com/sdk/server) file names _MUST_ :
  * have a `.server.ts` (or `.server.js`) suffix
  * contain an `export default async function`


The suffix is how Attio knows to execute them on the server. However, they are imported as if they were in the same bundle as the client side code, even though they are not.
Because they live in different bundles and runtimes, everything passed to, returned from, or thrown by server functions _MUST_ be serializable.
send-to-alc.server.ts
Copy
```
import {attioFetch, getWorkspaceConnection} from "attio/server"
export default async function sendToAlc(recordId: string, name: string, phoneNumber: string) {
    // Get the authorization token from the workspace connection
    // that the user has set up in their Attio account.
    const connection = getWorkspaceConnection()
    const authorizationToken = connection.value
    const response = await fetch("https://api.acmeleadchecker.ai/api/v1/leads", {
        method: "POST",
        headers: {
            "Content-Type": "application/json",
            "Authorization": `Bearer ${authorizationToken}`,
        },
        body: JSON.stringify({recordId, name, phoneNumber}),
    })
    if (!response.ok) {
        throw new Error("Failed to send to ALC")
    }
    const lead = await response.json()
    // Update the person record with the ALC ID
    await attioFetch({
        // call to Attio's REST API
    })
    return lead
}
```

### 
[​](https://docs.attio.com/sdk/introduction#webhook-handler)
Webhook handler
Our [webhook handler](https://docs.attio.com/sdk/server/webhooks) is going to be called by Acme Lead Checker when they have processed our lead that we sent them.
Webhook handler files _MUST_ :
  * Live under the `src/webhooks` directory
  * Have a `.webhook.ts` (or `.webhook.js`) suffix.
  * Contain an `export default async function` that: 
    * takes an HTTP [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) argument
    * returns an HTTP [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response)


webhooks/lead-processed.webhook.ts
Copy
```
import {attioFetch} from "attio/server"
export default async function leadProcessedWebhook(req: Request): Promise<Response> {
    const body = await req.json()
    const recordId = body.record_id
    const status = body.status
    await attioFetch({
        // call to Attio's REST API
    })
    return new Response(null, {status: 200})
}
```

### 
[​](https://docs.attio.com/sdk/introduction#connection-event-handlers)
Connection event handlers
In order to let Acme Lead Checker know how to call our app’s webhook, we need to tell them as soon as our user creates an authorized [connection](https://docs.attio.com/sdk/server/connections); we accomplish this with [event handlers](https://docs.attio.com/sdk/server/events).
Connection Event Handler files _MUST_ :
  * Live in `src/events`
  * Have a `.event.ts` (or `.event.js`) suffix.
  * Contain an `export default async function` that: 
    * Takes a `{ connection: Connection }` argument
    * Returns `void`


#### 
[​](https://docs.attio.com/sdk/introduction#connection-added-event-handler)
Connection added event handler
When a connection is added, we need to:
  1. Create a webhook
  2. Register our webhook with Acme Lead Checker
  3. Update our webhook with the unique identifier of our webhook on ALC’s side


events/connection-added.event.ts
Copy
```
import type {Connection} from "attio/server"
import {createWebhookHandler, updateWebhookHandler} from "attio/server"
export default async function connectionAdded({connection}: {connection: Connection}) {
    // The filename must match the file in src/webhooks, but without the suffix
    const handler = await createWebhookHandler({fileName: "lead-processed"})
    const authorizationToken = connection.value
    const response = await fetch("https://api.acmeleadchecker.ai/api/v1/webhooks", {
        method: "POST",
        headers: {
            "Content-Type": "application/json",
            "Authorization": `Bearer ${authorizationToken}`,
        },
        body: JSON.stringify({
            name: handler.id,
            url: handler.url,
            event: "lead.processed",
        }),
    })
    if (!response.ok) {
        throw new Error(`Failed to register webhook: ${response.statusText}`)
    }
    const webhook = await response.json()
    // Save the external webhook ID so we can delete it when the connection is removed
    await updateWebhookHandler(handler.id, {
        externalWebhookId: webhook.webhook_id,
    })
}
```

#### 
[​](https://docs.attio.com/sdk/introduction#connection-removed-event-handler)
Connection removed event handler
When a connection is removed, we need to:
  1. Load all our app’s webhook handlers (there should only be one)
  2. For each handler, tell ALC to stop calling it
  3. Delete the webhook from Attio


events/connection-removed.event.ts
Copy
```
import type {Connection} from "attio/server"
import {deleteWebhookHandler, listWebhookHandlers} from "attio/server"
export default async function connectionRemoved({connection}: {connection: Connection}) {
    try {
        const handlers = await listWebhookHandlers()
        const authorizationToken = connection.value
        // Delete webhooks on ALC
        // There should be only one webhook handler active as we have single workspace connection
        await Promise.all(
            handlers.map(async (handler) => {
                const response = await fetch(
                    `https://api.acmeleadchecker.ai/api/v1/webhooks/${handler.externalWebhookId}`,
                    {
                        method: "DELETE",
                        headers: {
                            Authorization: `Bearer ${authorizationToken}`,
                        },
                    }
                )
                if (!response.ok) {
                    throw new Error(`Failed to delete webhook: ${response.statusText}`)
                }
            })
        )
        // Delete webhooks on Attio
        await Promise.all(
            handlers.map(async (handler) => {
                await deleteWebhookHandler(handler.id)
            })
        )
    } catch (error) {
        console.error(error)
        // don't rethrow the error so the connection is still removed
    }
}
```

Was this page helpful?
YesNo
[Creating an app](https://docs.attio.com/sdk/creating-an-app)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Sequence](https://docs.attio.com/sdk/introduction#sequence)
  * [Installation](https://docs.attio.com/sdk/introduction#installation)
  * [Usage](https://docs.attio.com/sdk/introduction#usage)
  * [Implementation](https://docs.attio.com/sdk/introduction#implementation)
  * [Record action](https://docs.attio.com/sdk/introduction#record-action)
  * [GraphQL query](https://docs.attio.com/sdk/introduction#graphql-query)
  * [Server function](https://docs.attio.com/sdk/introduction#server-function)
  * [Webhook handler](https://docs.attio.com/sdk/introduction#webhook-handler)
  * [Connection event handlers](https://docs.attio.com/sdk/introduction#connection-event-handlers)
  * [Connection added event handler](https://docs.attio.com/sdk/introduction#connection-added-event-handler)
  * [Connection removed event handler](https://docs.attio.com/sdk/introduction#connection-removed-event-handler)


Assistant
Responses are generated using AI and may contain mistakes.
