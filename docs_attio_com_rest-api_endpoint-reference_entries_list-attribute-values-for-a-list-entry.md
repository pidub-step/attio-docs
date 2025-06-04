---
title: List attribute values for a list entry - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members
---

# List attribute values for a list entry - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Entries
List attribute values for a list entry
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
    * Lists
    * Entries
      * [POSTList entries](https://docs.attio.com/rest-api/endpoint-reference/entries/list-entries)
      * [PUTAssert a list entry by parent](https://docs.attio.com/rest-api/endpoint-reference/entries/assert-a-list-entry-by-parent)
      * [POSTCreate an entry (add record to list)](https://docs.attio.com/rest-api/endpoint-reference/entries/create-an-entry-add-record-to-list)
      * [GETGet a list entry](https://docs.attio.com/rest-api/endpoint-reference/entries/get-a-list-entry)
      * [PUTUpdate a list entry (overwrite multiselect values)](https://docs.attio.com/rest-api/endpoint-reference/entries/update-a-list-entry-overwrite-multiselect-values)
      * [DELDelete a list entry](https://docs.attio.com/rest-api/endpoint-reference/entries/delete-a-list-entry)
      * [PATCHUpdate a list entry (append multiselect values)](https://docs.attio.com/rest-api/endpoint-reference/entries/update-a-list-entry-append-multiselect-values)
      * [GETList attribute values for a list entry](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry)
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


Entries
# List attribute values for a list entry
Gets all values for a given attribute on a list entry. If the attribute is historic, this endpoint has the ability to return all historic values using the `show_historic` query param.
Required scopes: `list_entry:read`, `list_configuration:read`.
GET
/
v2
/
lists
/
{list}
/
entries
/
{entry_id}
/
attributes
/
{attribute}
/
values
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
  --url https://api.attio.com/v2/lists/{list}/entries/{entry_id}/attributes/{attribute}/values \
  --header 'Authorization: Bearer <token>'
```

200
400
404
Copy
```
{
  "data": [
    {
      "active_from": "2023-01-01T15:00:00.000000000Z",
      "active_until": "2023-01-01T15:00:00.000000000Z",
      "created_by_actor": {
        "type": "workspace-member",
        "id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "referenced_actor_type": "workspace-member",
      "referenced_actor_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b",
      "attribute_type": "actor-reference"
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Path Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-list)
list
string
required
A UUID or slug identifying the list the entry is in.
Example:
`"enterprise_sales"`
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-entry-id)
entry_id
string
required
A UUID identifying the entry.
Example:
`"2e6e29ea-c4e0-4f44-842d-78a891f8c156"`
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-attribute)
attribute
string
required
A UUID or slug to identify the attribute you want to query values on.
Example:
`"41252299-f8c7-4b5e-99c9-4ff8321d2f96"`
#### Query Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-show-historic)
show_historic
boolean
default:false
If `true`, the endpoint will return all historic values for the attribute. If `false`, the endpoint will only return the currently active value(s). Defaults to `false`. Can only be set to `true` for attributes which support historic data; the endpoint will throw if set to `true` for non-historic attributes.
Example:
`true`
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-limit)
limit
integer
The maximum number of results to return. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`10`
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#parameter-offset)
offset
integer
The number of results to skip over before returning. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`5`
#### Response
200
200 400 404
application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry#response-data)
data
object[]
required
  * Option 1
  * Option 2
  * Option 3
  * Option 4
  * Option 5
  * Option 6
  * Option 7
  * Option 8
  * Option 9
  * Option 10
  * Option 11
  * Option 12
  * Option 13
  * Option 14
  * Option 15
  * Option 16
  * Option 17


Show child attributes
Was this page helpful?
YesNo
[Update a list entry (append multiselect values)](https://docs.attio.com/rest-api/endpoint-reference/entries/update-a-list-entry-append-multiselect-values)[List workspace members](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members)
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
  --url https://api.attio.com/v2/lists/{list}/entries/{entry_id}/attributes/{attribute}/values \
  --header 'Authorization: Bearer <token>'
```

200
400
404
Copy
```
{
  "data": [
    {
      "active_from": "2023-01-01T15:00:00.000000000Z",
      "active_until": "2023-01-01T15:00:00.000000000Z",
      "created_by_actor": {
        "type": "workspace-member",
        "id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "referenced_actor_type": "workspace-member",
      "referenced_actor_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b",
      "attribute_type": "actor-reference"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
