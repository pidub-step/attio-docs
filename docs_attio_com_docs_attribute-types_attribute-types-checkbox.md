---
title: Checkbox - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-checkbox
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Checkbox - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-checkbox](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Checkbox
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
# Checkbox
Modelling boolean values
Checkbox attributes are used to represent boolean values (`true` and `false`). In the UI, they are presented to users as a checkbox, hence the name.
There are no predefined checkbox attributes on any of the standard objects. As a result, checkbox attributes will only be present when added by the user.
Checkbox attributes may only be single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#reading-values)
Reading values
If the checkbox is checked, you’ll get the `true` property back, otherwise it will be `false`. This attribute does not support null values.
Example: a checked attribute
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "checkbox",
  "value": true
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#writing-values)
Writing values
To write checkbox attribute values, you can use either the boolean values `true`/`false` or their string equivalents `"true"`/`"false"`.
We support setting these values directly as raw booleans/strings, or by using an object with a single key, `value`.
We only support single-select checkbox attributes, so you may always write checkbox values without wrapping the values in an array (array values containing a single element are also supported).
Using boolean
Using string
Using array
Using object
Copy
```
{
  "a_custom_checkbox_attribute": true
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#filtering)
Filtering
Checkbox attribute values can be filtered by true/false. If using explicit operators, only the `$eq` operator is supported. For example:
Records where checkbox is checked
Expanded format
Copy
```
{
  "filter": {
    "a_custom_checkbox_attribute": true
  }
}
```

Was this page helpful?
YesNo
[Actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference)[Currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
