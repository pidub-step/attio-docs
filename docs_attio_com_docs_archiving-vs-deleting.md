---
title: Archiving vs deleting - Attio Docs
url: https://docs.attio.com/docs/archiving-vs-deleting
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Archiving vs deleting - Attio Docs

**Source:** [https://docs.attio.com/docs/archiving-vs-deleting](https://docs.attio.com/docs/archiving-vs-deleting)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Further reading
Archiving vs deleting
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
# Archiving vs deleting
Attio uses two separate but related concepts: **archiving** and **deleting**.
**Deleting** should be considered permanent. Any data you delete will eventually be removed from our servers entirely, without the ability for restoration. As such, deletes should be handled extremely carefully.
When using our API, deleting occurs using the conventional REST semantics of the `DELETE` HTTP verb.
**Archiving** is softer, allowing data to remain in the system, albeit in a more hidden state. The exact behaviour of archived data will depend on the object you are archiving, but the behaviour will be documented for the given endpoint.
When using our API, archiving occurs by setting the `is_archived` property to `true`, and restored by setting it to `false`.
Was this page helpful?
YesNo
[Default values](https://docs.attio.com/docs/default-values)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
