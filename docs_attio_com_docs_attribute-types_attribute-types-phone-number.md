---
title: Phone number - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-phone-number
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Phone number - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-phone-number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Phone number
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
# Phone number
International telephone numbers
Phone number attributes represent telephone numbers. They are represented in [E164 format](https://en.wikipedia.org/wiki/E.164) and always prefixed with a country code.
The person object comes with a phone number attribute (`phone_numbers`), which is is a multi-select attribute, but users can also create their own phone number attributes on other objects or lists as well.
There are three properties on a phone number: `original_phone_number` (as inputted by the user), `country_code` (an ISO 3166-1 alpha-2 country code) and `normalized_phone_number` (as set by Attio). All properties are represented as strings.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#reading-values)
Reading values
Example: a US telephone number
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "phone-number",
  "original_phone_number": "+15558675309",
  "normalized_phone_number": "+15558675309",
  "country_code": "US"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#writing-values)
Writing values
You may either write phone number values as strings or objects. For both formats, you must provide sufficient information to identify the country code of the number.
For string values, the phone number must be prefixed with the area code, starting with ”+”.
Object values must include both a `original_phone_number` and `country_code` property. You may pass `null` to `country_code` if an area code prefix is provided as part of `original_phone_number`.
All values are validated against the E164 format.
Since the `phone_numbers` attribute is multi-select, you must always pass values as part of an array.
Using string
Setting phone number with country
Setting just the number
Copy
```
{
  "phone_numbers": ["+447777777777"]
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#filtering)
Filtering
Phone numbers can be filtered by equality or substrings (`$eq`,`$contains`,`$starts_with`,`$ends_with`). Note that the explicit property is called `phone_number`, internally Attio will use the normalized phone number for searching.
The `country_code` property can also be filtered by `$eq` and `$not_empty`.
People by exact phone number
... with US phone numbers
... with part of a phone number
Copy
```
{
  "filter": {
    "phone_numbers": "+15558675309"
  }
}
```

Was this page helpful?
YesNo
[Number](https://docs.attio.com/docs/attribute-types/attribute-types-number)[Rating](https://docs.attio.com/docs/attribute-types/attribute-types-rating)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
