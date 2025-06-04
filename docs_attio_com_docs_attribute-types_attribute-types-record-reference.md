---
title: Record reference - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-record-reference
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Record reference - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-record-reference](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Record reference
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
# Record reference
Relationships and one-way links between records
Record reference attributes are one of the most useful types of attribute. They allow pointing to other records of the same object, or records of other objects. When combined with features such as drill-down filters, it becomes possible to deeply relate the various parts of your data model.
By default, all of the standard objects have at least one record reference:
  * Company has `team` (people), `associated_deals` (deals) and `associated_workspaces` (workspaces)
  * Person has `company` (company), `associated_deals`(deals) and `associated_users` (users)
  * Deal has `associated_people` (people) and `associated_company` (company)
  * User has `person` (person) and `workspace` (workspace)
  * Workspace has `users` (users) and `company` (company)


### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#a-note-about-relationship-attributes)
A note about relationship attributes
All of the example attributes above are also relationship attributes.
[Relationship attributes](https://attio.com/help/reference/workspace/attributes#relationship-attributes) describe a relationship between two objects, which appear as a pair of record reference attributes, one on each object. Updating an attribute value on either of the attributes automatically updates the other attribute, which means you don’t need to explicitly update both. For example, adding a person to a company by updating the company `team` property, will also update the `company` property on that person.
Currently, you will be able to see relationship attributes alongside other non-relationship record reference attributes in the API. The attribute type is still marked as `record-reference`, but there is an additional property, `relationship`, that you can use to distinguish these.
If the attribute is also a relationship attribute, the `relationship` property will be an object containing an `id` property. In the example below, our company’s `team` attribute has a relationship with the person’s `company` attribute:
Example "team" attribute on a company
Copy
```
{
  "id": { ... },
  "title": "Team",
  "api_slug": "team",
  "type": "record-reference",
  "relationship": {
     "id": {
       "workspace_id": "14beef7a-99f7-4534-a87e-70b564330a4c",
       "object_id": "4e71c40b-7d35-463c-afcb-e339cfd6dbd1",   // Person object
       "attribute_id": "41252299-f8c7-4b5e-99c9-4ff8321d2f96" // "Company" attribute on Person object
     }
  },
  ...
}
```

If the record reference attribute is not a relationship attribute, the `relationship` property will be set to `null`.
In the web application, when setting up a relationship, the user specifies whether the relationship is many-to-many, many-to-one, one-to-many or one-to-one. It is possible to discern this relationship by looking at the `is_multiselect` property on each attribute: if `true`, this attribute is a “many”, if `false` it is a “one”.
Unfortunately, at present it is not possible to create relationship attributes using the API; they can only be created in the web application and then used in the API.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#configuration)
Configuration
Record references are usually constrained to referencing a specific object. For example, you can’t specify a deal for the company `team` attribute. This is accomplished with the configuration property `allowed_object_ids` which is an array of object IDs (slugs are supported when writing this property):
Create "owner" attribute which only supports People
Copy
```
POST /v2/objects/:object/attributes HTTP/1.1
Authorization: Bearer <<oauth2>>
Content-Type: application/json
{
"title": "Owner",
"api_slug": "owner",
"type": "record-reference",
"config": {
"record_reference": {
"allowed_objects": ["person"]
}
}
}
```

In responses from the API, this appears as `allowed_object_ids`, like so:
Attribute definition response for "team" attribute
Copy
```
{
  "id": { ... },
  "title": "Team",
  "api_slug": "team",
  "type": "record-reference",
  "config": {
    "record_reference": {
      "allowed_object_ids": [
        "4e71c40b-7d35-463c-afcb-e339cfd6dbd1"
      ]
    }
  },
  ...
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#reading-values)
Reading values
Record reference values have two properties, `target_object` (the `api_slug` representing what kind of object it is) and `target_record_id` (the ID of the Record).
A reference to person@company.com
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "record-reference",
  "target_object": "people",
  "target_record_id": "891dcbfc-9141-415d-9b2a-2238a6cc012d"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#writing-values)
Writing values
There are multiple ways to write a record reference. Since it’s such a common operation, Attio provides special write functionality if the record reference only allows a single object and that object is one of our standard objects:
  * If the allowed object is a company, you can use the `domains` attribute.
  * If the allowed object is a person, you can use the `email_addresses` attribute.
  * If the allowed object is a user, you can use the `user_id` attribute.
  * If the allowed object is a workspace, you can use the `workspace_id` attribute.


Referencing a company
Referencing a person
Referencing a user
Referencing a workspace
Copy
```
{
  "associated_company": [
    {
      "domains": [{"domain": "company.com"}],
      "target_object": "companies"
    }
  ]
}
```

Furthermore, we allow writing to these attributes using string values.
  * If the allowed object is a company, string values will be interpreted as a domain.
  * If the allowed object is a person, string values will be interpreted as email addresses.
  * If the allowed object is a user, string values will be interpreted as `user_id` text values.
  * If the allowed object is a workspace, string values will be interpreted as `workspace_id` text values.


Domain
Domains
Email
Email
User
Users
Workspace
Workspaces
Copy
```
{
  "associated_company": "company.com"
}
```

If the attribute is multiselect (“many”), you can also pass these as a series of values like so:
It’s also possible to write record references using record IDs.
Using record IDs
Copy
```
{
  "associated_company": [
    {
      "target_record_id": "99a03ff3-0435-47da-95cc-76b2caeb4dab",
      "target_object": "companies"
    }
  ]
}
```

Note that the write will fail if the target record does not exist, i.e. you can’t create the target record automatically. For example, if you tried to assert a person and referenced a company that did not exist, the request would fail. This means that you need to do your writes in reverse-order, e.g. starting with the company that the person is linked to, then creating the person.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#filtering)
Filtering
Record reference values can be filtered by `target_object` and `target_record_id` using exact equality matches.
Find people with a given company
Find workspaces with a given user
Copy
```
{
  "filter": {
    "company": {
      "target_object": "companies",
      "target_record_id": "99a03ff3-0435-47da-95cc-76b2caeb4dab"
    }
  }
}
```

As well as exact equality matches, record reference values also support the `$in` operator.
Find people where their company's record_id is one of several possible values
Copy
```
{
  "filter": {
    "company": {
      "target_object": "companies",
      "target_record_id": {
        "$in": [
          "3aeb39cd-fed8-524e-94b8-1300549354ac",
          "8c5cd602-1297-45d2-a99c-14ae091cbac3"
        ]
      }
    }
  }
}
```

Record references are special, because they are also filterable using “paths”, also known as “drill-downs”. You can filter records based on attributes of the target records. `paths` is an array containing tuples of `(object type, attribute slug or ID)`, while `constraints` are applied to the attribute identified by the final path element.
For example, we could construct a filter like “find me Companies which have an employee named John”:
Companies with an employee named John
Copy
```
{
  "filter": {
    "path": [
      ["companies", "team"],
      ["people", "name"]
    ],
    "constraints": {
      "first_name": { "$eq": "John" }
    }
  }
}
```

Here, we’re using the `team` attribute on a Company, which is a multi-select record reference to the person record. We then look across at those related `people`, and their `name` attribute values. Finally, since `name` is a [(personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name) attribute, we can query against the `first_name` property.
Paths can be more complex, and even somewhat recursive. For example, if you had a `manager` attribute on the Person object, and it pointed to another Person, you could find people by who their manager’s manager’s manager was:
People by their manager's manager's manager
Copy
```
{
  "filter": {
    "path": [
      ["people", "manager"],
      ["people", "manager"],
    ],
    "constraints": {
      "target_object": "people",
      "target_record_id": "managers-manager-id"
    }
  }
}
```

Was this page helpful?
YesNo
[Rating](https://docs.attio.com/docs/attribute-types/attribute-types-rating)[Select](https://docs.attio.com/docs/attribute-types/attribute-types-select)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [A note about relationship attributes](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#a-note-about-relationship-attributes)
  * [Configuration](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#configuration)
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
