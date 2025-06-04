---
title: Actor reference - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Actor reference - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Actor reference
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
    * [Overview](https://docs.attio.com/docs/attribute-types/attribute-types)
    * [Actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference)
    * [Checkbox](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox)
    * [Currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency)
    * [Date](https://docs.attio.com/docs/attribute-types/attribute-types-date)
    * [Domain](https://docs.attio.com/docs/attribute-types/attribute-types-domain)
    * [Email address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address)
    * [Interaction](https://docs.attio.com/docs/attribute-types/attribute-types-interaction)
    * [Location](https://docs.attio.com/docs/attribute-types/attribute-types-location)
    * [(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)
    * [Number](https://docs.attio.com/docs/attribute-types/attribute-types-number)
    * [Phone number](https://docs.attio.com/docs/attribute-types/attribute-types-phone-number)
    * [Rating](https://docs.attio.com/docs/attribute-types/attribute-types-rating)
    * [Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference)
    * [Select](https://docs.attio.com/docs/attribute-types/attribute-types-select)
    * [Status](https://docs.attio.com/docs/attribute-types/attribute-types-status)
    * [Text](https://docs.attio.com/docs/attribute-types/attribute-types-text)
    * [Timestamp](https://docs.attio.com/docs/attribute-types/attribute-types-timestamp)


##### Further reading
  * [Actors](https://docs.attio.com/docs/actors)
  * [Slugs and IDs](https://docs.attio.com/docs/slugs-and-ids)
  * [Default values](https://docs.attio.com/docs/default-values)
  * [Archiving vs deleting](https://docs.attio.com/docs/archiving-vs-deleting)


Attribute types
# Actor reference
References to workspace members and others
Actor references are used to link to [actors](https://docs.attio.com/docs/actors) in Attio. You’re most likely to encounter this attribute via the `created_by` attribute which is available on every object, the `owner` attribute on a deal object, or the `strongest_connection_user` on a company or person.
Actor reference attributes can be single-select or multi-select.
Please note, in the mobile and web clients, attributes of this type are marked as “User” attributes.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#reading-values)
Reading values
Actor reference values have two properties, `referenced_actor_type` and `referenced_actor_id`. The `referenced_actor_type` can be one of `"api-token"`, `"workspace-member"` or `"system"`. The `referenced_actor_id` is a UUID, or the value `null`, that uniquely identifies the actor.
Example: workspace member
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "actor-reference",
  "referenced_actor_type": "workspace-member",
  "referenced_actor_id": "fbe75eb0-d704-4d12-9e41-aa187e60ed73"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#writing-values)
Writing values
Currently, the only type of [actor](https://docs.attio.com/docs/actors) that can be explicitly set in our API is `"workspace-member"`. We may expand this list in future.
When writing references to workspace members, we allow you to identify actors by email addresses. You may do this either by passing an email address string directly, or by using an object with the key `workspace_member_email_address`.
Actor reference attributes may be multi-select or single-select. When writing to multi-select attributes, you must always wrap values in an array. Single-select attributes accept unwrapped data.
Using email string
Single-select string
Using workspace_member_email_address
Copy
```
{
  "owner": ["[email protected]"]
}
```

You may also specify the actor type and ID explicitly using an object with the keys `referenced_actor_type` and `referenced_actor_id`.
Using workspace member ID
Copy
```
{
  "owner": [
    {
      "referenced_actor_type": "workspace-member",
      "referenced_actor_id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b"
    }
  ]
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#filtering)
Filtering
Actor reference values can only be filtered using both the `referenced_actor_type` and `referenced_actor_id` properties. If using explicit operators, only the `$eq` operator is supported. For example:
Value written by workspace member
Value written by API token
Expanded format
Copy
```
{
  "filter": {
    "created_by": {
      "referenced_actor_type": "workspace-member",
      "referenced_actor_id": "ec44a06c-b690-4e4f-95b6-757fb4e2f55f"
    }
  }
}
```

Was this page helpful?
YesNo
[Overview](https://docs.attio.com/docs/attribute-types/attribute-types)[Checkbox](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
