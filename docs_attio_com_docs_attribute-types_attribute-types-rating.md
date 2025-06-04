---
title: Rating - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-rating
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Rating - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-rating](https://docs.attio.com/docs/attribute-types/attribute-types-rating)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Rating
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
# Rating
Star ratings from 0 to 5
Rating attributes are a numeric value from 0 to 5. In the UI, they are presented as a proportion of 5 stars.
There are no default rating attributes in Attio, but they can be created by users and in the API.
Only single-select rating attributes are permitted.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-rating#reading-values)
Reading values
Rating attribute values have a `value` property:
Example: 3 out of 5 stars
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "rating",
  "value": 3
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-rating#writing-values)
Writing values
To write rating values, you can either pass an integer directly, or an object with a single key, `value`.
As all rating attributes are single-select, you may pass the value directly or as an array containing a single element.
Using number
Using object
Copy
```
{
  "performance": 4
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-rating#filtering)
Filtering
Ratings can be filtered by the operators `$eq`, `$gte`, `$gt`,`$lte`,`$lt`. The implicit syntax does an exact equality check:
Finding records rated 4 stars
... with more than 3 stars
Copy
```
{
  "filter": {
    "performance": 4
  }
}
```

Was this page helpful?
YesNo
[Phone number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number)[Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-rating#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-rating#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-rating#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
