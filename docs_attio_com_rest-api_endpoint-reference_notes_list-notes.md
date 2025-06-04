---
title: List notes - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/endpoint-reference/workspace-members/get-a-workspace-member
---

# List notes - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Notes
List notes
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
      * [GETList notes](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes)
      * [POSTCreate a note](https://docs.attio.com/rest-api/endpoint-reference/notes/create-a-note)
      * [GETGet a note](https://docs.attio.com/rest-api/endpoint-reference/notes/get-a-note)
      * [DELDelete a note](https://docs.attio.com/rest-api/endpoint-reference/notes/delete-a-note)
    * Tasks
    * Threads
    * Comments
    * Webhooks
    * Meta
  * Standard objects
  * OAuth 2.0


##### Webhook reference
  * Webhook events


Notes
# List notes
List notes for all records or for a specific record.
Required scopes: `note:read`, `object_configuration:read`, `record_permission:read`.
GET
/
v2
/
notes
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
  --url https://api.attio.com/v2/notes \
  --header 'Authorization: Bearer <token>'
```

200
404
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "note_id": "ff3f3bd4-40f4-4f80-8187-cd02385af424"
      },
      "parent_object": "people",
      "parent_record_id": "891dcbfc-9141-415d-9b2a-2238a6cc012d",
      "title": "Initial Prospecting Call Summary",
      "content_plaintext": "Introduction\nDate and time of the call\nParticipants\nPurpose of the call\nCustomer Background\nCompany overview (industry, size, location)\nKey business challenges\nCurrent software solutions (if any) and pain points",
      "content_markdown": "# Introduction\nDate and time of the call\nParticipants\nPurpose of the call\n\n## Customer Background\n- Company overview (industry, size, location)\n- Key business challenges\n- Current software solutions (if any) and pain points",
      "tags": [
        {
          "type": "workspace-member",
          "workspace_member_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
        },
        {
          "type": "record",
          "object": "people",
          "record_id": "891dcbfc-9141-415d-9b2a-2238a6cc012d"
        }
      ],
      "created_by_actor": {
        "type": "workspace-member",
        "id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

#### Authorizations
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#authorization-authorization)
Authorization
string
header
required
This API uses OAuth 2.0 with the authorization code grant flow.
#### Query Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#parameter-limit)
limit
integer
The maximum number of results to return. The default is `10` and the maximum is `50`. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`10`
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#parameter-offset)
offset
integer
The number of results to skip over before returning. The default is `0`. See the [full guide to pagination here](https://docs.attio.com/rest-api/how-to/pagination).
Example:
`5`
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#parameter-parent-object)
parent_object
string
The slug or ID of the parent object the notes belong to.
Example:
`"people"`
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#parameter-parent-record-id)
parent_record_id
string
The ID of the parent record the notes belong to.
Example:
`"891dcbfc-9141-415d-9b2a-2238a6cc012d"`
#### Response
200
200 404
application/json
Success
[​](https://docs.attio.com/rest-api/endpoint-reference/notes/list-notes#response-data)
data
object[]
required
Show child attributes
Was this page helpful?
YesNo
[Get a workspace member](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/get-a-workspace-member)[Create a note](https://docs.attio.com/rest-api/endpoint-reference/notes/create-a-note)
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
  --url https://api.attio.com/v2/notes \
  --header 'Authorization: Bearer <token>'
```

200
404
Copy
```
{
  "data": [
    {
      "id": {
        "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
        "note_id": "ff3f3bd4-40f4-4f80-8187-cd02385af424"
      },
      "parent_object": "people",
      "parent_record_id": "891dcbfc-9141-415d-9b2a-2238a6cc012d",
      "title": "Initial Prospecting Call Summary",
      "content_plaintext": "Introduction\nDate and time of the call\nParticipants\nPurpose of the call\nCustomer Background\nCompany overview (industry, size, location)\nKey business challenges\nCurrent software solutions (if any) and pain points",
      "content_markdown": "# Introduction\nDate and time of the call\nParticipants\nPurpose of the call\n\n## Customer Background\n- Company overview (industry, size, location)\n- Key business challenges\n- Current software solutions (if any) and pain points",
      "tags": [
        {
          "type": "workspace-member",
          "workspace_member_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
        },
        {
          "type": "record",
          "object": "people",
          "record_id": "891dcbfc-9141-415d-9b2a-2238a6cc012d"
        }
      ],
      "created_by_actor": {
        "type": "workspace-member",
        "id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
      },
      "created_at": "2022-11-21T13:22:49.061281000Z"
    }
  ]
}
```

Assistant
Responses are generated using AI and may contain mistakes.
