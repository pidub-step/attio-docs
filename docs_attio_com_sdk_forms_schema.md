---
title: Schema - Attio Docs
url: https://docs.attio.com/sdk/forms/schema
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/sdk/hooks/use-form
---

# Schema - Attio Docs

**Source:** [https://docs.attio.com/sdk/forms/schema](https://docs.attio.com/sdk/forms/schema)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Schema
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


# Schema
How to build forms.
You can build a form schema using the builder pattern, as follows:
Copy
```
import {Forms} from "attio/client"
const schema = {
    name: Forms.string(),
    note: Forms.string().multiline(),
    nickname: Forms.string().optional(),
    age: Forms.number().min(18),
    numTokens: Forms.number().max(100),
    phoneNumbers: Forms.array(Forms.string()),
    addresses: Forms.array({
        street: Forms.string(),
        city: Forms.string(),
    }),
}
```

The allowed values are:
### 
[​](https://docs.attio.com/sdk/forms/schema#forms-string)
Forms.string()
A string value. Required by default.
**Mutators**
  * `.default(value : string)` sets a default value to return when no value is entered by the user. Note: This is NOT the same as an “initial value”, which should be passed to the `useForm()` hook.
  * `multiline()` will cause the string input to be multiline. i.e. a `<textarea>` rather than an `<input>` in DOM-speak.
  * `optional()` by default, strings are required. This will change that to let `null`, `undefined` and `""` pass validation.


### 
[​](https://docs.attio.com/sdk/forms/schema#forms-number)
Forms.number()
A numeric value. Required by default.
**Mutators**
  * `.default(value : number)` sets a default value to return when no value is entered by the user. Note: This is NOT the same as an “initial value”, which should be passed to the `useForm()` hook.
  * `optional()` by default, numbers are required. This will change that to let `null`, `undefined` and `""` pass validation.
  * `min(min : number)` provide a minimum value. Validation will fail if the user inputs number `< min`.
  * `max(max : number)` provide a maximum value. Validation will fail if the user inputs number `> max`.


### 
[​](https://docs.attio.com/sdk/forms/schema#forms-array-formvalue-%7C-record%3Cstring%2C-formvalue%3E)
Forms.array(`FormValue | Record<string, FormValue>`)
An array of other form values or objects of form values.
**Mutators**
  * `optional()` by default, arrays are required. This will change that to let `null`, `undefined` pass validation.


Was this page helpful?
YesNo
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Forms.string()](https://docs.attio.com/sdk/forms/schema#forms-string)
  * [Forms.number()](https://docs.attio.com/sdk/forms/schema#forms-number)
  * [Forms.array(FormValue | Record<string, FormValue>)](https://docs.attio.com/sdk/forms/schema#forms-array-formvalue-%7C-record%3Cstring%2C-formvalue%3E)


Assistant
Responses are generated using AI and may contain mistakes.
