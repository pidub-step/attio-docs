---
title: Interaction - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-interaction
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Interaction - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-interaction](https://docs.attio.com/docs/attribute-types/attribute-types-interaction)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Interaction
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
# Interaction
Calendar events and emails
Interactions are quite a generic concept, used to model when a given actor interacted with a record in a particular way. Presently, Attio has just two types of interaction:
  * Email interactions (`first_email_interaction` and `last_email_interaction`)
  * Calendar interactions (`first_calendar_interaction`, `last_calendar_interaction` and `next_calendar_interaction`)


These attributes are available on both the Company and Person objects, although they are enriched and not available on every billing plan. For more information about these attributes, [please see our Enriched data help page](https://attio.com/help/reference/data-and-syncing/enriched-data#communication-intelligence).
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#reading-values)
Reading values
Interaction attribute values have an `interaction_type` property, which can be either `"email"` or `"calendar-event"`, and an `interacted_at` timestamp property in ISO8601 format.
There is also an `owner_actor` property, which is an object relating the [actor](https://docs.attio.com/docs/actors) who created this interaction (this is different from the `created_by` attribute value property which could be e.g. a system actor).
Example: last email received by Tom on 2023-11-25
Copy
```
{
  "active_from": "2023-11-25T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {
    "type": "system",
    "id": null
  },
  "attribute_type": "interaction",
  "interaction_type": "email",
  "interacted_at": "2023-11-25T15:21:06.447000000Z",
  "owner_actor": {
    "type": "workspace-member",
    "id": "50cf242c-7fa3-4cad-87d0-75b1af71c57b" // Tom
  }
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#writing-values)
Writing values
It is not currently possible to write Interaction values, they are only created by the Attio system.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#filtering)
Filtering
There are three properties of interactions that can be used in filtering:
  * `owner_member_id` filters by the workspace member ID that is the `owner_actor`, this supports `$eq` and `$not_empty` operators
  * `interacted_at` (timestamp) supports `$eq`, `$gte`, `$gt`, `$lte` and `$lt` operators
  * `interaction_type` can also be filtered by `$eq` and `$not_empty`


Companies ... which have had an email interaction
... with whom Tom had a recent meeting
... via email
Copy
```
{
  "filter": {
    "last_email_interaction": {
      "owner_member_id": {
        "$not_empty": true
      }
    }
  }
}
```

Was this page helpful?
YesNo
[Email address](https://docs.attio.com/docs/attribute-types/attribute-types-email-address)[Location](https://docs.attio.com/docs/attribute-types/attribute-types-location)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-interaction#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
