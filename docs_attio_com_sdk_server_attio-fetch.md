---
title: attioFetch() - Attio Docs
url: https://docs.attio.com/sdk/server/attio-fetch
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# attioFetch() - Attio Docs

**Source:** [https://docs.attio.com/sdk/server/attio-fetch](https://docs.attio.com/sdk/server/attio-fetch)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Server
attioFetch()
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
# attioFetch()
Calls the Attio REST API
Copy
```
import {attioFetch} from "attio/server"
```

Calls the [Attio REST API](https://docs.attio.com/rest-api). It’s modeled after the [Node `fetch()` API](https://nodejs.org/en/learn/getting-started/fetch).
The auth credentials passed to the REST API will be those of your app.
What the API will allow you to do depends on the scopes granted to your app.
## 
[​](https://docs.attio.com/sdk/server/attio-fetch#arguments)
Arguments
An object containing:
### 
[​](https://docs.attio.com/sdk/server/attio-fetch#method-%3A-%22get%22-%7C-%22post%22-%7C-%22delete%22-%7C-%22patch%22)
`method : "GET" | "POST" | "DELETE" | "PATCH"`
The HTTP method to use.
### 
[​](https://docs.attio.com/sdk/server/attio-fetch#queryparams%3F-%3A-record%3Cstring%2C-unknown%3E)
`queryParams? : Record<string, unknown>`
The query parameters to use in the HTTP request.
### 
[​](https://docs.attio.com/sdk/server/attio-fetch#body%3F-%3A-%7B-data%3F%3A-record%3Cstring%2C-unknown%3E%2C-filter%3F%3A-record%3Cstring%2C-unknown%3E-%7D)
`body? : { data?: Record<string, unknown>, filter?: Record<string, unknown> }`
The body of the HTTP request.
In the [Attio REST API](https://docs.attio.com/rest-api), this is always an object with key `"data"` or `"filter"`.
## 
[​](https://docs.attio.com/sdk/server/attio-fetch#returns)
Returns
An object containing:
### 
[​](https://docs.attio.com/sdk/server/attio-fetch#data-%3A-record%3Cstring%2C-unknown%3E-%7C-array%3Crecord%3Cstring%2C-unknown%3E%3E)
`data : Record<string, unknown> | Array<Record<string, unknown>>`
The result of the Attio REST endpoint.
## 
[​](https://docs.attio.com/sdk/server/attio-fetch#example-usage)
Example Usage
Copy
```
import {attioFetch} from "attio/server"
...
const notes = await attioFetch({
    method: "GET",
    path: "/notes",
})
notes.data.forEach(note => {
  // do something with each note
})
```

Was this page helpful?
YesNo
[Server functions](https://docs.attio.com/sdk/server/server-functions)[Connections](https://docs.attio.com/sdk/server/connections/connections)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Arguments](https://docs.attio.com/sdk/server/attio-fetch#arguments)
  * [method : "GET" | "POST" | "DELETE" | "PATCH"](https://docs.attio.com/sdk/server/attio-fetch#method-%3A-%22get%22-%7C-%22post%22-%7C-%22delete%22-%7C-%22patch%22)
  * [queryParams? : Record<string, unknown>](https://docs.attio.com/sdk/server/attio-fetch#queryparams%3F-%3A-record%3Cstring%2C-unknown%3E)
  * [body? : { data?: Record<string, unknown>, filter?: Record<string, unknown> }](https://docs.attio.com/sdk/server/attio-fetch#body%3F-%3A-%7B-data%3F%3A-record%3Cstring%2C-unknown%3E%2C-filter%3F%3A-record%3Cstring%2C-unknown%3E-%7D)
  * [Returns](https://docs.attio.com/sdk/server/attio-fetch#returns)
  * [data : Record<string, unknown> | Array<Record<string, unknown>>](https://docs.attio.com/sdk/server/attio-fetch#data-%3A-record%3Cstring%2C-unknown%3E-%7C-array%3Crecord%3Cstring%2C-unknown%3E%3E)
  * [Example Usage](https://docs.attio.com/sdk/server/attio-fetch#example-usage)


Assistant
Responses are generated using AI and may contain mistakes.
