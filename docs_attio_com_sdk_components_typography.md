---
title: <Typography /> - Attio Docs
url: https://docs.attio.com/sdk/components/typography
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# <Typography /> - Attio Docs

**Source:** [https://docs.attio.com/sdk/components/typography](https://docs.attio.com/sdk/components/typography)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Components
<Typography />
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
# <Typography />
A component to style text.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/typography.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/typography-dark.png)
Copy
```
import {Typography} from "attio/client"
```

# 
[​](https://docs.attio.com/sdk/components/typography#%3Ctypography-title-%2F%3E)
`<Typography.Title />`
## 
[​](https://docs.attio.com/sdk/components/typography#props)
Props
### 
[​](https://docs.attio.com/sdk/components/typography#variant%3F%3A-%22extralarge%22-%7C-%22large%22-%7C-%22standard%22-%7C-%22medium%22-%7C-%22small%22-%7C-%22extrasmall%22)
`variant?: "extraLarge" | "large" | "standard" | "medium" | "small" | "extraSmall"`
The variant of the title.
Defaults to `"standard"`.
### 
[​](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode)
`children: React.ReactNode`
The content of the title.
# 
[​](https://docs.attio.com/sdk/components/typography#%3Ctypography-body-%2F%3E)
`<Typography.Body />`
## 
[​](https://docs.attio.com/sdk/components/typography#props-2)
Props
### 
[​](https://docs.attio.com/sdk/components/typography#variant%3F%3A-%22standard%22-%7C-%22large%22-%7C-%22strong%22-%7C-%22interactive%22)
`variant?: "standard" | "large" | "strong" | "interactive"`
The variant of the body.
Defaults to `"standard"`.
### 
[​](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode-2)
`children: React.ReactNode`
The content of the body.
# 
[​](https://docs.attio.com/sdk/components/typography#%3Ctypography-caption-%2F%3E)
`<Typography.Caption />`
## 
[​](https://docs.attio.com/sdk/components/typography#props-3)
Props
### 
[​](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode-3)
`children: React.ReactNode`
The content of the caption.
Was this page helpful?
YesNo
[<Toggle />](https://docs.attio.com/sdk/components/toggle)[<WithState />](https://docs.attio.com/sdk/components/with-state)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [<Typography.Title />](https://docs.attio.com/sdk/components/typography#%3Ctypography-title-%2F%3E)
  * [Props](https://docs.attio.com/sdk/components/typography#props)
  * [variant?: "extraLarge" | "large" | "standard" | "medium" | "small" | "extraSmall"](https://docs.attio.com/sdk/components/typography#variant%3F%3A-%22extralarge%22-%7C-%22large%22-%7C-%22standard%22-%7C-%22medium%22-%7C-%22small%22-%7C-%22extrasmall%22)
  * [children: React.ReactNode](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode)
  * [<Typography.Body />](https://docs.attio.com/sdk/components/typography#%3Ctypography-body-%2F%3E)
  * [Props](https://docs.attio.com/sdk/components/typography#props-2)
  * [variant?: "standard" | "large" | "strong" | "interactive"](https://docs.attio.com/sdk/components/typography#variant%3F%3A-%22standard%22-%7C-%22large%22-%7C-%22strong%22-%7C-%22interactive%22)
  * [children: React.ReactNode](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode-2)
  * [<Typography.Caption />](https://docs.attio.com/sdk/components/typography#%3Ctypography-caption-%2F%3E)
  * [Props](https://docs.attio.com/sdk/components/typography#props-3)
  * [children: React.ReactNode](https://docs.attio.com/sdk/components/typography#children%3A-react-reactnode-3)


Assistant
Responses are generated using AI and may contain mistakes.
