---
title: Notifying the user - Attio Docs
url: https://docs.attio.com/sdk/notifications/notifications
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Notifying the user - Attio Docs

**Source:** [https://docs.attio.com/sdk/notifications/notifications](https://docs.attio.com/sdk/notifications/notifications)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Notifications
Notifying the user
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
# Notifying the user
Methods to imperatively give feedback to the user
There are three main ways that you can send a notification to the user:
## 
[​](https://docs.attio.com/sdk/notifications/notifications#toasts)
[Toasts](https://docs.attio.com/sdk/notifications/show-toast)
A [toast](https://en.wikipedia.org/wiki/Pop-up_notification) is a subtle, usually temporary, pop-up notification to let the user know that something is happening or has just happened.
These are useful to show when you are performing asynchronous actions such as loading or saving data.
You show one using [`showToast()`](https://docs.attio.com/sdk/notifications/show-toast).
## 
[​](https://docs.attio.com/sdk/notifications/notifications#confirmations)
[Confirmations](https://docs.attio.com/sdk/notifications/confirm)
Analogous to the [`window.confirm()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm) function in web browser JavaScript. The popup is [modal](https://en.wikipedia.org/wiki/Modal_window).
It is useful when you need to get a yes/no answer back from the user, e.g. “Are you sure you want to delete this item?”.
You show one using [`confirm()`](https://docs.attio.com/sdk/notifications/confirm).
## 
[​](https://docs.attio.com/sdk/notifications/notifications#alerts)
[Alerts](https://docs.attio.com/sdk/notifications/alert)
Analogous to the [`window.alert()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert) function in web browser JavaScript. The popup is [modal](https://en.wikipedia.org/wiki/Modal_window).
It is useful when you forcefully let the user know that something has happened.
You show one using [`alert()`](https://docs.attio.com/sdk/notifications/alert).
Was this page helpful?
YesNo
[BulkRecordAction](https://docs.attio.com/sdk/actions/bulk-record-action)[alert()](https://docs.attio.com/sdk/notifications/alert)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Toasts](https://docs.attio.com/sdk/notifications/notifications#toasts)
  * [Confirmations](https://docs.attio.com/sdk/notifications/notifications#confirmations)
  * [Alerts](https://docs.attio.com/sdk/notifications/notifications#alerts)


Assistant
Responses are generated using AI and may contain mistakes.
