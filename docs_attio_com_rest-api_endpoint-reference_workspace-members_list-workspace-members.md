---
title: List workspace members - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/docs/users-and-workspaces
---

# List workspace members - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Workspace members
List workspace members
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
      * [GETList workspace members](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members)
      * [GETGet a workspace member](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/get-a-workspace-member)
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


Workspace members
# List workspace members
Lists all workspace members in the workspace.
Required scopes: `user_management:read`.
GET
/
v2
/
workspace_members
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
  --url https://api.attio.com/v2/workspace_members \
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
        "workspace_member_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "first_name": "Susan",
      "last_name": "Kare",
      "avatar_url": "https://lh3.googleusercontent.com/a/ABdFTp7z6OgAW9EqZx78wTqPfWClGCJCZXFjQfBG7rd9=s96-c",
      "email_address": "susan.kare@apple.com",
      "created_at": "2022-11-21T13:22:49.061281000Z",
      "access_level": "member"
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Response
200 - application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[List attribute values for a list entry](https://docs.attio.com/rest-api/endpoint-reference/entries/list-attribute-values-for-a-list-entry)[Get a workspace member](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/get-a-workspace-member)
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
  --url https://api.attio.com/v2/workspace_members \
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
        "workspace_member_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "first_name": "Susan",
      "last_name": "Kare",
      "avatar_url": "https://lh3.googleusercontent.com/a/ABdFTp7z6OgAW9EqZx78wTqPfWClGCJCZXFjQfBG7rd9=s96-c",
      "email_address": "susan.kare@apple.com",
      "created_at": "2022-11-21T13:22:49.061281000Z",
      "access_level": "member"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
