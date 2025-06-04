---
title: useForm() - Attio Docs
url: https://docs.attio.com/sdk/hooks/use-form
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# useForm() - Attio Docs

**Source:** [https://docs.attio.com/sdk/hooks/use-form](https://docs.attio.com/sdk/hooks/use-form)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Hooks
useForm()
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
# useForm()
A hook for creating forms inside your Attio app.
## 
[​](https://docs.attio.com/sdk/hooks/use-form#parameters)
Parameters
### 
[​](https://docs.attio.com/sdk/hooks/use-form#schema-%3A-record%3Cstring%2C-formvalue%3E)
`schema : Record<string, FormValue>`
A [form schema](https://docs.attio.com/sdk/form-schema) is how you tell Attio about the shape and validation rules of your form data.
### 
[​](https://docs.attio.com/sdk/hooks/use-form#initialvalues-%3A-record%3Cstring%2C-any%3E)
`initialValues : Record<string, any>`
These values must match the type defined by your [form schema](https://docs.attio.com/sdk/forms/schema).
## 
[​](https://docs.attio.com/sdk/hooks/use-form#returns)
Returns
an object containing:
### 
[​](https://docs.attio.com/sdk/hooks/use-form#functions)
Functions
#### 
[​](https://docs.attio.com/sdk/hooks/use-form#change-%3A-path%3A-string%2C-value%3A-any-%3D%3E-void)
`change : (path: string, value: any) => void`
An imperative function to update a particular value in the form.
#### 
[​](https://docs.attio.com/sdk/hooks/use-form#submit-%3A-%3D%3E-void)
`submit : () => void`
An imperative function to submit the form. It will cause validation to run, and if the validation passes it will call the `onSubmit` handler that you have passed to `<Form/>`.
Typically you won’t be using this, but will rather render a `<SubmitButton />`
### 
[​](https://docs.attio.com/sdk/hooks/use-form#components)
Components
  * [`<Checkbox />`](https://docs.attio.com/sdk/components/checkbox)
  * [`<Combobox />`](https://docs.attio.com/sdk/components/combobox)
  * [`<Form />`](https://docs.attio.com/sdk/components/form)
  * [`<NumberInput />`](https://docs.attio.com/sdk/components/number-input)
  * [`<SubmitButton />`](https://docs.attio.com/sdk/components/submit-button)
  * [`<TextInput />`](https://docs.attio.com/sdk/components/text-input)
  * [`<Toggle />`](https://docs.attio.com/sdk/components/toggle)
  * [`<WithState />`](https://docs.attio.com/sdk/components/with-state)


Was this page helpful?
YesNo
[useAsyncCache()](https://docs.attio.com/sdk/hooks/use-async-cache)[useQuery()](https://docs.attio.com/sdk/hooks/use-query)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Parameters](https://docs.attio.com/sdk/hooks/use-form#parameters)
  * [schema : Record<string, FormValue>](https://docs.attio.com/sdk/hooks/use-form#schema-%3A-record%3Cstring%2C-formvalue%3E)
  * [initialValues : Record<string, any>](https://docs.attio.com/sdk/hooks/use-form#initialvalues-%3A-record%3Cstring%2C-any%3E)
  * [Returns](https://docs.attio.com/sdk/hooks/use-form#returns)
  * [Functions](https://docs.attio.com/sdk/hooks/use-form#functions)
  * [change : (path: string, value: any) => void](https://docs.attio.com/sdk/hooks/use-form#change-%3A-path%3A-string%2C-value%3A-any-%3D%3E-void)
  * [submit : () => void](https://docs.attio.com/sdk/hooks/use-form#submit-%3A-%3D%3E-void)
  * [Components](https://docs.attio.com/sdk/hooks/use-form#components)


Assistant
Responses are generated using AI and may contain mistakes.
