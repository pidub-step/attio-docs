---
title: List webhooks - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/webhooks
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/how-to/webhooks
---

# List webhooks - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/webhooks](https://docs.attio.com/rest-api/endpoint-reference/webhooks)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Webhooks
List webhooks
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
    * Workspace members
    * Notes
    * Tasks
    * Threads
    * Comments
    * Webhooks
      * [GETList webhooks](https://docs.attio.com/rest-api/endpoint-reference/webhooks/list-webhooks)
      * [POSTCreate a webhook](https://docs.attio.com/rest-api/endpoint-reference/webhooks/create-a-webhook)
      * [GETGet a webhook](https://docs.attio.com/rest-api/endpoint-reference/webhooks/get-a-webhook)
      * [DELDelete a webhook](https://docs.attio.com/rest-api/endpoint-reference/webhooks/delete-a-webhook)
      * [PATCHUpdate a webhook](https://docs.attio.com/rest-api/endpoint-reference/webhooks/update-a-webhook)
    * Meta
  * Standard objects
  * OAuth 2.0


##### Webhook reference
  * Webhook events


Webhooks
# List webhooks
Get all of the webhooks in your workspace.
Required scopes: `webhook:read`.
GET
/
v2
/
webhooks
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
  --url https://api.attio.com/v2/webhooks \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "target_url": "https://example.com/webhook",
      "subscriptions": [
        {
          "event_type": "note.created",
          "filter": {
            "$and": [
              {
                "field": "parent_object_id",
                "operator": "equals",
                "value": "97052eb9-e65e-443f-a297-f2d9a4a7f795"
              }
            ]
          }
        }
      ],
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "webhook_id": "23e42eaf-323a-41da-b5bb-fd67eebda553"
      },
      "status": "active",
      "created_at": "2023-04-27T13:22:49.061281000Z"
    }
  ]
}
```

For more information about webhooks, checkout our [Using Webhooks](https://docs.attio.com/rest-api/how-to/webhooks) page.
#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/webhooks/list-webhooks#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Query Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/webhooks/list-webhooks#parameter-limit)
limit
integer
The maximum number of results to return, between 10 and 100, defaults to 10. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`10`
[​](https://docs.attio.com/rest-api/endpoint-reference/webhooks/list-webhooks#parameter-offset)
offset
integer
The number of results to skip over before returning, defaults to 0. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`5`
#### Response
200 - application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/webhooks/list-webhooks#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[Delete a comment](https://docs.attio.com/rest-api/endpoint-reference/comments/delete-a-comment)[Create a webhook](https://docs.attio.com/rest-api/endpoint-reference/webhooks/create-a-webhook)
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
  --url https://api.attio.com/v2/webhooks \
  --header 'Authorization: Bearer <token>'
```

200
Copy
```
{
  "data": [
    {
      "target_url": "https://example.com/webhook",
      "subscriptions": [
        {
          "event_type": "note.created",
          "filter": {
            "$and": [
              {
                "field": "parent_object_id",
                "operator": "equals",
                "value": "97052eb9-e65e-443f-a297-f2d9a4a7f795"
              }
            ]
          }
        }
      ],
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "webhook_id": "23e42eaf-323a-41da-b5bb-fd67eebda553"
      },
      "status": "active",
      "created_at": "2023-04-27T13:22:49.061281000Z"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
