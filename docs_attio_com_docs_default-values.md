---
title: Default values - Attio Docs
url: https://docs.attio.com/docs/default-values
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Default values - Attio Docs

**Source:** [https://docs.attio.com/docs/default-values](https://docs.attio.com/docs/default-values)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Further reading
Default values
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


##### Further reading
  * [Actors](https://docs.attio.com/docs/actors)
  * [Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)
  * [Default values](https://docs.attio.com/docs/default-values)
  * [Archiving vs deleting](https://docs.attio.com/docs/archiving-vs-deleting)


Further reading
# Default values
Attribute definitions on objects and lists support default values which are used to pre-populate values on records and entries.
There are two kinds of default value: static and dynamic.
## 
[​](https://docs.attio.com/docs/default-values#static-defaults)
Static defaults
Static values are raw values that are used directly without transformation. For example, you might want to always fill the “Deal Status” property on new entries in your “Sales” list to the value “Lead”.
Static values are supported on all attribute types. The `template` property on default values must match the type of the attribute. These types are documented in our endpoint reference docs.
## 
[​](https://docs.attio.com/docs/default-values#dynamic-defaults)
Dynamic defaults
Dynamic values are used to generate values on the fly, depending on context. For example, you might want to fill in an “Owner” property to the current user, or set a due date to one week in the future.
Dynamic values take the form of a string. The currently supported list of dynamic value templates, broken down by attribute type, is as follows:
  * `actor-reference` attributes, with the default value `current-user`
  * `timestamp` or `date` attributes, with an [ISO 8601 Duration](https://tc39.es/proposal-temporal/docs/duration.html) e.g. `“P1M”` for one month in the future


Other attribute types do not currently support dynamic default values.
Was this page helpful?
YesNo
[Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)[Archiving vs deleting](https://docs.attio.com/docs/archiving-vs-deleting)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Static defaults](https://docs.attio.com/docs/default-values#static-defaults)
  * [Dynamic defaults](https://docs.attio.com/docs/default-values#dynamic-defaults)


Assistant
Responses are generated using AI and may contain mistakes.
