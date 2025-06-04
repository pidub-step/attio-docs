---
title: showToast() - Attio Docs
url: https://docs.attio.com/sdk/notifications/show-toast
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# showToast() - Attio Docs

**Source:** [https://docs.attio.com/sdk/notifications/show-toast](https://docs.attio.com/sdk/notifications/show-toast)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Notifications
showToast()
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
# showToast()
Shows a toast to the user
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/notification.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/notification-dark.png)
Copy
```
import {showToast} from "attio/client"
```

A [toast](https://en.wikipedia.org/wiki/Pop-up_notification) is a subtle, usually temporary, pop-up notification to let the user know that something is happening or has just happened.
These are useful to show when you are performing asynchronous actions such as loading or saving data.
## 
[​](https://docs.attio.com/sdk/notifications/show-toast#api)
API
TypeScript
Copy
```
async function showToast(options: Options): Promise<{
    hideToast: () => Promise<void>
}>
```

## 
[​](https://docs.attio.com/sdk/notifications/show-toast#returns)
Returns
A `Promise` that resolves to an object containing:
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#hidetoast%3A-%3D%3E-promise%3Cvoid%3E)
`hideToast: () => Promise<void>`
By calling `hideToast()` you can imperatively hide the toast.
Useful if your toast was showing a “loading” or “saving” message.
## 
[​](https://docs.attio.com/sdk/notifications/show-toast#options)
Options
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#title-%3A-string)
`title : string`
The title of the toast.
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#text-%3A-string)
`text : string`
The text of the toastoas.
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#action%3F-%3A-%7B-label%3A-string%2C-onclick%3A-%3D%3E-void-%7D)
`action? : { label: string, onClick: () => void }`
An optional action button that can execute code if and when the user triggers it.
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#durationms%3F-%3A-number)
`durationMs? : number`
How long to keep the toast open.
Defaults to `4_000` (four seconds)
If you want the toast to remain open indefinitely, you can pass `Number.POSITIVE_INFINITY`.
Only do this if you do _**not**_ have `dismissable` set to `false`!
### 
[​](https://docs.attio.com/sdk/notifications/show-toast#dismissable%3F-%3A-boolean)
`dismissable? : boolean`
Whether or not to allow the user to dismiss the toast.
Defaults to `true`.
Was this page helpful?
YesNo
[confirm()](https://docs.attio.com/sdk/notifications/confirm)[showDialog()](https://docs.attio.com/sdk/dialogs/show-dialog)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [API](https://docs.attio.com/sdk/notifications/show-toast#api)
  * [Returns](https://docs.attio.com/sdk/notifications/show-toast#returns)
  * [hideToast: () => Promise<void>](https://docs.attio.com/sdk/notifications/show-toast#hidetoast%3A-%3D%3E-promise%3Cvoid%3E)
  * [Options](https://docs.attio.com/sdk/notifications/show-toast#options)
  * [title : string](https://docs.attio.com/sdk/notifications/show-toast#title-%3A-string)
  * [text : string](https://docs.attio.com/sdk/notifications/show-toast#text-%3A-string)
  * [action? : { label: string, onClick: () => void }](https://docs.attio.com/sdk/notifications/show-toast#action%3F-%3A-%7B-label%3A-string%2C-onclick%3A-%3D%3E-void-%7D)
  * [durationMs? : number](https://docs.attio.com/sdk/notifications/show-toast#durationms%3F-%3A-number)
  * [dismissable? : boolean](https://docs.attio.com/sdk/notifications/show-toast#dismissable%3F-%3A-boolean)


Assistant
Responses are generated using AI and may contain mistakes.
