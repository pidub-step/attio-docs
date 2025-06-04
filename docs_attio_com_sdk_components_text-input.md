---
title: <TextInput /> - Attio Docs
url: https://docs.attio.com/sdk/components/text-input
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <TextInput /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/text-input](https://docs.attio.com/sdk/components/text-input)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<TextInput />
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


Components
# <TextInput />
A string input field.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/text-input.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/text-input-dark.png)
This component is returned by [`useForm()`](https://docs.attio.com/sdk/hooks/use-form).
## 
[​](https://docs.attio.com/sdk/components/text-input#props)
Props
### 
[​](https://docs.attio.com/sdk/components/text-input#label-%3A-string)
`label : string`
The label of the input field.
### 
[​](https://docs.attio.com/sdk/components/text-input#name-%3A-string)
`name : string`
The path to the `string` value of the input field in your [form schema](https://docs.attio.com/sdk/form-schema).
e.g. `"name"`, `"shipping.address.street"`
### 
[​](https://docs.attio.com/sdk/components/text-input#type%3F%3A-%22text%22-%7C-%22email%22-%7C-%22password%22-%7C-%22tel%22-%7C-%22url%22)
`type?: "text" | "email" | "password" | "tel" | "url"`
The type of the input field.
They roughly correspond to the HTML types [`text`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text), [`email`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email), [`password`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password), [`tel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/tel), and [`url`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url).
Defaults to `"text"`.
Useful on mobile devices with virtual keyboards.
### 
[​](https://docs.attio.com/sdk/components/text-input#placeholder%3F-%3A-string)
`placeholder? : string`
An optional placeholder text for your input.
### 
[​](https://docs.attio.com/sdk/components/text-input#disabled%3F-%3A-boolean)
`disabled? : boolean`
Whether or not the field should be disabled.
Defaults to `false` (not disabled).
Was this page helpful?
YesNo
[<TextBlock />](https://docs.attio.com/sdk/components/text-block)[<Toggle />](https://docs.attio.com/sdk/components/toggle)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Props](https://docs.attio.com/sdk/components/text-input#props)
  * [label : string](https://docs.attio.com/sdk/components/text-input#label-%3A-string)
  * [name : string](https://docs.attio.com/sdk/components/text-input#name-%3A-string)
  * [type?: "text" | "email" | "password" | "tel" | "url"](https://docs.attio.com/sdk/components/text-input#type%3F%3A-%22text%22-%7C-%22email%22-%7C-%22password%22-%7C-%22tel%22-%7C-%22url%22)
  * [placeholder? : string](https://docs.attio.com/sdk/components/text-input#placeholder%3F-%3A-string)
  * [disabled? : boolean](https://docs.attio.com/sdk/components/text-input#disabled%3F-%3A-boolean)


Assistant
Responses are generated using AI and may contain mistakes.
