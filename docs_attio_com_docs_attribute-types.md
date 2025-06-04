---
title: Overview - Attio Docs
url: https://docs.attio.com/docs/attribute-types
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/rest-api/how-to/filtering-and-sorting
---

# Overview - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types](https://docs.attio.com/docs/attribute-types)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
Ask AI
Search...
Navigation
Attribute types
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
# Overview
Attributes are used to model data on objects and lists. Standard objects come with a series of “system” attributes predefined, but users and developers can create and modify their own attributes as well.
## 
[​](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-properties)
Attribute properties
In the API, attributes are presented as a set of properties. Some attribute types have specific properties (e.g. an actor reference attribute has the `referenced_actor_type` property), but all attributes have the following properties:
  * `id`, which is a [composite ID](https://docs.attio.com/docs/slugs-and-ids) composed of `(workspace_id, object_id, attribute_id)`
  * `title`, the human-readable name of the attribute (e.g. `"Name"`)
  * `description`, an optional human-readable description (e.g. `"The name as registered in our database"`)
  * `api_slug`, a shorthand way for developers to refer to this attribute (e.g. `"name"`)
  * `type`, one of the enumerated types below (e.g. `"text"`)
  * `is_archived`, whether the [attribute has been archived](https://docs.attio.com/docs/archiving-vs-deleting)
  * `is_required`, whether a value is required when creating the record or list entry
  * `is_unique`, whether the value for this attribute is unique among all other records or list entries of that type
  * `is_multiselect`, whether you can write more than one value to this attribute
  * `is_default_value_enabled` and `default_value`, see the [default values guide](https://docs.attio.com/docs/default-values)
  * `created_at`, a timestamp of when this attribute was first created
  * `config`, an object containing specific configuration for `currency` or `record_reference` types


For more information about attributes, you can find our [attribute APIs here](https://docs.attio.com/rest-api/endpoint-reference/attributes).
## 
[​](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-values)
Attribute values
Attribute values represent the value of the given attribute on a given record or list entry. They also have a set of common properties, that you’ll see referenced throughout this guide:
  * `active_from`, a timestamp showing when this value was created
  * `active_until`, either a timestamp (meaning the value was readable until that point in time) or `null`, meaning the value is still currently active. Most endpoints will only return active values, meaning this value is usually `null`. In special cases, such as the [list record attribute values API](https://attio.readme.io/reference/get_v2-objects-object-records-record-id-attributes-attribute-values), you can also query historic data.
  * `created_by_actor`, a reference to the `id` and `type` of the [Actor](https://docs.attio.com/docs/actors) who created this value
  * `attribute_type`, matches the `type` property on the Attribute itself (e.g. `"text"`)


## 
[​](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-types)
Attribute types
Attio currently has 17 different attribute types, and they can behave differently when creating, viewing, filtering and sorting. This guide will walk through each type, with examples of where you might find them and how to work with them:
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


Was this page helpful?
YesNo
[Workspaces](https://docs.attio.com/docs/standard-objects/standard-objects-workspaces)[Actor reference](https://docs.attio.com/docs/attribute-types/attribute-types-actor-reference)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Attribute properties](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-properties)
  * [Attribute values](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-values)
  * [Attribute types](https://docs.attio.com/docs/attribute-types/attribute-types#attribute-types)


Assistant
Responses are generated using AI and may contain mistakes.
