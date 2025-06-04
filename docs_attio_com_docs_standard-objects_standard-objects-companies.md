---
title: Companies - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects-companies
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/standard-objects/standard-objects-users
---

# Companies - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects-companies](https://docs.attio.com/docs/standard-objects/standard-objects-companies)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
Companies
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
# Companies
An object to represent businesses: customers, partners, peers…
Company configuration
Copy
```
api_slug: companies
singular_noun: Company
plural_noun: Companies
```

The company object is available in every Attio workspace. Companies represent businesses, such as customers, partners, suppliers, etc.
When creating a person, a related company record will automatically be generated or matched based on the domain of the person’s email address, but they can also be created manually via the web application or the API.
Company records are enriched, which means that Attio will automatically populate additional attributes, and those enriched values cannot be overridden by API users. Additionally, some enriched attributes may be hidden from the API depending on the workspace billing plan.
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects-companies#writable-attributes)
Writable attributes
The following attributes can always be read and written using the API:
Attribute | Slug | Type | Traits  
---|---|---|---  
Domains | `domains` | [Domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain) | Unique, multiselect  
Name | `name` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Description | `description` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Team | `team` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Person -> company`, multiselect  
Categories | `categories` | [Select](https://docs.attio.com/docs/attribute-types/attribute-types-select) | Multiselect  
Primary location | `primary_location` | [Location](https://docs.attio.com/docs/attribute-types/attribute-types-location) |   
AngelList | `angellist` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Facebook | `facebook` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Instagram | `instagram` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
LinkedIn | `linkedin` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Twitter | `twitter` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Associated deals | `associated_deals` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Deal -> associated_companies` (only visible if [Deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals) activated  
Associated workspaces | `associated_workspaces` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Workspace -> company` (only visible if [Workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces) activated)  
It’s important to note that while standard attributes like `domains` have unique properties by default, you cannot create new custom attributes with a unique constraint for Company objects.
Was this page helpful?
YesNo
[Overview](https://docs.attio.com/docs/standard-objects/standard-objects)[People](https://docs.attio.com/docs/standard-objects/standard-objects-people)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Writable attributes](https://docs.attio.com/docs/standard-objects/standard-objects-companies#writable-attributes)


Assistant
Responses are generated using AI and may contain mistakes.
