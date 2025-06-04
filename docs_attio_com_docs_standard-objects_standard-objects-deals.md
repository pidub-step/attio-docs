---
title: Deals - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects-deals
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/standard-objects/standard-objects-users
---

# Deals - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects-deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
Deals
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Get started
  * [Overview](https://docs.attio.com/docs/overview)


##### Core concepts
  * [Objects and lists](https://docs.attio.com/docs/objects-and-lists)
  * [Users and workspaces](https://docs.attio.com/docs/users-and-workspaces)
  * Standard objects
    * [Overview](https://docs.attio.com/docs/standard-objects/standard-objects)
    * [Companies](https://docs.attio.com/docs/standard-objects/standard-objects-companies)
    * [People](https://docs.attio.com/docs/standard-objects/standard-objects-people)
    * [Deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals)
    * [Users](https://docs.attio.com/docs/standard-objects/standard-objects-users)
    * [Workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)
  * Attribute types


##### Further reading
  * [Actors](https://docs.attio.com/docs/actors)
  * [Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)
  * [Default values](https://docs.attio.com/docs/default-values)
  * [Archiving vs deleting](https://docs.attio.com/docs/archiving-vs-deleting)


Standard objects
# Deals
An object to represent deals involving people & companies
Deal configuration
Copy
```
api_slug: deals
singular_noun: Deal
plural_noun: Deal
```

The Deal object is available in every Attio workspace, but disabled by default. It can only be activated by a workspace admin, in the [objects settings](https://app.attio.com/_/settings/data/objects) page.
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects-deals#writeable-attributes)
Writeable attributes
Attribute | Slug | Type | Traits  
---|---|---|---  
Name | `name` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) | Required  
Deal stage | `stage` | [Status](https://docs.attio.com/docs/attribute-types/attribute-types-status) | Required - by default one of `"Lead"`, `"In Progress"`, `"Won 🎉"`, `"Lost"` (workspaces can configure these status options)  
Deal owner | `owner` | [Actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference) | Required  
Deal value | `value` | [Currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency) | Defaults to USD, can be changed  
Associated people | `associated_people` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Person -> associated_deals`  
Associated company | `associated_company` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Company -> associated_deals`  
Note that deals do not have a unique attribute by default. This means that they cannot be automatically asserted without adding an additional unique attribute.
Was this page helpful?
YesNo
[People](https://docs.attio.com/docs/standard-objects/standard-objects-people)[Users](https://docs.attio.com/docs/standard-objects/standard-objects-users)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Writeable attributes](https://docs.attio.com/docs/standard-objects/standard-objects-deals#writeable-attributes)


Assistant
Responses are generated using AI and may contain mistakes.
