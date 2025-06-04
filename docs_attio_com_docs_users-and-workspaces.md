---
title: Users and workspaces - Attio Docs
url: https://docs.attio.com/docs/users-and-workspaces
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Users and workspaces - Attio Docs

**Source:** [https://docs.attio.com/docs/users-and-workspaces](https://docs.attio.com/docs/users-and-workspaces)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Core concepts
Users and workspaces
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
# Users and workspaces
_Not to be confused with our standard objects[users](https://docs.attio.com/docs/standard-objects/standard-objects-users) and [workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)_
A **user** is a login account with Attio. For example, a person who has signed up to Attio with the email `person@company.com`.
A **workspace** is a company account with objects, records, lists and such. Every user has at least one workspace created when signing up for the first time. Some users will have multiple workspaces when they are members of large orgsharanisations with multiple workspaces, or for testing and development purposes.
Since users can join multiple workspaces, we use the **workspace member** concept to represent a single user in a single workspace (this also encapsulates their permissions, such as whether they are an admin).
All access to the Attio API is scoped to a single workspace, so you will never interact with users directly. Instead, user-level data such as email addresses are accessed through [workspace member APIs](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/list-workspace-members).
Was this page helpful?
YesNo
[Objects and lists](https://docs.attio.com/docs/objects-and-lists)[Overview](https://docs.attio.com/docs/standard-objects/standard-objects)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
