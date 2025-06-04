---
title: (Personal) name - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-personal-name
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# (Personal) name - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-personal-name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
(Personal) name
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
# (Personal) name
A person’s name
Name attributes represent a person’s name. They have three properties: `first_name`, `last_name` and `full_name`.
Only the person object has a `name` attribute. Name attributes cannot be created by users.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#reading-values)
Reading values
All three properties are present in responses:
Example: John Smith
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "personal-name",
  "first_name": "John",
  "last_name": "Smith",
  "full_name": "John Smith"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#writing-values)
Writing values
Attio provides two syntaxes for writing name values, a string syntax and an object syntax. If possible, we recommend using the object syntax as it provides full control over the name values you create.
When writing values using the object syntax, all three properties must be set.
Using object
Copy
```
{
  "name": {
    "first_name": "John",
    "last_name": "Smith",
    "full_name": "John Smith"
  }
}
```

When writing using a string, the string must match format ‘Last name(s), First name(s)’. Text without a comma is interpreted as solely comprising the first name. Further commas will be ignored and assumed to be part of the first name.
Using string
Copy
```
{
  "name": "Smith, John"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#filtering)
Filtering
You can filter by any of the properties, using these operators:
  * `$eq`
  * `$not_empty`
  * `$contains`, `$starts_with`, `$ends_with`


Using the implicit filter syntax, you can search for exact matches of `full_name`, otherwise any combination of property/operator.
People exactly named John Smith
...where first_name starts with "jo"
... where last_name is specified
Copy
```
{
  "filter": {
    "name": "John Smith"
  }
}
```

Was this page helpful?
YesNo
[Location](https://docs.attio.com/docs/attribute-types/attribute-types-location)[Number](https://docs.attio.com/docs/attribute-types/attribute-types-number)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
