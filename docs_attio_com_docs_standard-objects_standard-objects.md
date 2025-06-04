---
title: Overview - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/docs/users-and-workspaces
---

# Overview - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects](https://docs.attio.com/docs/standard-objects/standard-objects)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
Overview
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
# Overview
Companies and people are available in all workspaces
Every Attio workspace starts with a company and person object, and admins can optionally enable the deal, user and workspace standard objects if it meets their needs.
These 5 objects come with a pre-defined set of attributes. As a developer, you can rely on being able to read and write from/to these predefined (or “system”) attributes. Admins can also add custom attributes to any of these objects, or create new custom objects with custom attributes on those.
Developers can interact with both standard and custom objects in the same ways, using e.g. the [assert a Record](https://docs.attio.com/rest-api/endpoint-reference/records/assert-a-record) API, but the following pages go into more detail about exactly which attributes you might find and how to read/write them for these.
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects#attributes-on-every-object)
Attributes on every object
Attribute | Type | Writable? | Notes  
---|---|---|---  
`created_at` | Timestamp | No | When the record was created, defaults to current timestamp (see [Default values](https://docs.attio.com/docs/default-values))  
`created_by` (which actor created the record) | Actor reference | No | Which actor created the record, defaults to current user in web application, or the integration in API  
`record_id` | Text (UUID) | No | The unique identifier for the record, available as an attribute value to allow easy querying  
Was this page helpful?
YesNo
[Users and workspaces](https://docs.attio.com/docs/users-and-workspaces)[Companies](https://docs.attio.com/docs/standard-objects/standard-objects-companies)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Attributes on every object](https://docs.attio.com/docs/standard-objects/standard-objects#attributes-on-every-object)


Assistant
Responses are generated using AI and may contain mistakes.
