---
title: useAsyncCache() - Attio Docs
url: https://docs.attio.com/sdk/hooks/use-async-cache
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# useAsyncCache() - Attio Docs

**Source:** [https://docs.attio.com/sdk/hooks/use-async-cache](https://docs.attio.com/sdk/hooks/use-async-cache)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Hooks
useAsyncCache()
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


Hooks
# useAsyncCache()
A suspenseful hook that returns, and caches, the results of calling one or more async functions, typically to load data from a third-party via server functions.
Copy
```
import {useAsyncCache} from "attio/client"
```

While the async functions are running, the component that uses this hook will “suspend”.
You _MUST_ wrap the component in a [`<React.Suspense/>`](https://react.dev/reference/react/Suspense) component and give it a `fallback` component to render until the functions have completed.
## 
[​](https://docs.attio.com/sdk/hooks/use-async-cache#parameters)
Parameters
It takes an object mapping a `string` key to an async function. If the function requires parameters, the key should map to an array with the async function as the first element and the parameters as the subsequent elements.
## 
[​](https://docs.attio.com/sdk/hooks/use-async-cache#returns)
Returns
An object containing:
  * `values`: an object mapping from the `string` keys provided to whatever type that key’s async function returns
  * `invalidate`: a `(key: string) => void` function to call to invalidate individual cached values, called with the key you want to invalidate


Calling `invalidate()` will cause the values for the specified function to be fetched again, re-suspending the component.
## 
[​](https://docs.attio.com/sdk/hooks/use-async-cache#example-usage)
Example Usage
load-widgets.server.tsx
Copy
```
export default async function loadWidgets(): Promise<Array<Widget>> {
    // fetch widgets from somewhere
}
```

load-sprockets.server.ts
Copy
```
export default async function loadSprockets(
    material: Material,
    max?: number
): Promise<Array<Sprocket>> {
    // fetch sprockets from somewhere
}
```

Copy
```
import { useAsyncCache } from "attio/client"
import loadWidgets from "./load-widgets.server.ts"
import loadSprockets from "./load-sprockets.server.ts"
...
// inside component:
const results = useAsyncCache({
  // loadWidgets takes zero parameters and can thus be called without an array
  widgets: loadWidgets,
  // loadSprockets takes a `material` parameter, so we call it like this
  ironSprockets: [loadSprockets, "iron"],
  copperSprockets: [loadSprockets, "copper", 42],
})
const { widgets, ironSprockets, copperSprockets } = results.values
...
// inside an event handler, perhaps, to refetch _only_ the iron sprockets
results.invalidate("ironSprockets")
```

Was this page helpful?
YesNo
[runQuery()](https://docs.attio.com/sdk/graphql/run-query)[useForm()](https://docs.attio.com/sdk/hooks/use-form)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Parameters](https://docs.attio.com/sdk/hooks/use-async-cache#parameters)
  * [Returns](https://docs.attio.com/sdk/hooks/use-async-cache#returns)
  * [Example Usage](https://docs.attio.com/sdk/hooks/use-async-cache#example-usage)


Assistant
Responses are generated using AI and may contain mistakes.
