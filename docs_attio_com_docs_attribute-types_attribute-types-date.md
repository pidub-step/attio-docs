---
title: Date - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-date
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Date - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-date](https://docs.attio.com/docs/attribute-types/attribute-types-date)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Date
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
# Date
A timezone-less calendar date
Date attributes are used to represent a single calendar year, month and day, independent of timezone. Attio exclusively works with the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format, i.e. `YYYY-MM-DD` e.g. `2023-11-24`.
There is only one default example of a date attribute, `foundation_date` on the company object.
Date attributes can only be single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-date#reading-values)
Reading values
Date attributes have a single property, `value` (a string).
Example: 24th November, 2023
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "date",
  "value": "2023-11-24"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-date#writing-values)
Writing values
Date values can be written by passing an ISO 8601 date string.
If hours, months, seconds or timezones are provided, they will be trimmed. For example:
  * `'2023'` → `'2023-01-01'`
  * `'2023-01'` → `'2023-01-01'`
  * `'2023-01-02'` → `'2023-01-02'`
  * `'2023-01-02T13:00'` → `'2023-01-02'`
  * `'2023-01-02T14:00:00'` → `'2023-01-02'`
  * `'2023-01-02T15:00:00.000000000'` → `'2023-01-02'`
  * `'2023-01-02T15:00:00.000000000+02:00'` → `'2023-01-02'`


If a timezone is provided that would result in a different calendar date in UTC, the date will be coerced to UTC and then the timezone component will be trimmed. For example, the value `'2023-01-02T23:00:00-10:00'` will be returned as `'2023-01-03'`.
As date values are always single-select, you may write values either by passing the date string directly, or by wrapping a single value in an array.
You may also write date values using an object with a single `value` key.
Using string
Using object
Copy
```
{
  "foundation_date": "2004-07-29"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-date#filtering)
Filtering
Date attribute values can be filtered by their value. You can filter for an exact date using the implicit syntax, or use the `$eq`,`$gt`,`$gte`,`$lt`,`$lte` operators with the explicit syntax.
Companies founded on 2023-11-24
Companies formed after the year 2000
Copy
```
{
  "filter": {
    "foundation_date": "2023-11-24"
  }
}
```

Was this page helpful?
YesNo
[Currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency)[Domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-date#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-date#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-date#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
