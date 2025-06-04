---
title: Server functions - Attio Docs
url: https://docs.attio.com/sdk/server/server-functions
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Server functions - Attio Docs

**Source:** [https://docs.attio.com/sdk/server/server-functions](https://docs.attio.com/sdk/server/server-functions)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Server
Server functions
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


Server
# Server functions
Running code on the server
Not to be confused with [React Server Functions](https://react.dev/reference/rsc/server-functions); while they serve similar purposes, Attio server functions have different requirements and therefore do not follow the RSC protocol.
Server functions allow you to get, update, or delete data from third-party services, optionally using the user’s access token or secret. We do not allow client-side fetch requests, so all HTTP requests to third-party services must happen within server functions, which run inside a secure sandbox within the Attio infrastructure. The server function runtime _**is not Node.js compatible**_ , meaning some libraries that work in Node.js might not work in our environment.
The globals available to you are listed in [Available Globals](https://docs.attio.com/sdk/server/available-globals).
To add a server function to your app, you need to create a file with the `.server.ts` (or `.server.js`) suffix. The file must `export` a `default async function`, which will serve as the entry point for the server function. You can then import and call this function within the client code.
Here is an example of using a server function to make [a request](https://developers.outreach.io/api/reference/tag/Sequence-State/#tag/Sequence-State/paths/~1sequenceStates/post) to Outreach on behalf of a user.
TypeScript
Copy
```
// add-to-sequence.server.ts
import {getUserConnection} from "attio/server"
export default async function addToSequence({
    prospectId,
    sequenceId,
    mailboxId,
}: {
    prospectId: string
    sequenceId: number
    mailboxId: number
}): Promise<{id: string}> {
    const response = await fetch(`https://api.outreach.io/api/v2/sequenceStates`, {
        method: "POST",
        headers: {
            "Content-Type": "application/vnd.api+json",
            "Authorization": `Bearer ${getUserConnection().value}`,
        },
        body: JSON.stringify({prospectId, sequenceId, mailboxId}),
    })
    if (!response.ok) {
        throw new Error(`Failed to add prospect to sequence: ${await response.text()}`)
    }
    // ℹ️ better to parse with a tool like Zod than to cast
    const body = (await response.json()) as {data: Record<string, string>}
    return body.data
}
```

Then, this `addToSequence()` function can be called from your client side code like:
TypeScript
Copy
```
import addToSequence from "add-to-sequence.server.ts"
...
const sequenceState = await addToSequence({
  prospectId: "XXX",
  sequenceId: 42,
  mailboxId: 42
})
```

As you can see, it’s possible to pass arguments and access the return value of a server function. Each call to a server function makes a request to the Attio infrastructure which is executed in a sandbox environment. Since we have to cross a network boundary, _**it’s only possible to pass JSON-serializable data**_ between client and server functions.
Whatever you pass to or return from a server function will go through `JSON.stringify(JSON.parse(...))`.
If a server function throws an error, it is re-thrown on the client side and can be handled with `try/catch` or `.catch` [promise chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#chaining).
To check output of `console.log()` inside the server functions,
TODO: Finish this sentence 👆
Was this page helpful?
YesNo
[useQuery()](https://docs.attio.com/sdk/hooks/use-query)[attioFetch()](https://docs.attio.com/sdk/server/attio-fetch)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
