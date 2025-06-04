---
title: How to authenticate requests - Attio Docs
url: https://docs.attio.com/rest-api/how-to/authentication
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# How to authenticate requests - Attio Docs

**Source:** [https://docs.attio.com/rest-api/how-to/authentication](https://docs.attio.com/rest-api/how-to/authentication)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
How-to guides
How to authenticate requests
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


##### Webhook reference
  * Webhook events


How-to guides
# How to authenticate requests
How to generate access tokens and make requests
In order to make requests to the Attio REST API, you need to generate an access token.
There are two ways to generate an access token:
  1. By implementing an OAuth 2.0 flow
  2. By generating an API key for your workspace


You should prefer the OAuth 2.0 flow if building an app for multiple workspaces. If you are building an app for a single workspace, you can manually generate an API key to make requests on behalf of that workspace only.
## 
[​](https://docs.attio.com/rest-api/how-to/authentication#generating-access-tokens)
Generating access tokens
### 
[​](https://docs.attio.com/rest-api/how-to/authentication#oauth-2-0)
OAuth 2.0
Attio implements the standard [OAuth 2.0 specification](https://datatracker.ietf.org/doc/html/rfc6749). You can find the reference for our OAuth authorize, token exchange and introspect endpoints [here](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint).
If you would prefer a tutorial on how to implement an OAuth 2.0 flow into an existing app, you can find one [here](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth).
### 
[​](https://docs.attio.com/rest-api/how-to/authentication#api-key)
API key
If you only need a token for a single workspace, you can generate an API key in the developer settings page of your apps. You can find docs on to do this [here](https://attio.com/help/apps/other-apps/generating-an-api-key).
## 
[​](https://docs.attio.com/rest-api/how-to/authentication#using-tokens)
Using tokens
Both OAuth access tokens and single-workspace access token are used in the same way. Pass the value of the token in the `Authorization` header of your requests like so.
Copy
```
Authorization: Bearer <access_token>
```

We also support [HTTP Basic Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization#basic_authentication), where the username is the token and the password is left blank. However, we recommend using Bearer authentication where possible.
### 
[​](https://docs.attio.com/rest-api/how-to/authentication#scopes)
Scopes
Both OAuth access tokens and single-workspace access tokens use scopes to control the resources that the token has access to and the actions that can be performed on those resources.
The possible scopes for OAuth and single-workspace access tokens are the same.
The reference documentation for each endpoint includes a “Required scopes” section that lists the scopes needed to call that endpoint.
When using an OAuth access token, the scopes are specified by configuring the scope settings for your app in the developer dashboard.
When using a single-workspace access token, the scopes are specified in the settings UI when generating the token. Scopes for single-workspace access tokens can also be modified on existing tokens.
Was this page helpful?
YesNo
[Overview](https://docs.attio.com/rest-api/overview)[How to handle rate limits](https://docs.attio.com/rest-api/how-to/rate-limiting)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Generating access tokens](https://docs.attio.com/rest-api/how-to/authentication#generating-access-tokens)
  * [OAuth 2.0](https://docs.attio.com/rest-api/how-to/authentication#oauth-2-0)
  * [API key](https://docs.attio.com/rest-api/how-to/authentication#api-key)
  * [Using tokens](https://docs.attio.com/rest-api/how-to/authentication#using-tokens)
  * [Scopes](https://docs.attio.com/rest-api/how-to/authentication#scopes)


Assistant
Responses are generated using AI and may contain mistakes.
