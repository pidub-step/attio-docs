---
title: alert() - Attio Docs
url: https://docs.attio.com/sdk/notifications/alert
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# alert() - Attio Docs

**Source:** [https://docs.attio.com/sdk/notifications/alert](https://docs.attio.com/sdk/notifications/alert)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Notifications
alert()
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
# alert()
Shows an alert to the user
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/alert.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/alert-dark.png)
Copy
```
import {alert} from "attio/client"
```

Analogous to the [`window.alert()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert) function in web browser JavaScript. The popup is [modal](https://en.wikipedia.org/wiki/Modal_window).
It is useful when you forcefully let the user know that something has happened.
## 
[​](https://docs.attio.com/sdk/notifications/alert#api)
API
TypeScript
Copy
```
async function alert(options: Options): Promise<void>
```

## 
[​](https://docs.attio.com/sdk/notifications/alert#options)
Options
### 
[​](https://docs.attio.com/sdk/notifications/alert#title-%3A-string)
`title : string`
The title of the alert pop-up.
### 
[​](https://docs.attio.com/sdk/notifications/alert#text-%3A-string)
`text : string`
The text of the alert pop-up.
### 
[​](https://docs.attio.com/sdk/notifications/alert#oklabel%3F-%3A-string)
`okLabel? : string`
The label for the “OK” button.
Defaults to `"OK"`.
Was this page helpful?
YesNo
[Notifying the user](https://docs.attio.com/sdk/notifications/notifications)[confirm()](https://docs.attio.com/sdk/notifications/confirm)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [API](https://docs.attio.com/sdk/notifications/alert#api)
  * [Options](https://docs.attio.com/sdk/notifications/alert#options)
  * [title : string](https://docs.attio.com/sdk/notifications/alert#title-%3A-string)
  * [text : string](https://docs.attio.com/sdk/notifications/alert#text-%3A-string)
  * [okLabel? : string](https://docs.attio.com/sdk/notifications/alert#oklabel%3F-%3A-string)


Assistant
Responses are generated using AI and may contain mistakes.
