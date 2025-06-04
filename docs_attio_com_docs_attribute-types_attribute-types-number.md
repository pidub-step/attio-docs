---
title: Number - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-number
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Number - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-number](https://docs.attio.com/docs/attribute-types/attribute-types-number)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Number
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Get started
  * [Overview](https://docs.attio.com/docs/overview)


##### Core concepts
  * [Objects and lists](https://docs.attio.com/docs/objects-and-lists)
  * [Users and workspaces](https://docs.attio.com/docs/users-and-workspaces)
  * Standard objects
  * Attribute types
    * [Overview](https://docs.attio.com/docs/attribute-types/attribute-types)
    * [Actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference)
    * [Checkbox](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox)
    * [Currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency)
    * [Date](https://docs.attio.com/docs/attribute-types/attribute-types-date)
    * [Domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain)
    * [Email address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address)
    * [Interaction](https://docs.attio.com/docs/attribute-types/attribute-types-interaction)
    * [Location](https://docs.attio.com/docs/attribute-types/attribute-types-location)
    * [(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)
    * [Number](https://docs.attio.com/docs/attribute-types/attribute-types-number)
    * [Phone number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number)
    * [Rating](https://docs.attio.com/docs/attribute-types/attribute-types-rating)
    * [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference)
    * [Select](https://docs.attio.com/docs/attribute-types/attribute-types-select)
    * [Status](https://docs.attio.com/docs/attribute-types/attribute-types-status)
    * [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text)
    * [Timestamp](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp)


##### Further reading
  * [Actors](https://docs.attio.com/docs/actors)
  * [Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)
  * [Default values](https://docs.attio.com/docs/default-values)
  * [Archiving vs deleting](https://docs.attio.com/docs/archiving-vs-deleting)


Attribute types
# Number
Quantities, sums and metrics
Number attributes store floating point numbers with up to four decimal places of precision.
An example of a number attribute is the `twitter_follower_count` attribute on both the company and person objects.
Only single-select number attributes are supported.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-number#reading-values)
Reading values
Number attribute values have a `value` property:
Example: 14 Twitter followers
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "number",
  "value": 14
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-number#writing-values)
Writing values
To write number values, simply pass your desired number, either as an integer or a float. Alternatively, you can use an object with a single `value` property.
Using number
Using object
Copy
```
{
  "a_custom_number_attribute": 3.1415
}
```

Please note that `twitter_follower_count` is a system attribute and cannot be written to from the API.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-number#filtering)
Filtering
Numbers can be filtered by the operators `$eq`, `$gte`, `$gt`,`$lte`,`$lt`. The implicit syntax does an exact equality check:
Finding records with 14 Twitter followers
... with more than 1000 followers
Copy
```
{
  "filter": {
    "twitter_follower_count": 14
  }
}
```

Was this page helpful?
YesNo
[(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)[Phone number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-number#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-number#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-number#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
