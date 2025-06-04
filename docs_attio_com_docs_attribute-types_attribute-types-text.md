---
title: Text - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-text
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Text - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-text](https://docs.attio.com/docs/attribute-types/attribute-types-text)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Text
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
# Text
Human-readable, unconstrained text inputs
Text attributes are the most common type of attribute, and usually represent unstructured or human-readable data. They have a max size of 10mb.
Examples of text attributes include the `description`, `facebook` or `instagram` attributes on company and person, or the `workspace_id` and `user_id` attributes on workspace/user. Please note that on person, the `name` attribute is a [(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name) attribute, but on company it’s a text attribute.
Text attributes are always single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-text#reading-values)
Reading values
Text attribute values have a single `value` property:
Example: 14 Twitter followers
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "text",
  "value": "A long time ago in a galaxy far, far away..."
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-text#writing-values)
Writing values
To write text attribute values, simply pass the string that you would like to set.
You may also pass an object with a single `value` property.
Using string
Using object
Copy
```
{
  "description": "Headquartered in New York City, Waystar Royco was founded by Logan Roy and operates in 50 countries across 4 continents"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-text#filtering)
Filtering
Text can be filtered by the operators `$eq`, `$in`, `$contains`, `$starts_with` and `$ends_with`. The implicit syntax does an exact equality (`$eq`) check:
Finding companies with an exact description
... which starts with a prefix
... which contains a keyword
...where record_id is one of supplied values
Copy
```
{
  "filter": {
    "description": "An exact match"
  }
}
```

Was this page helpful?
YesNo
[Status](https://docs.attio.com/docs/attribute-types/attribute-types-status)[Timestamp](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-text#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-text#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-text#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
