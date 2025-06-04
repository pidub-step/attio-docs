---
title: confirm() - Attio Docs
url: https://docs.attio.com/sdk/notifications/confirm
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# confirm() - Attio Docs

**Source:** [https://docs.attio.com/sdk/notifications/confirm](https://docs.attio.com/sdk/notifications/confirm)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Notifications
confirm()
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


Notifications
# confirm()
Shows a confirmation prompt to the user
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/confirm.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/confirm-dark.png)
Copy
```
import {confirm} from "attio/client"
```

Analogous to the [`window.confirm()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm) function in web browser JavaScript. The popup is [modal](https://en.wikipedia.org/wiki/Modal_window).
It is useful when you need to get a yes/no answer back from the user, e.g. “Are you sure you want to delete this item?”.
## 
[​](https://docs.attio.com/sdk/notifications/confirm#api)
API
TypeScript
Copy
```
async function confirm(options: Options): Promise<boolean>
```

## 
[​](https://docs.attio.com/sdk/notifications/confirm#options)
Options
### 
[​](https://docs.attio.com/sdk/notifications/confirm#title-%3A-string)
`title : string`
The title of the confirm pop-up.
### 
[​](https://docs.attio.com/sdk/notifications/confirm#text-%3A-string)
`text : string`
The text of the confirm pop-up.
### 
[​](https://docs.attio.com/sdk/notifications/confirm#confirmlabel%3F-%3A-string)
`confirmLabel? : string`
The label for the confirm button.
Defaults to `"OK"`.
### 
[​](https://docs.attio.com/sdk/notifications/confirm#cancellabel%3F-%3A-string)
`cancelLabel? : string`
The label for the cancel button.
Defaults to `"Cancel"`.
### 
[​](https://docs.attio.com/sdk/notifications/confirm#confirmvariant%3F%3A-%22primary%22-%7C-%22secondary%22-%7C-%22secondary-destructive%22-%7C-%22destructive%22)
`confirmVariant?: "primary" | "secondary" | "secondary-destructive" | "destructive"`
The style of the confirm button.
Defaults to `"primary"`.
Was this page helpful?
YesNo
[alert()](https://docs.attio.com/sdk/notifications/alert)[showToast()](https://docs.attio.com/sdk/notifications/show-toast)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [API](https://docs.attio.com/sdk/notifications/confirm#api)
  * [Options](https://docs.attio.com/sdk/notifications/confirm#options)
  * [title : string](https://docs.attio.com/sdk/notifications/confirm#title-%3A-string)
  * [text : string](https://docs.attio.com/sdk/notifications/confirm#text-%3A-string)
  * [confirmLabel? : string](https://docs.attio.com/sdk/notifications/confirm#confirmlabel%3F-%3A-string)
  * [cancelLabel? : string](https://docs.attio.com/sdk/notifications/confirm#cancellabel%3F-%3A-string)
  * [confirmVariant?: "primary" | "secondary" | "secondary-destructive" | "destructive"](https://docs.attio.com/sdk/notifications/confirm#confirmvariant%3F%3A-%22primary%22-%7C-%22secondary%22-%7C-%22secondary-destructive%22-%7C-%22destructive%22)


Assistant
Responses are generated using AI and may contain mistakes.
