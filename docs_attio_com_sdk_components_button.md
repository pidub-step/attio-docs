---
title: <Button /> - Attio Docs
url: https://docs.attio.com/sdk/components/button
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <Button /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/button](https://docs.attio.com/sdk/components/button)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<Button />
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
# <Button />
A button component.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/button.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/button-dark.png)
Copy
```
import {Button} from "attio/client"
```

Any buttons placed inside a dialog will be rendered at the bottom of the dialog.
## 
[​](https://docs.attio.com/sdk/components/button#props)
Props
### 
[​](https://docs.attio.com/sdk/components/button#label-%3A-string)
`label : string`
The text of the button.
### 
[​](https://docs.attio.com/sdk/components/button#variant%3F-%3A-%22secondary%22-%7C-%22destructive%22)
`variant? : "secondary" | "destructive"`
The style of the button.
Defaults to `"secondary"`.
The only way to have a “primary” button is to use a [submit button](https://docs.attio.com/sdk/components/submit-button).
### 
[​](https://docs.attio.com/sdk/components/button#onclick-%3A-%3D%3E-void)
`onClick : () => void`
A function that will be called if the users clicks the button.
### 
[​](https://docs.attio.com/sdk/components/button#disabled%3F-%3A-boolean)
`disabled? : boolean`
Whether or not the button is disabled.
Defaults to `false`.
### 
[​](https://docs.attio.com/sdk/components/button#keyboardhint%3F-%3A-keyboardkey)
`keyboardHint? : KeyboardKey`
An optional [keyboard shortcut](https://docs.attio.com/sdk/components/keyboard-key) that will fire the button.
Was this page helpful?
YesNo
[showDialog()](https://docs.attio.com/sdk/dialogs/show-dialog)[<Checkbox />](https://docs.attio.com/sdk/components/checkbox)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Props](https://docs.attio.com/sdk/components/button#props)
  * [label : string](https://docs.attio.com/sdk/components/button#label-%3A-string)
  * [variant? : "secondary" | "destructive"](https://docs.attio.com/sdk/components/button#variant%3F-%3A-%22secondary%22-%7C-%22destructive%22)
  * [onClick : () => void](https://docs.attio.com/sdk/components/button#onclick-%3A-%3D%3E-void)
  * [disabled? : boolean](https://docs.attio.com/sdk/components/button#disabled%3F-%3A-boolean)
  * [keyboardHint? : KeyboardKey](https://docs.attio.com/sdk/components/button#keyboardhint%3F-%3A-keyboardkey)


Assistant
Responses are generated using AI and may contain mistakes.
