---
title: Domain - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-domain
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Domain - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Domain
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
# Domain
An internet domain
Domain attributes represent an internet domain, for example, “apple.com”.
Attio represents domains as structured objects rather than raw strings, allowing filtering and display of specific domain properties such as the root domain.
Please note that domain attributes store domains, not URLs. Any inputted values will have paths and query parameters trimmed. If you would like to store full URLs, please use a text attribute.
It isn’t currently possible to create your own domain attributes, so you’ll find only the multi-select `domains` attribute on a company object.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-domain#reading-values)
Reading values
There are two properties on a domain attribute, `domain` and `root_domain`.
The `domain` property contains the entire domain, after normalization.
The `root_domain` property is the top-most part of the domain besides the public suffix. For example, the root domain of `"app.attio.com"` would be `"attio.com"`.
Example: app.attio.com
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "domain",
  "domain": "app.attio.com",
  "root_domain": "attio.com"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-domain#writing-values)
Writing values
To write domain values, simply pass the string of the domain.
The `root_domain` property will automatically be inferred from input values so there is no need to write it yourself.
You may also write domain values using an object with a single key, `domain`.
As the `domains` attribute is multi-select, you must always pass values wrapped in an array.
Using string (single value)
Using string (multiple values)
Using object
Copy
```
{
  "domains": ["app.attio.com"]
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-domain#filtering)
Filtering
Domain attribute values can be filtered by either the `root_domain` or `domain` property, and support several operators:
  * `$eq` for an exact match
  * `$not_empty` for any value present
  * `$contains` , `$starts_with` and `$ends_with`


In implicit mode, the `domain` property is checked for equality, otherwise you can use the explicit syntax to combine the properties and operators above.
Companies where domain=app.attio.com
...where subdomain=attio.com
...where domain includes attio
Copy
```
{
  "filter": {
    "domain": "app.attio.com"
  }
}
```

Was this page helpful?
YesNo
[Date](https://docs.attio.com/docs/attribute-types/attribute-types-date)[Email address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-domain#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-domain#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-domain#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
