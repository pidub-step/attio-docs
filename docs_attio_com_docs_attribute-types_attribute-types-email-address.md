---
title: Email address - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-email-address
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Email address - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-email-address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Email address
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
# Email address
An email address
Email address attributes are a string referencing an internet email address. For example, an email address might be `"[email protected]"`. Like [domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain) attributes, we do some parsing of the email domain part, as well as validating the general shape of an email address overall.
It isn’t currently possible to create your own email address attributes. You’ll find only the multiselect `email_addresses` attribute on a person object, or the single attribute `email_address` attribute on the user standard object.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#reading-values)
Reading values
There are five properties available on this attribute:
  * `email_address` - the normalized form of the email address, this is the one you are most likely to use
  * `original_email_address` - the email as it was originally input to the system, without normalization
  * `email_domain` - the full domain part of the email address
  * `email_root_domain` - the root domain part of the email address
  * `email_local_specifier` - the local part of the email address


Example: person@company.com
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "email-address",
  "email_address": "[email protected]",
  "original_email_address": "[email protected]",
  "email_domain": "company.com",
  "email_root_domain": "company.com",
  "email_local_specifier": "person"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#writing-values)
Writing values
Email address values can be written by passing in a string of the email you would like to write.
We also support passing values with a single key, `email_address`.
We strictly validate that email addresses have valid domain and local part formats.
Attio will automatically infer the root domain, local specify and other properties available on read so there is no need to write them yourself.
If writing to a multi-select attribute, you must wrap your input values in an array.
Writing to email_addresses
Writing to email_address
Using object
Copy
```
{
  "email_addresses": ["[email protected]", "[email protected]"]
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#filtering)
Filtering
Email attribute values can be filtered by the `email_address`, `email_domain`, `email_root_domain` and `email_local_specifier` properties, and support several operators:
  * `$eq` for an exact match
  * `$contains` , `$starts_with` and `$ends_with`


In implicit mode, the `email_address` property is checked for equality, otherwise you can use the explicit syntax to combine the properties and operators above.
People where email_addresses=person@company.com
...where domain=attio.com
...where local part includes person
Copy
```
{
  "filter": {
    "email_addresses": "[email protected]"
  }
}
```

Was this page helpful?
YesNo
[Domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain)[Interaction](https://docs.attio.com/docs/attribute-types/attribute-types-interaction)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-email-address#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
