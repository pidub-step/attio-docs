---
title: RecordAction - Attio Docs
url: https://docs.attio.com/sdk/actions/record-action
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# RecordAction - Attio Docs

**Source:** [https://docs.attio.com/sdk/actions/record-action](https://docs.attio.com/sdk/actions/record-action)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Actions
RecordAction
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


Actions
# RecordAction
Registers an action for records in Attio
Record actions are rendered:
  * on Record pages in Attio
  * in the CMD+K quick action palette.


Any file with a [named export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#using_named_exports) of `recordAction` will register a record action
## 
[​](https://docs.attio.com/sdk/actions/record-action#arguments)
Arguments
### 
[​](https://docs.attio.com/sdk/actions/record-action#id-%3A-string)
`id : string`
The unique identifier for this action.
It is only used internally; never shown to the user.
### 
[​](https://docs.attio.com/sdk/actions/record-action#label-%3A-string)
`label : string`
The human readable label for the record action.
### 
[​](https://docs.attio.com/sdk/actions/record-action#icon-%3A-string)
`icon : string`
An icon to display in the action, either an [`AttioIcon`](https://docs.attio.com/sdk/actions/icons) or a string `.png` referencing a file in your app’s `assets` directory.
If no `icon` prop is provided, it will default to your app’s icon that you set up in the [Developer dashboard](https://build.attio.com).
### 
[​](https://docs.attio.com/sdk/actions/record-action#ontrigger%3F-%3A-async-%7B-recordid%3A-string-%7D-%3D%3E-promise%3Cvoid%3E)
`onTrigger? : async ({ recordId: string }) => Promise<void>`
The function to run when the action is triggered. You’ll likely want to [show a dialog](https://docs.attio.com/sdk/dialogs/show-dialog) or run a [server function](https://docs.attio.com/sdk/server/server-functions) here.
### 
[​](https://docs.attio.com/sdk/actions/record-action#objects%3F%3A-objectslug-%7C-array%3Cobjectslug%3E)
`objects?: ObjectSlug | Array<ObjectSlug>`
A single slug or an array of slugs to select which types of record the record action will apply to.
Defaults to `undefined`, which will cause the action to show on _**all**_ types of records.
The built-in slugs are
  * [`"companies"`](https://docs.attio.com/docs/standard-objects/standard-objects-companies)
  * [`"people"`](https://docs.attio.com/docs/standard-objects/standard-objects-people)
  * [`"deals"`](https://docs.attio.com/docs/standard-objects/standard-objects-deals)
  * [`"users"`](https://docs.attio.com/docs/standard-objects/standard-objects-users)
  * [`"workspaces"`](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)


## 
[​](https://docs.attio.com/sdk/actions/record-action#example-usage)
Example Usage
TypeScript
Copy
```
import type {RecordAction} from "attio/client"
export const recordAction: RecordAction = {
    id: "send-invoice",
    label: "Send Invoice",
    icon: "Sales",
    onTrigger: async ({recordId}) => {
        // Run code here
    },
    objects: "people",
}
```

Was this page helpful?
YesNo
[Design guidelines](https://docs.attio.com/sdk/design-guidelines)[BulkRecordAction](https://docs.attio.com/sdk/actions/bulk-record-action)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Arguments](https://docs.attio.com/sdk/actions/record-action#arguments)
  * [id : string](https://docs.attio.com/sdk/actions/record-action#id-%3A-string)
  * [label : string](https://docs.attio.com/sdk/actions/record-action#label-%3A-string)
  * [icon : string](https://docs.attio.com/sdk/actions/record-action#icon-%3A-string)
  * [onTrigger? : async ({ recordId: string }) => Promise<void>](https://docs.attio.com/sdk/actions/record-action#ontrigger%3F-%3A-async-%7B-recordid%3A-string-%7D-%3D%3E-promise%3Cvoid%3E)
  * [objects?: ObjectSlug | Array<ObjectSlug>](https://docs.attio.com/sdk/actions/record-action#objects%3F%3A-objectslug-%7C-array%3Cobjectslug%3E)
  * [Example Usage](https://docs.attio.com/sdk/actions/record-action#example-usage)


Assistant
Responses are generated using AI and may contain mistakes.
