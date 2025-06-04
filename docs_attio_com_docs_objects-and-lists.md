---
title: Objects and lists - Attio Docs
url: https://docs.attio.com/docs/objects-and-lists
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Objects and lists - Attio Docs

**Source:** [https://docs.attio.com/docs/objects-and-lists](https://docs.attio.com/docs/objects-and-lists)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Core concepts
Objects and lists
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


Core concepts
# Objects and lists
At the core of Attio is our powerful and flexible data model, which allows you to define custom objects and lists with a wide array of attribute types.
Objects can be used to model your domain entities, while lists can be used to aggregate them together and model business processes. However, both objects and lists can have their own attributes. For example, you might be using the deal object to keep track of the various deals you have in progress, but you could also create a list of deals with some additional attributes only relevant to a deal in that list.
## 
[​](https://docs.attio.com/docs/objects-and-lists#objects)
Objects
Objects are the data types used to store facts about your customer. By themselves, they contain little information other than a name, but records and attributes are scoped to a single object. Attio comes with two objects enabled by default, people and companies, and three optional objects: deal, user and workspace.
In relational database terms, objects are roughly tables. In object-orientated terms, they are analogous to classes. Note that an instance of an object is called a record (see below).
For more information about Attio objects, please [see our help center guide](https://attio.com/help/reference/workspace/objects).
### 
[​](https://docs.attio.com/docs/objects-and-lists#records)
Records
Records are an instantiation of an object, e.g. a specific person or a specific company. In relational database terms, a record is roughly a row in a table. In object-orientated terms, they are analogous to an object (an instantiated class).
### 
[​](https://docs.attio.com/docs/objects-and-lists#attributes)
Attributes
Attributes sit on objects and lists and describe what data we can store. Some attributes, such as the name on a person, are system defined. Others, you define yourself, either in Attio’s UI or over the API. Attributes are one of many types such as text, number, select, or currency. In relational database terms, an attribute is roughly a column in a table.
## 
[​](https://docs.attio.com/docs/objects-and-lists#lists-%26-entries)
Lists & entries
Lists are composed of multiple rows, known as “entries”, each of which corresponds to a single record. Entries are created by adding a record to a list. Lists can be used to model a particular process. For example, you might have a “Sales” list that contains the companies that you have relationships with.
Was this page helpful?
YesNo
[Overview](https://docs.attio.com/docs/overview)[Users and workspaces](https://docs.attio.com/docs/users-and-workspaces)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Objects](https://docs.attio.com/docs/objects-and-lists#objects)
  * [Records](https://docs.attio.com/docs/objects-and-lists#records)
  * [Attributes](https://docs.attio.com/docs/objects-and-lists#attributes)
  * [Lists & entries](https://docs.attio.com/docs/objects-and-lists#lists-%26-entries)


Assistant
Responses are generated using AI and may contain mistakes.
