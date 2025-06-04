---
title: useQuery() - Attio Docs
url: https://docs.attio.com/sdk/hooks/use-query
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# useQuery() - Attio Docs

**Source:** [https://docs.attio.com/sdk/hooks/use-query](https://docs.attio.com/sdk/hooks/use-query)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Hooks
useQuery()
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
# useQuery()
A suspensful hook to run a GraphQL query
Not to be confused with the popular [TanStack `useQuery()`](https://tanstack.com/query/latest/docs/framework/react/reference/useQuery) of [Apollo `useQuery()`](https://www.apollographql.com/tutorials/lift-off-part1/10-the-usequery-hook) hooks; this hook is custom to the Attio runtime for running GraphQL queries against the [Attio GraphQL Schema](https://docs.attio.com/sdk/graphql/graphql).
Copy
```
import {useQuery} from "attio/client"
```

While the query is running, the component that uses this hook will “suspend”.
You _MUST_ wrap the component in a [`<React.Suspense/>`](https://react.dev/reference/react/Suspense) component and give it a `fallback` component to render until the query has completed.
If you use more than one `useQuery()` hook in a component, _**they will be executed in sequence, not parallel!**_ Sometimes this is desired, but sometimes you might want to [run them in parallel](https://docs.attio.com/sdk/hooks/use-query#running-in-parallel).
## 
[​](https://docs.attio.com/sdk/hooks/use-query#parameters)
Parameters
### 
[​](https://docs.attio.com/sdk/hooks/use-query#query-%3A-string)
`query : string`
A GraphQL query string.
If you’re using TypeScript and [default] `import` this value from a `.graphql` or `.gql` file, the variables and return value with be strongly typed.
[Read more](https://docs.attio.com/sdk/graphql/graphql).
### 
[​](https://docs.attio.com/sdk/hooks/use-query#variables%3F-%3A-record%3Cstring%2C-any%3E)
`variables? : Record<string, any>`
The named variables your query accepts. If your query has no variables, you needn’t pass any.
## 
[​](https://docs.attio.com/sdk/hooks/use-query#returns)
Returns
### 
[​](https://docs.attio.com/sdk/hooks/use-query#record%3Cstring%2C-any%3E)
`Record<string, any>`
The structured JSON as defined by your query.
## 
[​](https://docs.attio.com/sdk/hooks/use-query#running-in-parallel)
Running in parallel
If you need to run multiple GraphQL queries in parallel, this can be accomplished with a combination of [`runQuery()`](https://docs.attio.com/sdk/graphql/run-query) and [`useAsyncCache()`](https://docs.attio.com/sdk/hooks/use-async-cache) like so:
meet-person.tsx
meet-person.jsx
get-current-user.graphql
get-person-name.graphql
Copy
```
import React from "react"
import {runQuery, TextBlock, useAsyncCache} from "attio/client"
import getPersonName from "./get-person-name.graphql"
import getCurrentUser from "./get-current-user.graphql"
export function MeetPerson({ recordId }: { recordId: string }) {
  // Will run in parallel and suspend until both queries have returned
  const { values } = useAsyncCache({
    currentUserResult: async () => await runQuery(getCurrentUser),
    personResult: async () => await runQuery(getPersonName, { recordId })
  })
  const currentUserName : string =
    values.currentUserResult.currentUser.name
  const personName : string | null | undefined =
    values.personResult.person?.name?.full_name
return (
<TextBlock>
    {personName ?? "Unknown"} would like to meet with {currentUserName}.
</TextBlock>
) }
```

Was this page helpful?
YesNo
[useForm()](https://docs.attio.com/sdk/hooks/use-form)[Server functions](https://docs.attio.com/sdk/server/server-functions)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Parameters](https://docs.attio.com/sdk/hooks/use-query#parameters)
  * [query : string](https://docs.attio.com/sdk/hooks/use-query#query-%3A-string)
  * [variables? : Record<string, any>](https://docs.attio.com/sdk/hooks/use-query#variables%3F-%3A-record%3Cstring%2C-any%3E)
  * [Returns](https://docs.attio.com/sdk/hooks/use-query#returns)
  * [Record<string, any>](https://docs.attio.com/sdk/hooks/use-query#record%3Cstring%2C-any%3E)
  * [Running in parallel](https://docs.attio.com/sdk/hooks/use-query#running-in-parallel)


Assistant
Responses are generated using AI and may contain mistakes.
