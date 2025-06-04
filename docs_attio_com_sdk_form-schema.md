---
title: Form schema - Attio Docs
url: https://docs.attio.com/sdk/form-schema
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Form schema - Attio Docs

**Source:** [https://docs.attio.com/sdk/form-schema](https://docs.attio.com/sdk/form-schema)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Forms
Form schema
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


Forms
# Form schema
Defines the shape of your form data
Copy
```
import {Forms} from "attio/client"
```

The schema is formed using the [builder pattern](https://howtodoinjava.com/design-patterns/creational/builder-pattern-in-java/). Objects can be nested arbitrarily deep.
## 
[​](https://docs.attio.com/sdk/form-schema#example)
Example
Copy
```
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

The allowed `FormValue`s are:
## 
[​](https://docs.attio.com/sdk/form-schema#forms-string)
`Forms.string()`
A string value. Required by default.
### 
[​](https://docs.attio.com/sdk/form-schema#mutators)
Mutators
`.default(value : string)`
Sets a default value to return when no value is entered by the user.
This is _**NOT**_ the same as an “initial value”, which should be passed to the [`useForm()`](https://docs.attio.com/sdk/hooks/use-form) hook.
`.multiline()`
Will cause the string input to be multiline.
A `<textarea />` rather than an `<input type="text" />` in DOM-speak
`.optional()`
By default, strings are required. This will change that to let `null`, `undefined`, and `""` pass validation.
## 
[​](https://docs.attio.com/sdk/form-schema#forms-number)
`Forms.number()`
A numeric value. Required by default.
### 
[​](https://docs.attio.com/sdk/form-schema#mutators-2)
Mutators
`.default(value : number)`
Sets a default value to return when no value is entered by the user.
This is _**NOT**_ the same as an “initial value”, which should be passed to the [`useForm()`](https://docs.attio.com/sdk/hooks/use-form) hook.
`.optional()`
By default, numbers are required. This will change that to let `null` and `undefined` pass validation.
`.min(min: number)`
Provide a minimum value. Validation will fail if the user inputs number `< min`.
`.max(max: number)`
Provide a maximum value. Validation will fail if the user inputs number `> max`.
## 
[​](https://docs.attio.com/sdk/form-schema#forms-array-formvalue-%7C-record%3Cstring%2C-formvalue%3E)
`Forms.array(FormValue | Record<string, FormValue>)`
An array of other form values or objects of form values.
They are referenced with a `name` prop like `"addresses[0].street"`.
### 
[​](https://docs.attio.com/sdk/form-schema#mutators-3)
Mutators
`.optional()`
By default, arrays are required. This will change that to let `null` and `undefined` pass validation.
Was this page helpful?
YesNo
[<WithState />](https://docs.attio.com/sdk/components/with-state)[Using GraphQL](https://docs.attio.com/sdk/graphql/graphql)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Example](https://docs.attio.com/sdk/form-schema#example)
  * [Forms.string()](https://docs.attio.com/sdk/form-schema#forms-string)
  * [Mutators](https://docs.attio.com/sdk/form-schema#mutators)
  * [Forms.number()](https://docs.attio.com/sdk/form-schema#forms-number)
  * [Mutators](https://docs.attio.com/sdk/form-schema#mutators-2)
  * [Forms.array(FormValue | Record<string, FormValue>)](https://docs.attio.com/sdk/form-schema#forms-array-formvalue-%7C-record%3Cstring%2C-formvalue%3E)
  * [Mutators](https://docs.attio.com/sdk/form-schema#mutators-3)


Assistant
Responses are generated using AI and may contain mistakes.
