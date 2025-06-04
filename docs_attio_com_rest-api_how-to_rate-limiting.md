---
title: How to handle rate limits - Attio Docs
url: https://docs.attio.com/rest-api/how-to/rate-limiting
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# How to handle rate limits - Attio Docs

**Source:** [https://docs.attio.com/rest-api/how-to/rate-limiting](https://docs.attio.com/rest-api/how-to/rate-limiting)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
How-to guides
How to handle rate limits
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
# How to handle rate limits
How to ensure your app handles rate limits gracefully
The Attio API applies rate limits to all API calls to ensure fair usage and maintain the availability and stability of the platform.
Our rate limit across the whole API is **100 requests per second** for read requests, **25 requests per second** for write requests. We may occasionally reduce the rate limit as part of incident response to protect our other systems, and we may also permanently lower it for specific APIs which handle a lot of data (this will be documented on the endpoint if so).
This means that your software should be prepared to receive this response, and handle it appropriately, even if you don’t currently anticipate making this many requests.
## 
[​](https://docs.attio.com/rest-api/how-to/rate-limiting#rate-limit-response)
Rate limit response
If you exceed the limit, you’ll get a special HTTP response, like this:
HTTP
Copy
```
HTTP/1.1 429 Too Many Requests
Retry-After: Tue, 23 May 2023 14:42:01 GMT
Content-Type: application/json
{
  "status_code": 429,
  "type": "rate_limit_error",
  "code": "rate_limit_exceeded",
  "message": "Rate limit exceeded, please try again later"
}
```

Rate limit responses always have the HTTP status code `429`. They also always include a `Retry-After` header, which is a date at which the limit resets (usually the following second), and they may also include additional debugging information in the JSON body.
### 
[​](https://docs.attio.com/rest-api/how-to/rate-limiting#handling-rate-limit-responses)
Handling rate limit responses
A rate limited response means that we have not processed the request, so it can be safely retried after the limit has reset. Typically this will be in the next clock second. Most programming languages offer a sleep command or equivalent that allows waiting for the reset time to elapse.
Alternatively, you might want to put the request into a background queue to be processed in a different execution thread later.
Was this page helpful?
YesNo
[How to authenticate requests](https://docs.attio.com/rest-api/how-to/authentication)[How to apply filters and sorts](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Rate limit response](https://docs.attio.com/rest-api/how-to/rate-limiting#rate-limit-response)
  * [Handling rate limit responses](https://docs.attio.com/rest-api/how-to/rate-limiting#handling-rate-limit-responses)


Assistant
Responses are generated using AI and may contain mistakes.
