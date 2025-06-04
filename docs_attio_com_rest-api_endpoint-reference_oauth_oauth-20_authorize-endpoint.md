---
title: Authorize Endpoint - Attio Docs
url: https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/how-to/authentication
---

# Authorize Endpoint - Attio Docs

**Source:** [https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
OAuth 2.0
Authorize Endpoint
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
  * Standard objects
  * OAuth 2.0
    * [GETAuthorize Endpoint](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint)
    * [POSTToken Endpoint](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/token-endpoint)
    * [POSTIntrospect Endpoint](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/introspect-endpoint)


##### Webhook reference
  * Webhook events


OAuth 2.0
# Authorize Endpoint
Use open source libraries to perform OAuth 2.0. You can find a list of libraries here: <https://oauth.net/code/>
GET
/
authorize
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
  --url https://app.attio.com/authorize
```

302
Copy
```
{}
```

#### Query Parameters
[​](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint#parameter-client-id)
client_id
string
required
The client ID of your integration (this can be found in your integration settings page).
[​](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint#parameter-response-type)
response_type
enum<string>
required
The response type. This should always be `code`.
Available options:
`code`
[​](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint#parameter-redirect-uri)
redirect_uri
string
required
The URL to redirect to after the user has authorized the integration. This URL must exactly match one of the registered redirect URLs in your integration settings page.
[​](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint#parameter-state)
state
string
A random string to prevent CSRF attacks. You should set this when starting the OAuth flow and check that when the user is redirected back to your app that it matches this value.
#### Response
302 - application/json
After the user approves the connection, they are sent to the redirect_uri with an authorization code.
The response is of type `object`.
Was this page helpful?
YesNo
[List workspace records](https://docs.attio.com/rest-api/endpoint-reference/standard-objects/workspaces/list-workspace-records)[Token Endpoint](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/token-endpoint)
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
  --url https://app.attio.com/authorize
```

302
Copy
```
{}
```

Assistant
Responses are generated using AI and may contain mistakes.
