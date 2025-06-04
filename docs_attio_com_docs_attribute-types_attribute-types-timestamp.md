---
title: Timestamp - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/docs/actors
---

# Timestamp - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-timestamp](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Timestamp
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
# Timestamp
A calendar date including time information, stored in UTC
Timestamp attributes represent a single, universal moment in time using the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. Time information is stored with nanosecond precision, and UTC is the assumed timezone if one is not provided. Timestamp values will always be returned in UTC.
Every Attio object has a `created_at` timestamp attribute, but users can also create their own custom timestamp attributes.
All timestamp attributes are single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#reading-values)
Reading values
Timestamp attributes have a single property, `value` (string).
Example: 24th November, 2023
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "date",
  "value": "2023-11-24T15:17:48.000000000Z"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#writing-values)
Writing values
Input values will be coerced into the full format. UTC is assumed if not specified. For example, the following input values would all be coerced to `"2023-01-02T13:00:00.000000000Z"`:
  * `"2023"`
  * `"2023-01"`
  * `"2023-01-02"`
  * `"2023-01-02T13:00"`
  * `"2023-01-02T13:00:00"`
  * `"2023-01-02T13:00:00.000000000"`
  * `"2023-01-02T15:00:00.000000000+02:00`


To write timestamp attribute values, you should specify the `value` property:
You may also pass an object with a single property, `value`.
Using string
Using object
Copy
```
{
  "my_timestamp_attribute": "2019-01-17T15:17:48.000000000Z"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#filtering)
Filtering
Timestamp attribute values can be filtered by their value. Unlike when writing timestamp values, both date and time components must be specified.
You can filter for an exact timestamp using the implicit syntax, or use the `$eq`,`$gt`,`$gte`,`$lt`,`$lte` operators with the explicit syntax.
Companies created on 2023-11-24 at 15:34:07.111222333Z
... after the year 2000
Copy
```
{
  "filter": {
    "created_at": "2023-11-24T15:34:07.111222333Z"
  }
}
```

Since timestamps are stored with nanosecond precision, it is often undesirable to look for an exact timestamp if you’re trying to filter records with a lower precision, e.g. in a given hour or day. Here, you should use two operators to set the upper and lower bounds of the query, remembering to use the inclusive `$gte` for the earlier bound and the exclusive `$lt` for the upper bound:
Companies created between 8am and 9am
... on 24th November
Copy
```
{
  "filter": {
    "created_at": {
      "$gte": "2023-11-24T08:00:00Z",
      "$lt":  "2023-11-24T09:00:00Z"
    }
  }
}
```

Was this page helpful?
YesNo
[Text](https://docs.attio.com/docs/attribute-types/attribute-types-text)[Actors](https://docs.attio.com/docs/actors)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
