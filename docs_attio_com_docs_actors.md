---
title: Actors - Attio Docs
url: https://docs.attio.com/docs/actors
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Actors - Attio Docs

**Source:** [https://docs.attio.com/docs/actors](https://docs.attio.com/docs/actors)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Further reading
Actors
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
# Actors
Keeping track of who did what
In various places in the Attio API, you will see the concept of an “actor”. An actor is something that performs actions inside Attio. A workspace member is the prime example of an actor, but you will also encounter apps and automations as actors.
## 
[​](https://docs.attio.com/docs/actors#types-of-actors)
Types of Actors
An Actor is made up of two things: a type and an ID. The current list of actors types and their corresponding ID format is as follows:
  * `workspace-member` - A human user who is signed into a workspace. Comes with a unique UUID. You can get further information about the workspace member, e.g. name, avatar and email address, using the [list workspace members endpoints](https://docs.attio.com/rest-api/endpoint-reference/workspace-members/get-a-workspace-member).
  * `api-token` - An integration using the developer API. Comes with a unique UUID for the token.
  * `system` - An internal part of the Attio system. For example, communications intelligence updates are registered with system actors. Always comes with a `null` ID.


Actors are recorded in various parts of the system. Every attribute value write, for example, includes the actor who wrote it, e.g:
The actor who wrote a particular value
Copy
```
"created_by_actor": {
  "type": "workspace-member",
  "id": "175bec0c-f06a-4c45-9962-7a7a6be28b8a"
}
```

Actors are often encountered via the “actor reference” attribute type. Every standard object includes a `created_by` attribute of this type. For more information, please see the [actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference.mdx) documentation.
Was this page helpful?
YesNo
[Timestamp](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp)[Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Types of Actors](https://docs.attio.com/docs/actors#types-of-actors)


Assistant
Responses are generated using AI and may contain mistakes.
