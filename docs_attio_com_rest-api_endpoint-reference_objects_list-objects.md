---
title: List objects - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/endpoint-reference/openapi
---

# List objects - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects](https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Objects
List objects
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
      * [GETList objects](https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects)
      * [POSTCreate an object](https://docs.attio.com/rest-api/endpoint-reference/objects/create-an-object)
      * [GETGet an object](https://docs.attio.com/rest-api/endpoint-reference/objects/get-an-object)
      * [PATCHUpdate an object](https://docs.attio.com/rest-api/endpoint-reference/objects/update-an-object)
    * Attributes
    * Records
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


Objects
# List objects
Lists all system-defined and user-defined objects in your workspace.
Required scopes: `object_configuration:read`.
GET
/
v2
/
objects
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
  --url https://api.attio.com/v2/objects \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "object_id": "97052eb9-e65e-443f-a297-f2d9a4a7f795"
      },
      "api_slug": "people",
      "singular_noun": "Person",
      "plural_noun": "People",
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Response
200 - application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/objects/list-objects#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[OpenAPI](https://docs.attio.com/rest-api/endpoint-reference/openapi)[Create an object](https://docs.attio.com/rest-api/endpoint-reference/objects/create-an-object)
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
  --url https://api.attio.com/v2/objects \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "object_id": "97052eb9-e65e-443f-a297-f2d9a4a7f795"
      },
      "api_slug": "people",
      "singular_noun": "Person",
      "plural_noun": "People",
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
