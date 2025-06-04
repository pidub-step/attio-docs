---
title: Slugs and IDs - Attio Docs
url: https://docs.attio.com/docs/slugs-and-ids
crawled_at: unknown
depth: 1
parent_url: https://docs.attio.com/docs/
---

# Slugs and IDs - Attio Docs

**Source:** [https://docs.attio.com/docs/slugs-and-ids](https://docs.attio.com/docs/slugs-and-ids)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Further reading
Slugs and IDs
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
# Slugs and IDs
Attio uses [UUIDs](https://en.wikipedia.org/wiki/Universally_unique_identifier) (universally unique identifiers) to identify most of the objects in our system. We can also identify many API objects by their slug property. Slugs have the advantage that they are human-readable. For standard objects and attributes, slugs are also consistent across workspaces.
## 
[​](https://docs.attio.com/docs/slugs-and-ids#ids-and-uniqueness)
IDs and Uniqueness
Entities returned from Attio’s API contain an `id` property which is composed of one or more sub-IDs. The sub-IDs are each a UUID that identifies either the entity or one of its parents.
Example ID from a record response
Copy
```
{  
  "data": {  
    "id": {  
      "workspace_id": "5821c091-cf04-4aab-a72a-f1646dbd6841",  
      "object_id": "7c430b6d-fa5b-48c6-bfa7-9520c088c7bc",  
      "record_id": "d2c2f990-3af0-4be5-808a-5605549e787f"
    },  
    // ...  
  }  
}
```

Uniqueness of an ID is only guaranteed when the ID is taken as a whole, using all sub-IDs. For example, it is unsafe to assume in the example above that the record is the only record with `record_id=”d2c2f990-3af0-4be5-808a-5605549e787f”`.
The safe assumption is that the record is the only record with `record_id=”d2c2f990-3af0-4be5-808a-5605549e787f”`  _and_ `object_id=”7c430b6d-fa5b-48c6-bfa7-9520c088c7bc"`  _and_ `workspace_id="5821c091-cf04-4aab-a72a-f1646dbd6841"`.
In practice, such collisions will be rare, but they are important to bear in mind. This is especially true if you are building large integrations which operate on the data of many workspaces.
If you are only operating on data from your own workspace, you can essentially disregard the `workspace_id` key.
## 
[​](https://docs.attio.com/docs/slugs-and-ids#slugs)
Slugs
For ergonomics and readability, Attio’s API utilises slugs across a variety of entities such as list, objects and attributes. Path parameters, query parameters, request bodies and responses will utilise a unique slug instead of an ID where appropriate.
For example, a request to the [create record endpoint](https://docs.attio.com/rest-api/endpoint-reference/records/create-a-record) accepts values keyed by either the attribute slug or attribute ID and returns values keyed by slug.
Request
Copy
```
// Slug form
{
  "data": {
    "values": {
      "email_addresses": [
        {
          "email_address": "[email protected]"
        }
      ]
    }
    // other values...
  }
}
// ID form
{
  "data": {
    "values": {
      "8a8ad54f-9314-4bdb-b867-e62d02a7d333": [
        {
          "email_address": "[email protected]"
        }
      ]
    }
    // other values...
  }
}
```

Response
Copy
```
{
    "data": {
        "values": {
            "email_addresses": [
                {
                    "active_from": "2023-06-01T15:49:08.524000000Z",
                    "active_until": null,
                    "created_by_actor": {
                        "type": "api-token",
                        "id": "d475d597-2900-4c93-841c-9f83154f21dc"
                    },
                    "original_email_address": "[email protected]",
                    "email_address": "[email protected]",
                    "email_domain": "bell-labs.com",
                    "email_root_domain": "bell-labs.com",
                    "email_local_specifier": "r.hamming",
                    "attribute_type": "email-address"
                }
            ]
            // other values...
        }
        // other properties on data...
    }
}
```

Slugs are set explicitly over the API, or created automatically when entities are created through the UI. Slugs are not updated when entities are renamed through the UI, so they can be reliably used once seen. They are always unique across entities. For example, there cannot be two attributes with the same slug on the same list.
Slugs of system attributes and objects are consistent across time and across workspaces. Non-system slugs are mutable, so care should be taken when modifying them in case they break any integrations relying upon them. If you would like to provide resilience against such changes, please use IDs when looking up objects instead.
Slugs can be found on the following entities:
  * Object (`api_slug`)
  * Attribute (`api_slug`)
  * List (`api_slug`)
  * Status (`title`)
  * Select Option (`title`)


* * *
Was this page helpful?
YesNo
[Actors](https://docs.attio.com/docs/actors)[Default values](https://docs.attio.com/docs/default-values)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [IDs and Uniqueness](https://docs.attio.com/docs/slugs-and-ids#ids-and-uniqueness)
  * [Slugs](https://docs.attio.com/docs/slugs-and-ids#slugs)


Assistant
Responses are generated using AI and may contain mistakes.
