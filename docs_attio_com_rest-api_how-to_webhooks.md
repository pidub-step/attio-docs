---
title: How to configure webhooks - Attio Docs
url: https://docs.attio.com/rest-api/how-to/webhooks
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# How to configure webhooks - Attio Docs

**Source:** [https://docs.attio.com/rest-api/how-to/webhooks](https://docs.attio.com/rest-api/how-to/webhooks)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
How-to guides
How to configure webhooks
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
# How to configure webhooks
Responding to changes in real-time
Webhooks allow you to subscribe to changes that happen in Attio and then receive real-time HTTP requests to a chosen target URL to notify you of these changes.
This pattern can be useful in a wide range of contexts, but is often implemented by those who want to build real-time data syncs (e.g. an ETL pipeline) or fire automations in a timely manner (e.g. Attio’s own Zapier integration is powered by webhooks).
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#creating-webhooks)
Creating webhooks
There are two places you can create webhooks: in our settings pages, and the API.
### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#creating-using-the-api)
Creating using the API
We offer a range of endpoints for creating, updating, deleting and viewing webhooks. You can find these endpoints in the [webhooks API reference](https://docs.attio.com/rest-api/endpoint-reference/webhooks).
Creating webhooks over the API is essential for those building integrations for Attio that will operate for many customers.
The webhook APIs also allow you to utilise our powerful filtering functionality (see “Filtering” section below).
### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#creating-using-settings-page)
Creating using settings page
You can create webhooks for an integration in the developer settings page.
Please note that webhooks created with tokens that were created through our OAuth sign up flow will not be shown in the developer settings page.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#authenticating)
Authenticating
When receiving webhooks, you should ensure that the request came from us. We cryptographically sign every webhook request using your webhook secret, and include it as HTTP header called `Attio-Signature` (this is duplicated as `X-Attio-Signature` to support legacy middleware).
The `Attio-Signature` value is calculated using a SHA256 HMAC of the request body using your webhook secret as the secret. The webhook’s secret is viewable inside the developer settings page and in the API response when creating the webhook.
To verify that webhooks came from us, you should also construct the signature on your side using the same algorithm, then verify that it matches the one in the request.
We encode the Attio-Signature as a hexadecimal string, and we only sign the request body, which we interpret as a UTF-8 string.
Here’s an example in NodeJS for verifying the webhook signature:
TypeScript
Copy
```
const webhookBody = request.body
const webhookSignature = request.headers["attio-signature"]
// Generate signature ourselves
const webhookSecret = "..."
const hmac = crypto.createHmac("sha256", webhookSecret)
hmac.update(webhookBody)
const expectedSignature = hmac.digest("hex")
// Compare signature
if (!crypto.timingSafeEqual(webhookSignature, expectedSignature)) {
    throw new Error("Invalid signature")
}
```

## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#https)
HTTPS
Webhooks must target URLs secured with HTTPS. This is because targeting URLs using HTTP reveals the confidential content of webhooks to the public internet. In addition to exposing your data to ‘man in the middle’ attacks, webhooks delivered via HTTP can be read at any point in the journey to your server, for example, by cloud providers or logging services. Ensuring your target URL is encrypted with HTTPS keeps your data secure.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#idempotency)
Idempotency
Webhooks guarantee at-least-once message delivery. Occasionally, due to network instability, Attio may send duplicate messages. To help deduplicate messages, Attio includes an `Idempotency-Key` header which will be different for each message, but the same between retries and redeliveries.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#delivery-attempts)
Delivery attempts
If you’re receiving many duplicate messages, it may mean you’re not acknowledging them properly. Attio will mark a delivery as successful if the response code is within the 200-299 range (for example `200` or `202`). If you answer with any other code, Attio will retry delivery of the message up to 10 times with an exponential back-off, which will happen over approximately 3 days in total; after which, the webhook will be marked as degraded and we’ll send you an email.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#ip-addresses)
IP addresses
We recommend using the request signature to validate the request instead of relying on IP allowlisting. This will mean that your integration does not require maintenance if we add new IP addresses.
Attio delivers webhooks from a fixed set of IP addresses. In some environments with restrictive firewalls it might be necessary to allowlist these IPs, and from time to time we might need to add a new IP Address to our list. We’ll endeavour to provide you with as much notice as possible before we change these.
Attio webhooks egress IP addresses
Copy
```
34.76.181.69
35.189.212.204
35.190.200.137
104.199.25.43
35.205.134.181
34.77.170.251
104.155.38.31
35.240.20.227
35.205.218.25
34.77.63.171
35.195.180.236
104.199.20.44
34.78.73.25
34.77.104.7
35.205.250.54
34.78.179.95
35.189.210.201
34.77.106.144
104.155.115.39
34.78.11.169
35.241.187.180
35.240.124.129
35.241.222.75
35.195.62.68
```

## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#delivery-rate-limiting)
Delivery rate limiting
To avoid overwhelming your server with a large burst of requests, Attio smoothes out webhook delivery with a rate limiter. Rate limiting is implemented on a per-target URL basis. We restrict delivery per URL to a maximum of 25 requests per second. Please contact support if you would like this number adjusted for your workspace.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#testing-webhooks)
Testing webhooks
The developer settings page provides the ability to deliver test payloads to your webhook’s target URL.
When building an integration that uses webhooks, this lets you quickly test that your integration is functioning, without having to modify real data in your workspace.
To send a test payload:
  1. Navigate to an integration the developer settings page and select an integration.
  2. Open an existing webhook or create a new one inside your integration.
  3. Ensure your webhook is subscribed to the events that you want to test.
  4. Open the dropdown next to the event you want to send a test payload for and select “Send test event to target URL”.
  5. We’ll make an HTTP request to your target URL.


We populate test payloads with real data from your workspace. For example, when testing the `note.created` event, we’ll set the `note_id` property on the payload to correspond to a real note you have created. In cases where this is not possible, for example if you have no notes in your system, we’ll fallback to randomly generated fake data.
Please note that filters are not taken into account when generating test data.
## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#filtering)
Filtering
To reduce the amount of webhooks you receive and help avoid writing client-side filtering code, it’s possible to define rules to further limit the events Attio will send. Filters work by taking the payload of the generated webhook event, and running it against a set of rules that you define.
For example, you might only care about updates to a particular attribute on a particular list, or about new notes on people but not companies.
Our API will validate that the filter syntax you have provided is valid. Filters are currently only editable and viewable over the API.
### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#filter-syntax)
Filter syntax
The filter syntax can be broken down into the following components.
#### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#logical-joins-or)
Logical joins (and,and, and,or)
  * An `$and` filter passes when all operations match the payload.
  * An `$or` filter passes when at least one operation matches the payload.


#### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#operations)
Operations
  * `field`: Specifies which property of the webhook payload to apply the filter condition on. It supports nested properties using dot notation, such as `"actor.type"` and `"actor.id"`.
  * `operator`: The operator property defines the comparison operation to be used in the filter operation. The currently supported operators are: `"equals"` and `"not_equals"`
  * `value`: The value property specifies the value to compare against the chosen payload field using the operator.


### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#filter-examples)
Filter examples
**Subscribe to changes on the “Sales” list or the “Hiring” list**
JSON
Copy
```
{
    "$or": [
        {
            "field": "id.list_id",
            "operator": "equals",
            "value": "2a33abd4-dae7-49d0-b6ed-b09da0d8f00b" // <-- Sales List ID
        },
        {
            "field": "id.list_id",
            "operator": "equals",
            "value": "9d74e5c9-41eb-4d5c-b70b-d346ef15e13e" // <-- Hiring List ID
        }
    ]
}
```

**Subscribe to changes to the value of the “Status” attribute of the Sales list**
JSON
Copy
```
{
    "$and": [
        {
            "field": "id.list_id",
            "operator": "equals",
            "value": "2a33abd4-dae7-49d0-b6ed-b09da0d8f00b" // <-- Sales List ID
        },
        {
            "field": "id.attribute_id",
            "operator": "equals",
            "value": "c65a3828-b5e9-46d9-afe6-c8319ae46412" // <-- Status Attribute ID
        }
    ]
}
```

**Subscribe to changes made by workspace members**
JSON
Copy
```
{
    "$and": [
        {
            "field": "actor.type",
            "operator": "equals",
            "value": "workspace-member"
        }
    ]
}
```

**Subscribe to all events**
JSON
Copy
```
{"filter": null}
```

## 
[​](https://docs.attio.com/rest-api/how-to/webhooks#migrating-from-v1-webhooks)
Migrating from V1 webhooks
Webhooks were supported over the V1 API and have now been replaced by updated V2 Webhooks. Using V2 webhooks will allow you to use our new filtering system and receive payloads which are consistent with the rest of the V2 API (e.g. we now refer to “lists” instead of “collections”).
V1 Webhook endpoints and even types will eventually be removed. Therefore, we recommend upgrading to use V2 Webhooks at your soonest convenience.
### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#event-types)
Event Types
The following V1 Webhook events should be considered deprecated:
Copy
```
entry.created
entry-attribute.updated
entry.deleted
```

These have been replaced by the following V2 event types which fire under exactly the same circumstances.
Copy
```
entry.created → list-entry.created
entry-attribute.updated → list-entry.updated
entry.deleted → list-entry.deleted
```

### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#payloads)
Payloads
Your code will also need to take into account the changes in the payloads of the above events.
Below are examples of payloads with V1 events and V2.
#### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#entry-created)
entry.created
Copy
```
// V1
{
  "event_type": "entry.created",
  "collection_id": "69815e80-949c-44c9-92be-242457a4be28",
  "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e"
}
// V2
{
  "event_type": "list-entry.created",
  "id": {
    "workspace_id": "928e88d9-de10-4e1c-9aef-36b07cb4260d", // New
    "list_id": "69815e80-949c-44c9-92be-242457a4be28", // Previously, collection_id
    "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e", // Previously, entry_id
  },
  "parent_object_id": "7298c9b4-63ac-4b7e-8a74-4468d2e403a9", // New
  "parent_record_id": "6003a6aa-7122-45f1-b840-efe9231dfd06", // New
}
```

#### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#entry-attribute-updated)
entry-attribute.updated
Copy
```
// V1
{
  "event_type": "entry-attribute.updated",
  "collection_id": "69815e80-949c-44c9-92be-242457a4be28",
  "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e",
  "attribute_id": "18b7bb8c-fc41-4b70-be0b-0dea00b3ca23"
}
// V2
{
  "event_type": "list-entry.updated",
  "id": {
    "workspace_id": "928e88d9-de10-4e1c-9aef-36b07cb4260d", // New
    "list_id": "69815e80-949c-44c9-92be-242457a4be28", // Previously, collection_id
    "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e", // Previously, entry_id
    "attribute_id": "18b7bb8c-fc41-4b70-be0b-0dea00b3ca23", // Previously, attribute_id
  },
  "parent_object_id": "7298c9b4-63ac-4b7e-8a74-4468d2e403a9", // New
  "parent_record_id": "6003a6aa-7122-45f1-b840-efe9231dfd06", // New
}
```

#### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#entry-deleted)
entry.deleted
Copy
```
// V1
{
  "event_type": "entry.deleted",
  "collection_id": "69815e80-949c-44c9-92be-242457a4be28",
  "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e"
}
// V2
{
  "event_type": "list-entry.deleted",
  "id": {
    "workspace_id": "928e88d9-de10-4e1c-9aef-36b07cb4260d", // New
    "list_id": "69815e80-949c-44c9-92be-242457a4be28", // Previously, collection_id
    "entry_id": "861c1071-54ba-4d3d-b642-f72f7bcc8c7e", // Previously, entry_id
  },
  "parent_object_id": "7298c9b4-63ac-4b7e-8a74-4468d2e403a9", // New
  "parent_record_id": "6003a6aa-7122-45f1-b840-efe9231dfd06", // New
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/webhooks#step-by-step-migration-guide)
Step-by-step migration guide
The following guide assumes you are implementing a zero downtime migration. You are, of course, welcome to migrate without such a constraint.
  1. **Update your webhook server to handle V1 and V2 Events**. First, update the endpoints that handle the events we send you to deal with both V1 and V2 events.As there will be a brief overlap period where you receive both V1 and V2 events, you may wish to make your handler idempotent.
  2. **Add new events**. Create new subscriptions to replace your old ones. For example, if you previously had a subscription on the `"entry.created"` event type, add a new one for the `"list-entry.updated"` event type. V1 subscriptions used a static `"collection_id"` property to limit subscriptions to a particular List (formerly “Collection”). This functionality can be replaced using our new filter functionality.


For example, below is an example of a V1 subscription and its V2 replacement. These two subscriptions will respond to exactly the same changes in the system.
Copy
```
// V1
{
  "event_type": "entry.created",
  "collection_id": "738eefb5-d481-4aed-9735-ce918f279b74"
}
// V2
{
  "event_type": "list-entry.created",
  "filter": {
    "$and": [
      {
        "field": "id.list_id",
        "operator": "equals",
        "value": "d0a22439-5668-468a-b82a-f5988d9826f8"
      }
    ]
  }
}
```

Any automated subscription creation using V1 APIs should be moved over to use V2 APIs. You should also move delete and update endpoints over to the V2 endpoints.
  1. **Remove old events**. Your server should now be receiving both V1 and V2 events and responding to each correctly. Now that this is the case, you can go ahead and remove the V1 events using either the developer settings UI or the V1 delete endpoint.
  2. **Clean up any V1 handling code**. Now that you are no longer receiving V1 events, you are welcome to clean up any code on your servers that handled the V1 events.


Was this page helpful?
YesNo
[How to paginate API results](https://docs.attio.com/rest-api/how-to/pagination)[Connect an app to Attio through OAuth](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Creating webhooks](https://docs.attio.com/rest-api/how-to/webhooks#creating-webhooks)
  * [Creating using the API](https://docs.attio.com/rest-api/how-to/webhooks#creating-using-the-api)
  * [Creating using settings page](https://docs.attio.com/rest-api/how-to/webhooks#creating-using-settings-page)
  * [Authenticating](https://docs.attio.com/rest-api/how-to/webhooks#authenticating)
  * [HTTPS](https://docs.attio.com/rest-api/how-to/webhooks#https)
  * [Idempotency](https://docs.attio.com/rest-api/how-to/webhooks#idempotency)
  * [Delivery attempts](https://docs.attio.com/rest-api/how-to/webhooks#delivery-attempts)
  * [IP addresses](https://docs.attio.com/rest-api/how-to/webhooks#ip-addresses)
  * [Delivery rate limiting](https://docs.attio.com/rest-api/how-to/webhooks#delivery-rate-limiting)
  * [Testing webhooks](https://docs.attio.com/rest-api/how-to/webhooks#testing-webhooks)
  * [Filtering](https://docs.attio.com/rest-api/how-to/webhooks#filtering)
  * [Filter syntax](https://docs.attio.com/rest-api/how-to/webhooks#filter-syntax)
  * [Logical joins (or)](https://docs.attio.com/rest-api/how-to/webhooks#logical-joins-or)
  * [Operations](https://docs.attio.com/rest-api/how-to/webhooks#operations)
  * [Filter examples](https://docs.attio.com/rest-api/how-to/webhooks#filter-examples)
  * [Migrating from V1 webhooks](https://docs.attio.com/rest-api/how-to/webhooks#migrating-from-v1-webhooks)
  * [Event Types](https://docs.attio.com/rest-api/how-to/webhooks#event-types)
  * [Payloads](https://docs.attio.com/rest-api/how-to/webhooks#payloads)
  * [entry.created](https://docs.attio.com/rest-api/how-to/webhooks#entry-created)
  * [entry-attribute.updated](https://docs.attio.com/rest-api/how-to/webhooks#entry-attribute-updated)
  * [entry.deleted](https://docs.attio.com/rest-api/how-to/webhooks#entry-deleted)
  * [Step-by-step migration guide](https://docs.attio.com/rest-api/how-to/webhooks#step-by-step-migration-guide)


Assistant
Responses are generated using AI and may contain mistakes.
