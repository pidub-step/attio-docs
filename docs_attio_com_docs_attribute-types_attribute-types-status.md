---
title: Status - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-status
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Status - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-status](https://docs.attio.com/docs/attribute-types/attribute-types-status)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Status
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
# Status
Similar to select attributes, originally designed for use in Lists
Just like [select](https://docs.attio.com/docs/attribute-types/attribute-types-select) attributes, status attributes are a constrained input type, where the user must pick from a predefined list. They are used in the Attio UI to define the different columns on a kanban board, but they can also be used with objects directly.
There’s only one predefined status attribute, available on the deal object as `stage`.
The possible values of a status attribute are known as “statuses”, and there are [separate APIs for managing them](https://docs.attio.com/rest-api/endpoint-reference/attributes/list-statuses).
All status attributes are single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-status#reading-values)
Reading values
Status values have a `status` property, which is an object describing which status was used:
Example: 3 out of 5 stars
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "select",
  "status": {
    "id": {
      "workspace_id": "4f9a01be-3792-4ab9-926f-ca7f9005700c",
      "object_id": "5f1feef5-fe73-4c0e-9d97-5b0a96a7d32b",
      "attribute_id": "a4977b52-d367-4e28-a671-b5c4fa401fc5",
      "status_id": "11f07f01-c10f-4e05-a522-33e050bc52ee"
    },
    "title": "In Progress",
    "is_archived": false,
    "target_time_in_status": null,
    "celebration_enabled": false
  }
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-status#writing-values)
Writing values
You can find a list of available statuses using the [list statuses](https://docs.attio.com/rest-api/endpoint-reference/attributes/list-statuses) API.
To write status values, pass the title of the status as a string.
You can also pass an object with a `status` property which references either the `status_id` or the `title` of the status.
If you attempt to write a value where the ID or title cannot be found, you will receive an error rather than create a new status.
Using string
Using object (title)
Using object (status_id)
Copy
```
{
  "stage": "Lead"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-status#filtering)
Filtering
Status attributes can be filtered by equality, using either the implicit syntax or the explicit one, with either the title or status ID:
Finding deals in the "In Progress" stage
... with a status ID instead
Copy
```
{
  "filter": {
    "stage": "In Progress"
  }
}
```

You can also filter for multiple possible matching values using the `$or` syntax:
Finding deals in either "In Progress" or "Lead" stage
Copy
```
{
  "filter": {
    "$or": [
      {"stage": "In Progress"},
      {"stage": "Lead"}
    ]
  }
}
```

Status attributes can also be filtered based on when they were modified, using the `active_from` property. This allows automations based on when the attribute was changed. This filter supports the `$lt`, `$lte`, `$gt`, `$gte` operators:
Finding deals where the stage was changed this week
... where the stage was not changed this year
Copy
```
{
  "filter": {
    "stage": {
      "active_from": {
        "$gte": "2023-11-20"
      }
    }
  }
}
```

Was this page helpful?
YesNo
[Select](https://docs.attio.com/docs/attribute-types/attribute-types-select)[Text](https://docs.attio.com/docs/attribute-types/attribute-types-text)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-status#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-status#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-status#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
