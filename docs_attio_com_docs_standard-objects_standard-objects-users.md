---
title: Users - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects-users
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/docs/users-and-workspaces
---

# Users - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects-users](https://docs.attio.com/docs/standard-objects/standard-objects-users)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
Users
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
# Users
An object to represent users of your product
User configuration
Copy
```
api_slug: users
singular_noun: User
plural_noun: Users
```

The User object is available in every Attio workspace, but disabled by default. It can only be activated by a workspace admin, in the [Objects settings](https://app.attio.com/_/settings/data/objects) page.
Users represent a user of your product. They are related to a [Person](https://docs.attio.com/docs/standard-objects/standard-objects-people), have an email address, and an ID attribute that is defined by your system. Users are grouped together in Workspaces.
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects-users#writeable-attributes)
Writeable attributes
Attribute | Slug | Type | Traits  
---|---|---|---  
Person | `person` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Person -> associated_users`  
Primary email address | `primary_email_address` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) | Required, unique - this is usually their login email in your system  
ID | `user_id` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) | Required, unique - this is usually their ID in your system  
Workspaces | `workspace` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Workspace -> users`  
Users can be asserted by either their `primary_email_address` or `user_id` unique attributes, or you can add your own.
Was this page helpful?
YesNo
[Deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals)[Workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Writeable attributes](https://docs.attio.com/docs/standard-objects/standard-objects-users#writeable-attributes)


Assistant
Responses are generated using AI and may contain mistakes.
