---
title: How to apply filters and sorts - Attio Docs
url: https://docs.attio.com/rest-api/how-to/filtering-and-sorting
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# How to apply filters and sorts - Attio Docs

**Source:** [https://docs.attio.com/rest-api/how-to/filtering-and-sorting](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
How-to guides
How to apply filters and sorts
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Introduction
  * [Overview](https://docs.attio.com/rest-api/overview)


##### How-to guides
  * [How to authenticate requests](https://docs.attio.com/rest-api/how-to/authentication)
  * [How to handle rate limits](https://docs.attio.com/rest-api/how-to/rate-limiting)
  * [How to apply filters and sorts](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)
  * [How to paginate API results](https://docs.attio.com/rest-api/how-to/pagination)
  * [How to configure webhooks](https://docs.attio.com/rest-api/how-to/webhooks)


##### Tutorials
  * [Connect an app to Attio through OAuth](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth)


##### Endpoint reference
  * [OpenAPI](https://docs.attio.com/rest-api/endpoint-reference/openapi)
  * Core endpoints
  * Standard objects
  * OAuth 2.0


##### Webhook reference
  * Webhook events


How-to guides
# How to apply filters and sorts
Searching for just the records you need
Some of our endpoints allow specifying `filter` or `sorts` objects as part of the request. These properties can help reduce the size of the result set or get them back in a more appropriate order.
## 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#filtering)
Filtering
Attio supports two distinct formats for filtering. There is the verbose format, which supports a wider variety of operators and conditions, and a shorthand format, which is useful for quick equality checks.
### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#shorthand-filters)
Shorthand filters
Shorthand filters generally look like this:
People called "John Smith" with the email "john@smith.com"
Copy
```
POST /v2/objects/companies/records/query
Content-Type: application/json
{
  "filter": {
    "name": "John Smith",
    "email_addresses": "john@smith.com"
  }
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#verbose-filters)
Verbose filters
Verbose filters allow joining multiple different conditions together, or querying for different properties of the attribute value. All shorthand syntaxes can be expressed in the verbose syntax. For example, the above filter can also be written as:
Copy
```
POST /v2/objects/companies/records/query
Content-Type: application/json
{
  "filter": {
    "$and": [
      {
        "name": {
          "full_name": {
            "$eq": "John Smith"
          }
        }
      },
      {
        "email_addresses": {
          "email_address": {
            "$eq": "john@smith.com"
          }
        }
      }
    ]
  }
}
```

Note that we’re using a logical operator (`$and`) to combine these two conditions, and that we’re querying specific properties on the attributes (`full_name` and `normalized_email_address`).
Each attribute type has specific properties available, and so the set of possible filters varies by attribute type, but every attribute type is filterable in some way. We have examples of filtering by each attribute type in our [attribute types documentation](https://docs.attio.com/docs/attribute-types).
Next, let’s walk through some more advanced filtering, starting with the comparison operators.
## 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#comparison-operators)
Comparison operators
There are nine comparison operators in total.
`$eq` is by far the most common, this operator checks for equality. It is supported by every attribute type. If you’re using shorthand syntax, this is usually the implied operator, but it can also be specified explicitly:
Deals with an exact name
Copy
```
{
    "name": {
        "$eq": "Contract with Apple"
    }
}
```

`$not_empty` is also available on some attribute types, this operator allows filtering results based on whether there is any value defined at all, for example:
Companies which have at least one domain
Copy
```
{
    "domains": {
        "$not_empty": true
    }
}
```

`$in`can be used to check if the record or entry has a value that is part of a set.
Records where record_id is one of many values
Copy
```
{
    "filter": {
        "record_id": {
            "$in": ["000e8881-37cc-41d2-bc22-39fe35e76e6b", "592dc9d8-548b-4148-813f-1259055ca83c"]
        }
    }
}
```

There are also operators for string properties and numeric/date properties:
### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#string-comparisons)
String comparisons
For string-like properties or attributes, there are three further operators. `$contains` can be used for matching parts of a string, case-insensitively:
Companies in New York
Copy
```
{
    "primary_location": {
        "locality": {
            "$contains": "new york"
        }
    }
}
```

Companies with "LTD" in the name
Copy
```
{
    "name": {
        "$contains": "LTD"
    }
}
```

`$starts_with` and `$ends_with` can match on the beginning or the end of the string, respectively:
People with phone numbers starting +44
Copy
```
{
    "phone_numbers": {
        "$starts_with": "+44"
    }
}
```

People with a job title "X engineer"
Copy
```
{
    "job_title": {
        "$ends_with": "of things"
    }
}
```

Note that these can be combined on the same property or attribute to achieve a logical AND:
Phone number starts with +44 and ends with 798
Copy
```
{
    "phone_numbers": {
        "$starts_with": "+44",
        "$ends_with": "798"
    }
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#numeric-or-date-comparisons)
Numeric or date comparisons
There are four operators for comparing sortable properties like numbers or dates:
  1. **Less than** (`$lt`), finds records where the value is strictly less than (exclusive) the given value
  2. **Less than or equal** (`$lte`), finds records where the value is either less than or the same as the given value
  3. **Greater than or equal** (`$gte`), finds records where the value is either greater than or the same as the given value
  4. **Greater than** (`$gt`), finds records where the value is strictly more than (exclusive) the given value


People with 1000 or more Twitter followers
Copy
```
{
    "twitter_follower_count": {
        "$gte": 1000
    }
}
```

People with between 100 and 200 followers
Copy
```
{
    "twitter_follower_count": {
        "$gte": 100,
        "$lt": 200
    }
}
```

You can also combine multiple comparators to find values between two points:
Companies founded in 2019
Copy
```
{
    "foundation_date": {
        "$gte": "2019-01-01",
        "$lte": "2019-12-31"
    }
}
```

## 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#logical-operators)
Logical operators
You can combine multiple conditions using the `$and`, `$or` and `$not` operators.
### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24and-operator)
`$and` operator
`$and` specifies that all conditions must match. If using the shorthand syntax with multiple attributes, this operator is implied. Note that you can also use the shorthand syntax for individual conditions—see the following example.
Deals assigned to Lauren in the "In Progress" state
Copy
```
{
    "$and": [
        {"stage": "In Progress"},
        {
            "owner": {
                "referenced_actor_type": "workspace-member",
                "referenced_actor_id": "[laurens-id]"
            }
        }
    ]
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24or-operator)
`$or` operator
`$or` specifies that at least one of the conditions must match. It is not an exclusive-or, if all conditions match it will still pass.
List entries on a kanban board in either the "One" or "Two" stage
Copy
```
{
    "$or": [{"stage": "One"}, {"stage": "Two"}]
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24not-operator)
`$not` operator
Attio doesn’t offer negative operators, for example there is no inverse of `$eq` like `$neq`. Instead, filters should be wrapped using the `$not` operator, which matches all documents which don’t meet the condition.
People not called John
Copy
```
{
    "$not": {
        "name": {
            "first_name": "John"
        }
    }
}
```

Deals not in the "In Progress" state
Copy
```
{
    "$not": {
        "stage": "In Progress"
    }
}
```

### 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#combining-logical-operators)
Combining logical operators
It’s possible to combine logical operators to build up trees of filters. For example, you could express multiple `$and` conditions, where some of them are a `$not`:
Companies with Apple in their name that aren't using an apple domain
Copy
```
{
    "$and": [
        {"name": {"$contains": "Apple"}},
        {
            "$not": {
                "domains": {
                    "root_domain": "apple.com"
                }
            }
        }
    ]
}
```

Or you could query for “deals that are owned by Alice or Bob that are worth more than $500:
Deals owned by Alice/Bob worth more than $500
Copy
```
{
    "$and": [
        {
            "$or": [
                {
                    "owner": {
                        "referenced_actor_type": "workspace-member",
                        "referenced_actor_id": "[alices-id]"
                    }
                },
                {
                    "owner": {
                        "referenced_actor_type": "workspace-member",
                        "referenced_actor_id": "[bobs-id]"
                    }
                }
            ]
        },
        {
            "value": {
                "$gt": 500
            }
        }
    ]
}
```

## 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#paths-and-parents)
Paths and parents
For [record reference attributes](https://docs.attio.com/docs/attribute-types/attribute-types-record-reference), it’s possible to use special `path` filtering by drilling down into the target objects. This filtering method is also supported on list entries.
For example, let’s assume we have a list of people we want to hire, called “Candidates” (the `api_slug` is `candidates`). We could then write a query to find entries where the person has an `@apple.com` email address:
List entries filtered by their parent record email
Copy
```
{
    "path": [
        ["candidates", "parent_record"],
        ["people", "email_addresses"]
    ],
    "constraints": {
        "email_domain": "apple.com"
    }
}
```

Note that we’re using a special attribute called `parent_record` that we can use for filtering any list entry. We can even use these drill-down queries to express a more complicated query, like “entries where the candidate works at the same company as Steve Jobs”:
Candidates who have worked with Steve Jobs
Copy
```
{
    "path": [
        ["candidates", "parent_record"],
        ["people", "company"],
        ["company", "team"]
    ],
    "constraints": {
        "target_object": "people",
        "target_record_id": "[steve-jobs-record-id]"
    }
}
```

## 
[​](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#sorting)
Sorting
Sorting allows us to get our results back in a particular order, based on attribute values. Each sort must specify a `direction`. If the target attribute is composed of multiple properties (like [(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)), `field` can also be specified.
We can do sorting by `attribute`, which is either a slug or ID. For example, we could sort People by their last name, then their email address:
People sorted by last name, then email
Copy
```
{
    "sorts": [
        {"direction": "asc", "attribute": "name", "field": "last_name"},
        {"direction": "desc", "attribute": "email_addresses"}
    ]
}
```

We can also sort using paths, which works similarly to filtering by path. Instead of specifying `attribute`, you specify a `path` property which resolves to the attribute of the related record(s):
People sorted by their Company name
Copy
```
{
    "sorts": [
        {
            "direction": "asc",
            "path": [
                ["people", "company"],
                ["companies", "name"]
            ]
        }
    ]
}
```

Was this page helpful?
YesNo
[How to handle rate limits](https://docs.attio.com/rest-api/how-to/rate-limiting)[How to paginate API results](https://docs.attio.com/rest-api/how-to/pagination)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Filtering](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#filtering)
  * [Shorthand filters](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#shorthand-filters)
  * [Verbose filters](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#verbose-filters)
  * [Comparison operators](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#comparison-operators)
  * [String comparisons](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#string-comparisons)
  * [Numeric or date comparisons](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#numeric-or-date-comparisons)
  * [Logical operators](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#logical-operators)
  * [$and operator](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24and-operator)
  * [$or operator](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24or-operator)
  * [$not operator](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#%24not-operator)
  * [Combining logical operators](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#combining-logical-operators)
  * [Paths and parents](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#paths-and-parents)
  * [Sorting](https://docs.attio.com/rest-api/how-to/filtering-and-sorting#sorting)


Assistant
Responses are generated using AI and may contain mistakes.
