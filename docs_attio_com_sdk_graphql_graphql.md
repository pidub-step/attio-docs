---
title: Using GraphQL - Attio Docs
url: https://docs.attio.com/sdk/graphql/graphql
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Using GraphQL - Attio Docs

**Source:** [https://docs.attio.com/sdk/graphql/graphql](https://docs.attio.com/sdk/graphql/graphql)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
GraphQL
Using GraphQL
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


GraphQL
# Using GraphQL
Querying Attio data on the client via GraphQL
## 
[​](https://docs.attio.com/sdk/graphql/graphql#api)
API
The Attio client SDK provides a typesafe way to query record data via GraphQL.
There are two main functions for this. Which you choose to use is a design decision of your app.
### 
[​](https://docs.attio.com/sdk/graphql/graphql#runquery)
[`runQuery`](https://docs.attio.com/sdk/graphql/run-query)
An imperative asynchronous function to query record data.
### 
[​](https://docs.attio.com/sdk/graphql/graphql#usequery)
[`useQuery`](https://docs.attio.com/sdk/hooks/use-query)
A suspenseful hook to query record data.
## 
[​](https://docs.attio.com/sdk/graphql/graphql#writing-graphql-queries)
Writing GraphQL Queries
When you run `npx attio dev` to develop your app, you will be prompted to `Press "o" to open GraphQL Explorer.`. If you do press `o`, it will open an instance of [GraphiQL](https://github.com/graphql/graphiql/tree/main/packages/graphiql#graphiql).
GraphiQL will help you explore the schema as well as autocomplete your query as you type.
The GraphiQL instance is not hooked up to any data source!
Pressing the ▶️ button to execute the query will return `null` if there are no errors.
### 
[​](https://docs.attio.com/sdk/graphql/graphql#query-composing-example)
Query composing example
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/graphiql-light.gif) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/graphiql-dark.gif)
## 
[​](https://docs.attio.com/sdk/graphql/graphql#example-queries)
Example Queries
Get information about the current user
Copy
```
query getCurrentUser {
  currentUser {
    id
    name
    email
  }
}
```

Get email addresses for the current person record
Copy
```
query getPersonEmailAddresses($recordId: String!) {
  person(id: $recordId) {
    email_addresses
  }
}
```

Get the names and email addresses of people at the current company record
Copy
```
query getTeam($recordId: String!) {
  company(id: $recordId) {
    team {
      name {
        full_name
      }
      email_addresses
    }
  }
}
```

## 
[​](https://docs.attio.com/sdk/graphql/graphql#typescript-code-gen)
TypeScript Code-Gen
`runQuery()` and `useQuery()` will accept just a `string` as your query, but if you write your query in a separate file with the `.graphql` or `.gql` extension, you can then `import` your query into your TypeScript file. If you pass the imported query to these functions, your results will be strongly typed. The code generator will look for query files as long as you are runnning `npx attio dev`.
Let’s look at an example:
getCurrentUser.graphql
getCurrentUser.graphql.d.ts
usage.tsx
Copy
```
query getCurrentUser {
  currentUser {
    id
    name
    email
  }
}
```

## 
[​](https://docs.attio.com/sdk/graphql/graphql#custom-attributes)
Custom Attributes
Custom attributes can be loaded via GraphQL with their slug. The slug can be found under the kebab menu for the custom attribute in Workspace Settings.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/copy-slug-light.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/copy-slug-dark.png)
You can then use that slug in your GraphQL query like so:
get-bluesky.graphql
Copy
```
query getBlueSky($recordId: String!, $slug: String!) {
    person(id: $recordId) {
        attribute(slug: $slug) {
            __typename
            ... on TextValue {
                value
            }
        }
    }
}
```

You _must_ include `__typename` and the `... on` syntax to match the type of the attribute you are querying.
To please TypeScript, you will need check the `__typename` before reading the value.
Copy
```
const {person} = useQuery(getBlueSky, {recordId, slug: "bluesky"})
const blueSkyValue = person?.attribute?.__typename === "TextValue" ? person.attribute.value : null
```

## 
[​](https://docs.attio.com/sdk/graphql/graphql#advanced-usage)
Advanced Usage
### 
[​](https://docs.attio.com/sdk/graphql/graphql#fragments)
Fragments
Some queries can return multiple types of objects. The way this is handled in GraphQL is with [fragments](https://graphql.org/learn/queries/#fragments) and by querying `__typename` and then `switch`ing on its value.
The `record` query takes a record id and an object type and returns the matching object. Those variables happen to be _exactly_ what the `onTrigger()` function on our [record action](https://docs.attio.com/sdk/actions/record-action) is given.
get-record.gql
example-record-action.tsx
example-record-action.jsx
Copy
```
query getRecord($recordId: String!, $object: String!) {
  record(id: $recordId, object: $object) {
    id
    __typename
    url
    ...PersonFragment
    ...CompanyFragment
    ...DealFragment
    ...UserFragment
    ...WorkspaceFragment
  }
}
fragment PersonFragment on Person {
personName: name {
full_name
}
}
fragment CompanyFragment on Company {
companyName: name
}
fragment DealFragment on Deal {
dealName: name
}
fragment UserFragment on UserRecord {
person {
...PersonFragment
}
}
fragment WorkspaceFragment on WorkspaceRecord {
workspaceName: name
}
```

Was this page helpful?
YesNo
[Form schema](https://docs.attio.com/sdk/form-schema)[runQuery()](https://docs.attio.com/sdk/graphql/run-query)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [API](https://docs.attio.com/sdk/graphql/graphql#api)
  * [runQuery](https://docs.attio.com/sdk/graphql/graphql#runquery)
  * [useQuery](https://docs.attio.com/sdk/graphql/graphql#usequery)
  * [Writing GraphQL Queries](https://docs.attio.com/sdk/graphql/graphql#writing-graphql-queries)
  * [Query composing example](https://docs.attio.com/sdk/graphql/graphql#query-composing-example)
  * [Example Queries](https://docs.attio.com/sdk/graphql/graphql#example-queries)
  * [TypeScript Code-Gen](https://docs.attio.com/sdk/graphql/graphql#typescript-code-gen)
  * [Custom Attributes](https://docs.attio.com/sdk/graphql/graphql#custom-attributes)
  * [Advanced Usage](https://docs.attio.com/sdk/graphql/graphql#advanced-usage)
  * [Fragments](https://docs.attio.com/sdk/graphql/graphql#fragments)


Assistant
Responses are generated using AI and may contain mistakes.
