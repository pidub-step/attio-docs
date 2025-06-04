---
title: People - Attio Docs
url: https://docs.attio.com/docs/standard-objects/standard-objects-people
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/standard-objects/standard-objects-users
---

# People - Attio Docs

**Source:** [https://docs.attio.com/docs/standard-objects/standard-objects-people](https://docs.attio.com/docs/standard-objects/standard-objects-people)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Standard objects
People
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
# People
An object to represent human beings
People configuration
Copy
```
api_slug: people
singular_noun: Person
plural_noun: People
```

The person object is available in every Attio workspace. When creating a person, a related company record will automatically be generated or matched based on the domain of the person’s email address, but they can also be created manually via the web application or the API.
Person records are enriched, which means that Attio will automatically populate additional attributes, and those values cannot be overridden by API users. Additionally, some enriched attributes may be hidden from the API depending on the workspace billing plan.
## 
[​](https://docs.attio.com/docs/standard-objects/standard-objects-people#writeable-attributes)
Writeable attributes
Attribute | Slug | Type | Traits  
---|---|---|---  
Email addresses | `email_addresses` | [Email address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address) | Unique, multiselect  
Name | `name` | [(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name) |   
Company | `company` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Company -> team`  
Description | `description` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Job title | `job_title` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Phone numbers | `phone_numbers` | [Phone number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number) | Multiselect  
Primary location | `primary_location` | [Location](https://docs.attio.com/docs/attribute-types/attribute-types-location) |   
AngelList | `angellist` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Facebook | `facebook` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Instagram | `instagram` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
LinkedIn | `linkedin` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Twitter | `twitter` | [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text) |   
Associated deals | `associated_deals` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `Deal -> associated_people` (only available if [Deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals) activated)  
Associated users | `associated_users` | [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference) | Relationship, inverse of `User -> person` (only available if [Users](https://docs.attio.com/docs/standard-objects/standard-objects-users) activated)  
Was this page helpful?
YesNo
[Companies](https://docs.attio.com/docs/standard-objects/standard-objects-companies)[Deals](https://docs.attio.com/docs/standard-objects/standard-objects-deals)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Writeable attributes](https://docs.attio.com/docs/standard-objects/standard-objects-people#writeable-attributes)


Assistant
Responses are generated using AI and may contain mistakes.
