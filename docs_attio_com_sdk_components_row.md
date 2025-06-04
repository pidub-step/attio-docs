---
title: <Row /> - Attio Docs
url: https://docs.attio.com/sdk/components/row
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <Row /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/row](https://docs.attio.com/sdk/components/row)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<Row />
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
# <Row />
A component for laying out children horizontally.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/row.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/row-dark.png)
Copy
```
import {Row} from "attio/client"
```

It can be thought of as a
Copy
```
<div style={{ display: "flex", flexDirection: "row" }} />`
```

To lay out components vertically, use [`<Column />`](https://docs.attio.com/sdk/components/column).
On the web, it can fit up to three children horizontally, and on mobile, all children will be presented vertically.
## 
[​](https://docs.attio.com/sdk/components/row#props)
Props
### 
[​](https://docs.attio.com/sdk/components/row#align%3F-%3A-%22left%22-%7C-%22center%22-%7C-%22right%22)
`align? : "left" | "center" | "right"`
How to optionally align the content of the text block.
Defaults to `"center"`.
### 
[​](https://docs.attio.com/sdk/components/row#children-%3A-react-reactnode)
`children : React.ReactNode`
The child components to be displayed horizontally.
Was this page helpful?
YesNo
[<NumberInput />](https://docs.attio.com/sdk/components/number-input)[<Section />](https://docs.attio.com/sdk/components/section)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Props](https://docs.attio.com/sdk/components/row#props)
  * [align? : "left" | "center" | "right"](https://docs.attio.com/sdk/components/row#align%3F-%3A-%22left%22-%7C-%22center%22-%7C-%22right%22)
  * [children : React.ReactNode](https://docs.attio.com/sdk/components/row#children-%3A-react-reactnode)


Assistant
Responses are generated using AI and may contain mistakes.
