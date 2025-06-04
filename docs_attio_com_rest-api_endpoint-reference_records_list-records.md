---
title: List records - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/records/list-records
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/endpoint-reference/records/create-a-record
---

# List records - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/records/list-records](https://docs.attio.com/rest-api/endpoint-reference/records/list-records)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Records
List records
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Introduction
  * [Overview](https://docs.attio.com/rest-api/overview)


##### How-to guides
  * [How to authenticate requests](https://docs.attio.com/rest-api/how-to/authentication)
  * [How to handle rate limits](https://docs.attio.com/rest-api/how-to/rate-limiting)
  * [How to apply filters and sorts](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)
  * [How to paginate API results](https://docs.attio.com/rest-api/how-to/pagination)
  * [How to configure webhooks](https://docs.attio.com/rest-api/how-to/webhooks)


##### Tutorials
  * [Connect an app to Attio through OAuth](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth)


##### Endpoint reference
  * [OpenAPI](https://docs.attio.com/rest-api/endpoint-reference/openapi)
  * Core endpoints
    * Objects
    * Attributes
    * Records
      * [POSTList records](https://docs.attio.com/rest-api/endpoint-reference/records/list-records)
      * [PUTAssert a record](https://docs.attio.com/rest-api/endpoint-reference/records/assert-a-record)
      * [POSTCreate a record](https://docs.attio.com/rest-api/endpoint-reference/records/create-a-record)
      * [GETGet a record](https://docs.attio.com/rest-api/endpoint-reference/records/get-a-record)
      * [PUTUpdate a record (overwrite multiselect values)](https://docs.attio.com/rest-api/endpoint-reference/records/update-a-record-overwrite-multiselect-values)
      * [DELDelete a record](https://docs.attio.com/rest-api/endpoint-reference/records/delete-a-record)
      * [PATCHUpdate a record (append multiselect values)](https://docs.attio.com/rest-api/endpoint-reference/records/update-a-record-append-multiselect-values)
      * [GETList record attribute values](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-attribute-values)
      * [GETList record entries](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries)
    * Lists
    * Entries
    * Workspace members
    * Notes
    * Tasks
    * Threads
    * Comments
    * Webhooks
    * Meta
  * Standard objects
  * OAuth 2.0


##### Webhook reference
  * Webhook events


Records
# List records
Lists people, company or other records, with the option to filter and sort results.
Required scopes: `record_permission:read`, `object_configuration:read`.
POST
/
v2
/
objects
/
{object}
/
records
/
query
Try it
cURL
Python
JavaScript
PHP
Go
Java
Copy
```
curl --request POST \
  --url https://api.attio.com/v2/objects/{object}/records/query \
  --header 'Authorization: Bearer <token>' \
  --header 'Content-Type: application/json' \
  --data '{
  "filter": {
    "name": "Ada Lovelace"
  },
  "sorts": [
    {
      "direction": "asc",
      "attribute": "name",
      "field": "last_name"
    }
  ],
  "limit": 500,
  "offset": 0
}'
```

200
400
404
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "object_id": "97052eb9-e65e-443f-a297-f2d9a4a7f795",
        "record_id": "bf071e1f-6035-429d-b874-d83ea64ea13b"
      },
      "created_at": "2022-11-21T13:22:49.061281000Z",
      "web_url": "https://app.attio.com/salarya/person/bf071e1f-6035-429d-b874-d83ea64ea13b",
      "values": {}
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Path Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#parameter-object)
object
string
required
A UUID or slug to identify the object to list records for.
Example:
`"people"`
#### Body
application/json
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#body-filter)
filter
object
An object used to filter results to a subset of results. See the [full guide to filtering and sorting here](https://docs.attio.com/rest-api/how-to/filtering-and-sorting).
Example:
```
{ "name": "Ada Lovelace" }
```

[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#body-sorts)
sorts
object[]
An object used to sort results. See the [full guide to filtering and sorting here](https://docs.attio.com/rest-api/how-to/filtering-and-sorting).
  * Option 1
  * Option 2


Show child attributes
Example:
```
[  
  {  
    "direction": "asc",  
    "attribute": "name",  
    "field": "last_name"  
  }  
]
```

[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#body-limit)
limit
number
The maximum number of results to return. Defaults to 500. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`500`
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#body-offset)
offset
number
The number of results to skip over before returning. Defaults to 0. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`0`
#### Response
200
200 400 404
application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-records#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[Update a status](https://docs.attio.com/rest-api/endpoint-reference/attributes/update-a-status)[Assert a record](https://docs.attio.com/rest-api/endpoint-reference/records/assert-a-record)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
cURL
Python
JavaScript
PHP
Go
Java
Copy
```
curl --request POST \
  --url https://api.attio.com/v2/objects/{object}/records/query \
  --header 'Authorization: Bearer <token>' \
  --header 'Content-Type: application/json' \
  --data '{
  "filter": {
    "name": "Ada Lovelace"
  },
  "sorts": [
    {
      "direction": "asc",
      "attribute": "name",
      "field": "last_name"
    }
  ],
  "limit": 500,
  "offset": 0
}'
```

200
400
404
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "object_id": "97052eb9-e65e-443f-a297-f2d9a4a7f795",
        "record_id": "bf071e1f-6035-429d-b874-d83ea64ea13b"
      },
      "created_at": "2022-11-21T13:22:49.061281000Z",
      "web_url": "https://app.attio.com/salarya/person/bf071e1f-6035-429d-b874-d83ea64ea13b",
      "values": {}
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
