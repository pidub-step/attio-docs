---
title: <WithState /> - Attio Docs
url: https://docs.attio.com/sdk/components/with-state
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <WithState /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/with-state](https://docs.attio.com/sdk/components/with-state)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<WithState />
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
# <WithState />
A non-visual component to get form state when rendering JSX
This component is returned by [`useForm()`](https://docs.attio.com/sdk/hooks/use-form).
## 
[​](https://docs.attio.com/sdk/components/with-state#props)
Props
### 
[​](https://docs.attio.com/sdk/components/with-state#errors%3F-%3A-boolean)
`errors? : boolean`
Whether or not to request the form validation errors.
Defaults to `false`.
If `true`, the `errors` will be passed to the `children` render prop.
### 
[​](https://docs.attio.com/sdk/components/with-state#submitting%3F-%3A-boolean)
`submitting? : boolean`
Whether or not to request whether the form is currently being submitted.
Defaults to `false`.
If `true`, the `submitting` will be passed to the `children` render prop.
### 
[​](https://docs.attio.com/sdk/components/with-state#values%3F-%3A-boolean)
`values? : boolean`
Whether or not to request the form values.
Defaults to `false`.
If `true`, the `values` will be passed to the `children` render prop.
### 
[​](https://docs.attio.com/sdk/components/with-state#children%3A-%7B-errors%2C-submitting%2C-values-%7D-%3D%3E-react-reactnode)
`children: ({ errors, submitting, values }) => React.ReactNode`
A [render prop](https://react.dev/reference/react/Children#calling-a-render-prop-to-customize-rendering) that receives the requested form state.
#### 
[​](https://docs.attio.com/sdk/components/with-state#errors%3F-%3A-object)
`errors? : Object`
An object of form validation errors in the same shape as your form values.
#### 
[​](https://docs.attio.com/sdk/components/with-state#submitting%3F-%3A-boolean-2)
`submitting? : boolean`
`true` until the `Promise` resolves from `onSubmit`, `false` otherwise.
#### 
[​](https://docs.attio.com/sdk/components/with-state#values%3F-%3A-object)
`values? : Object`
The current values of your form.
Was this page helpful?
YesNo
[<Typography />](https://docs.attio.com/sdk/components/typography)[Form schema](https://docs.attio.com/sdk/form-schema)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Props](https://docs.attio.com/sdk/components/with-state#props)
  * [errors? : boolean](https://docs.attio.com/sdk/components/with-state#errors%3F-%3A-boolean)
  * [submitting? : boolean](https://docs.attio.com/sdk/components/with-state#submitting%3F-%3A-boolean)
  * [values? : boolean](https://docs.attio.com/sdk/components/with-state#values%3F-%3A-boolean)
  * [children: ({ errors, submitting, values }) => React.ReactNode](https://docs.attio.com/sdk/components/with-state#children%3A-%7B-errors%2C-submitting%2C-values-%7D-%3D%3E-react-reactnode)
  * [errors? : Object](https://docs.attio.com/sdk/components/with-state#errors%3F-%3A-object)
  * [submitting? : boolean](https://docs.attio.com/sdk/components/with-state#submitting%3F-%3A-boolean-2)
  * [values? : Object](https://docs.attio.com/sdk/components/with-state#values%3F-%3A-object)


Assistant
Responses are generated using AI and may contain mistakes.
