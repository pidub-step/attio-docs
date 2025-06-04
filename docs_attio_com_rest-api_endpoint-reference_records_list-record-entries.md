---
title: List record entries - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/endpoint-reference/records/create-a-record
---

# List record entries - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Records
List record entries
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
# List record entries
List all entries, across all lists, for which this record is the parent.
Required scopes: `record_permission:read`, `object_configuration:read`, `list_entry:read`.
GET
/
v2
/
objects
/
{object}
/
records
/
{record_id}
/
entries
Try it
cURL
Python
JavaScript
PHP
Go
Java
Copy
```
curl --request GET \
  --url https://api.attio.com/v2/objects/{object}/records/{record_id}/entries \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "list_id": "33ebdbe9-e529-47c9-b894-0ba25e9c15c0",
      "list_api_slug": "hiring-engineering",
      "entry_id": "2e6e29ea-c4e0-4f44-842d-78a891f8c156",
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Path Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#parameter-object)
object
string
required
A UUID or slug identifying the object that the record belongs to.
Example:
`"people"`
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#parameter-record-id)
record_id
string
required
A UUID identifying the record.
Example:
`"891dcbfc-9141-415d-9b2a-2238a6cc012d"`
#### Query Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#parameter-limit)
limit
integer
The maximum number of results to return. The default is `100` and the maximum is `1000`. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`10`
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#parameter-offset)
offset
integer
The number of results to skip over before returning. The default is `0`. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`5`
#### Response
200 - application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-entries#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[List record attribute values](https://docs.attio.com/rest-api/endpoint-reference/records/list-record-attribute-values)[List all lists](https://docs.attio.com/rest-api/endpoint-reference/lists/list-all-lists)
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
curl --request GET \
  --url https://api.attio.com/v2/objects/{object}/records/{record_id}/entries \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "list_id": "33ebdbe9-e529-47c9-b894-0ba25e9c15c0",
      "list_api_slug": "hiring-engineering",
      "entry_id": "2e6e29ea-c4e0-4f44-842d-78a891f8c156",
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
