---
title: Select - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-select
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Select - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-select](https://docs.attio.com/docs/attribute-types/attribute-types-select)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Select
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
# Select
An option from a predefined list
Select attributes are a constrained input type, where the user must pick from a predefined list.
Company has several select attributes (they are mostly [enriched attributes](https://attio.com/help/reference/data-and-syncing/enriched-data)): `categories`, `estimated_arr_usd` and `employee_range`. `strongest_connection_strength` is also available on both person and company.
Attio provides a [separate API for managing the select options available](https://docs.attio.com/rest-api/endpoint-reference/attributes/list-select-options).
Select attributes may be either single-select or multi-select. In the API, these two variants are represented using the same underlying type, select. However, in web and mobile clients, users will see these attributes as two separate types: select and multi-select.
Please note that select attributes cannot be configured to be unique.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-select#reading-values)
Reading values
Select attribute values have an `option` property, which is an object describing which select option was used:
Example: 3 out of 5 stars
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "select",
  "option": {
    "id": {
      "workspace_id": "4f9a01be-3792-4ab9-926f-ca7f9005700c",
      "object_id": "5f1feef5-fe73-4c0e-9d97-5b0a96a7d32b",
      "attribute_id": "a4977b52-d367-4e28-a671-b5c4fa401fc5",
      "option_id": "14938464-cae9-4e50-8856-0fb584844f24"
    },
    "title": "Aerospace & Defense",
    "is_archived": false
  }
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-select#writing-values)
Writing values
You can find a list of available options using the [list select options](https://docs.attio.com/rest-api/endpoint-reference/attributes/list-select-options) API.
To write select values, pass the title of the select option as a string. If it’s a multi-value select attribute, you’ll need to pass an array.
You can also pass an object with an `option` property, which references either the `option_id` or the `title` of the select option.
If you attempt to write a value where the ID or title cannot be found, you will receive an error rather than create a new select option.
Using string
Multiple values
Using object (title)
Using object (option_id)
Copy
```
{
  "categories": ["3D Printing"]
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-select#filtering)
Filtering
Select attributes can be filtered by equality, using either the implicit syntax or the explicit one:
Finding companies in the "Aerospace & Defense" category
... with an option ID instead
Copy
```
{
  "filter": {
    "categories": "Aerospace & Defense"
  }
}
```

It’s also possible to use `$or` to find records which match one of several categories:
Find Companies in one of many categories
Copy
```
{
  "filter": {
    "$or": [
      {"categories": "Aerospace & Defense"},
      {"categories": "Biotechnology"}
    ]
  }
}
```

Select attributes can also be filtered based on when they were modified, using the `active_from` property. This allows automations based on when the attribute was changed. This filter supports the `$lt`, `$lte`, `$gt`, `$gte` operators:
Finding companies where the category was changed this week
... where the category was not changed this year
Copy
```
{
  "filter": {
    "categories": {
      "active_from": {
        "$gte": "2023-11-20"
      }
    }
  }
}
```

Was this page helpful?
YesNo
[Record reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference)[Status](https://docs.attio.com/docs/attribute-types/attribute-types-status)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-select#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-select#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-select#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
