---
title: How to paginate API results - Attio Docs
url: https://docs.attio.com/rest-api/how-to/pagination
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# How to paginate API results - Attio Docs

**Source:** [https://docs.attio.com/rest-api/how-to/pagination](https://docs.attio.com/rest-api/how-to/pagination)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
How-to guides
How to paginate API results
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
# How to paginate API results
Retrieving particular ranges of data
API endpoints which are expected to return large numbers of results will use pagination to return a limited number of items at a time.
We use two parameters to provide pagination functionality: `limit` and `offset`.
  * `limit` controls the maximum number of results that an endpoint can return. The default value for limit is documented on each specific endpoint.
  * `offset` controls how many results to skip over in your results. By default, it is always 0.


When querying all results, your initial call should pass an offset of 0. If the number of results you receive is less than the limit you passed (or the default limit if none was passed explicitly), you have reached the end of the result set and can end pagination. Otherwise, make another API call with a new offset, set to the previous `offset` + `limit` to get the next page, and then repeat until you are at the end of the list.
For example, if there were 122 records available, your queries would look something like this:
Copy
```
GET /v2/objects/people/records?limit=50             # Results 1 to 50
GET /v2/objects/people/records?limit=50&offset=50   # Results 51 to 100
GET /v2/objects/people/records?limit=50&offset=100  # Results 101 to 122, less than limit, stop here
```

Was this page helpful?
YesNo
[How to apply filters and sorts](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)[How to configure webhooks](https://docs.attio.com/rest-api/how-to/webhooks)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
