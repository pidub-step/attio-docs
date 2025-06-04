---
title: Connections - Attio Docs
url: https://docs.attio.com/sdk/server/connections/connections
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/sdk/server/attio-fetch
---

# Connections - Attio Docs

**Source:** [https://docs.attio.com/sdk/server/connections/connections](https://docs.attio.com/sdk/server/connections/connections)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Connections
Connections
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
    * [Connections](https://docs.attio.com/sdk/server/connections/connections)
    * [getUserConnection()](https://docs.attio.com/sdk/server/connections/get-user-connection)
    * [getWorkspaceConnection()](https://docs.attio.com/sdk/server/connections/get-workspace-connection)
  * Events
  * Webhooks


##### System
  * [platform](https://docs.attio.com/sdk/system/platform)


Connections
# Connections
Authentication to third party services
A Connection is a way of authenticating into a third party service, either via OAuth 2.0 or a secret.
While an app can _technically_ have one of each kind of connection, it will be very rare.
There are two types of Connections:
## 
[​](https://docs.attio.com/sdk/server/connections/connections#user-connections)
User Connections
A User Connection is a connection set up by a specific user to a third party that is specific to a particular user.
e.g. Connecting one user’s calendar to Attio.
On the server side, the secret or auth token for a User Connection is achieved by calling [`getUserConnection()`](https://docs.attio.com/sdk/server/connections/get-user-connection).
## 
[​](https://docs.attio.com/sdk/server/connections/connections#workspace-connections)
Workspace Connections
A Workspace Connection is a connection that is valid for an entire workspace.
e.g. Connecting an entire workspace to a third party SaaS product.
On the server side, the secret or auth token for a Workspace Connection is achieved by calling [`getWorkspaceConnection()`](https://docs.attio.com/sdk/server/connections/get-workspace-connection).
Was this page helpful?
YesNo
[attioFetch()](https://docs.attio.com/sdk/server/attio-fetch)[getUserConnection()](https://docs.attio.com/sdk/server/connections/get-user-connection)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [User Connections](https://docs.attio.com/sdk/server/connections/connections#user-connections)
  * [Workspace Connections](https://docs.attio.com/sdk/server/connections/connections#workspace-connections)


Assistant
Responses are generated using AI and may contain mistakes.
