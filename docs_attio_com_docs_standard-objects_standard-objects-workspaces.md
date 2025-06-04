---
title: Workspaces - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects-workspaces
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/docs/users-and-workspaces
---

# Workspaces - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects-workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
Workspaces
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
# Workspaces
An object to group users of your product
Workspace configuration
Copy
```
api_slug: workspaces
singular_noun: Workspace
plural_noun: Workspaces
```

The Workspace object is available in every Attio workspace, but disabled by default. It can only be activated by a workspace admin, in the [objects settings](https://app.attio.com/_/settings/data/objects) page.
Workspaces represent a grouping of users, or an account, in your product. Workspaces can belong to a [company](https://docs.attio.com/docs/standard-objects/standard-objects-companies) and have multiple [users](https://docs.attio.com/docs/standard-objects/standard-objects-users).
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces#writeable-attributes)
Writeable attributes
Attribute | Slug | Type | Traits  
---|---|---|---  
ID | `workspace_id` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) | Unique, required  
Name | `name` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Users | `users` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `User -> workspaces`, multiselect  
Company | `company` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Company -> associated_workspaces`  
Avatar URL | `avatar_url` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) | Similar to [Company](https://docs.attio.com/docs/standard-objects/standard-objects-companies) `logo_url`  
Workspaces have a single unique attribute, `workspace_id`, which can be used for assertions, or you can add your own.
Was this page helpful?
YesNo
[Users](https://docs.attio.com/docs/standard-objects/standard-objects-users)[Overview](https://docs.attio.com/docs/attribute-types/attribute-types)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Writeable attributes](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces#writeable-attributes)


Assistant
Responses are generated using AI and may contain mistakes.
