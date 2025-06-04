---
title: showDialog() - Attio Docs
url: https://docs.attio.com/sdk/dialogs/show-dialog
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# showDialog() - Attio Docs

**Source:** [https://docs.attio.com/sdk/dialogs/show-dialog](https://docs.attio.com/sdk/dialogs/show-dialog)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Dialogs
showDialog()
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


Dialogs
# showDialog()
Show a dialog box
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/dialog.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/dialog-dark.png)
## 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#example-usage)
Example Usage
Call `showDialog()` from record actions. Hiding the dialog is automatically handled by Attio when the user closes it.
Copy
```
import React from "react"
import {RecordAction, showDialog} from "attio/client"
import {AuroraDialog} from "./aurora-dialog"
export const recordAction: RecordAction = {
    id: "aurora",
    label: "Aurora",
    onTrigger: async ({recordId}) => {
        showDialog({
            title: "Aurora",
            Dialog: () => {
                // This is a React component. It can use hooks and render other components.
                return <AuroraDialog recordId={recordId} />
            },
        })
    },
}
```

## 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#api)
API
TypeScript
Copy
```
async function showDialog(options: DialogOptions): Promise<{
    hideDialog: () => Promise<void>
}>
```

## 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#returns)
Returns
A `Promise` that resolves to an object containing:
### 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#hidedialog%3A-%3D%3E-promise%3Cvoid%3E)
`hideDialog: () => Promise<void>`
By calling `hideDialog()` you can imperatively hide the dialog.
## 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#dialogoptions)
DialogOptions
### 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#title-%3A-string)
`title : string`
The title of the dialog.
### 
[​](https://docs.attio.com/sdk/dialogs/show-dialog#dialog-%3A-react-fc%3C%7B-hidedialog%3A-%3D%3E-void-%7D%3E)
`Dialog : React.FC<{ hideDialog: () => void }>`
The contents of the dialog.
Was this page helpful?
YesNo
[showToast()](https://docs.attio.com/sdk/notifications/show-toast)[<Button />](https://docs.attio.com/sdk/components/button)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Example Usage](https://docs.attio.com/sdk/dialogs/show-dialog#example-usage)
  * [API](https://docs.attio.com/sdk/dialogs/show-dialog#api)
  * [Returns](https://docs.attio.com/sdk/dialogs/show-dialog#returns)
  * [hideDialog: () => Promise<void>](https://docs.attio.com/sdk/dialogs/show-dialog#hidedialog%3A-%3D%3E-promise%3Cvoid%3E)
  * [DialogOptions](https://docs.attio.com/sdk/dialogs/show-dialog#dialogoptions)
  * [title : string](https://docs.attio.com/sdk/dialogs/show-dialog#title-%3A-string)
  * [Dialog : React.FC<{ hideDialog: () => void }>](https://docs.attio.com/sdk/dialogs/show-dialog#dialog-%3A-react-fc%3C%7B-hidedialog%3A-%3D%3E-void-%7D%3E)


Assistant
Responses are generated using AI and may contain mistakes.
