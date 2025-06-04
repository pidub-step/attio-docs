---
title: <Combobox /> - Attio Docs
url: https://docs.attio.com/sdk/components/combobox
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <Combobox /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/combobox](https://docs.attio.com/sdk/components/combobox)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<Combobox />
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
# <Combobox />
A combobox input.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/combobox.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/combobox-dark.png)
This component is returned by [`useForm()`](https://docs.attio.com/sdk/hooks/use-form).
Options can be provided either synchronously (static or already loaded) or asynchronously (based on a search).
## 
[​](https://docs.attio.com/sdk/components/combobox#props)
Props
### 
[​](https://docs.attio.com/sdk/components/combobox#label-%3A-string)
`label : string`
The label of the combobox field.
### 
[​](https://docs.attio.com/sdk/components/combobox#name-%3A-string)
`name : string`
The path to the `string` value of the input field in your [form schema](https://docs.attio.com/sdk/form-schema).
e.g. `"status"`, `"shipping.address.state"`
### 
[​](https://docs.attio.com/sdk/components/combobox#options-%3A-array%3Ccomboboxoption%3E-%7C-comboboxoptionsprovider)
`options : Array<ComboboxOption> | ComboboxOptionsProvider`
Either an array of [ComboboxOption](https://docs.attio.com/sdk/components/combobox#comboboxoption)s, or a [ComboboxOptionsProvider](https://docs.attio.com/sdk/components/combobox#comboboxoptionsprovider) to load them.
### 
[​](https://docs.attio.com/sdk/components/combobox#placeholder%3F-%3A-string)
`placeholder? : string`
An optional placeholder text for your input.
### 
[​](https://docs.attio.com/sdk/components/combobox#disabled%3F-%3A-boolean)
`disabled? : boolean`
Whether or not the field should be disabled.
# 
[​](https://docs.attio.com/sdk/components/combobox#comboboxoption)
ComboboxOption
An object containing:
### 
[​](https://docs.attio.com/sdk/components/combobox#value-%3A-string)
`value : string`
The value that will be saved into your form data when this option is selected.
### 
[​](https://docs.attio.com/sdk/components/combobox#label-%3A-string-2)
`label : string`
The label the user will see for this option
### 
[​](https://docs.attio.com/sdk/components/combobox#color%3F-%3A-string)
`color? : string`
An optional CSS color for the option. It will be displayed in a little circle next to the label.
# 
[​](https://docs.attio.com/sdk/components/combobox#comboboxoptionprovider)
ComboboxOptionProvider
An object containing:
### 
[​](https://docs.attio.com/sdk/components/combobox#getoption-%3A-value%3A-string-%3D%3E-promise%3Comit%3Ccomboboxoption%2C-%22value%22%3E%3E)
`getOption : (value: string) => Promise<Omit<ComboboxOption, "value">>`
An async function that, given an option value, fetches the rest of the [`ComboboxOption`](https://docs.attio.com/sdk/components/combobox#comboboxoption).
### 
[​](https://docs.attio.com/sdk/components/combobox#search-%3A-query%3A-string-%3D%3E-promise%3Carray%3Ccomboboxoption%3E%3E)
`search : (query: string) => Promise<Array<ComboboxOption>>`
An async function that, given a search query, fetches an array of “matching” [`ComboboxOption`](https://docs.attio.com/sdk/components/combobox#comboboxoption)s.
What “matching” means is up to the developer.
Was this page helpful?
YesNo
[<Column />](https://docs.attio.com/sdk/components/column)[<Form />](https://docs.attio.com/sdk/components/form)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Props](https://docs.attio.com/sdk/components/combobox#props)
  * [label : string](https://docs.attio.com/sdk/components/combobox#label-%3A-string)
  * [name : string](https://docs.attio.com/sdk/components/combobox#name-%3A-string)
  * [options : Array<ComboboxOption> | ComboboxOptionsProvider](https://docs.attio.com/sdk/components/combobox#options-%3A-array%3Ccomboboxoption%3E-%7C-comboboxoptionsprovider)
  * [placeholder? : string](https://docs.attio.com/sdk/components/combobox#placeholder%3F-%3A-string)
  * [disabled? : boolean](https://docs.attio.com/sdk/components/combobox#disabled%3F-%3A-boolean)
  * [ComboboxOption](https://docs.attio.com/sdk/components/combobox#comboboxoption)
  * [value : string](https://docs.attio.com/sdk/components/combobox#value-%3A-string)
  * [label : string](https://docs.attio.com/sdk/components/combobox#label-%3A-string-2)
  * [color? : string](https://docs.attio.com/sdk/components/combobox#color%3F-%3A-string)
  * [ComboboxOptionProvider](https://docs.attio.com/sdk/components/combobox#comboboxoptionprovider)
  * [getOption : (value: string) => Promise<Omit<ComboboxOption, "value">>](https://docs.attio.com/sdk/components/combobox#getoption-%3A-value%3A-string-%3D%3E-promise%3Comit%3Ccomboboxoption%2C-%22value%22%3E%3E)
  * [search : (query: string) => Promise<Array<ComboboxOption>>](https://docs.attio.com/sdk/components/combobox#search-%3A-query%3A-string-%3D%3E-promise%3Carray%3Ccomboboxoption%3E%3E)


Assistant
Responses are generated using AI and may contain mistakes.
