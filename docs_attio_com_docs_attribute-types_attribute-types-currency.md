---
title: Currency - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-currency
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Currency - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-currency](https://docs.attio.com/docs/attribute-types/attribute-types-currency)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Currency
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
# Currency
More than just numbers
Currency attributes represent quantities of money. They are similar to number attributes, allowing storing numbers with up to four decimal places of precision, but are presented differently in the UI with a currency symbol usually alongside.
Two examples of currency attributes are the `funding_raised_usd` attribute on the company object, and the `value` attribute on the deal object.
There is a `currency_code` property returned from the API on each attribute value, but please note that this is shared among all attribute values of the attribute; it is not possible to override currency for a particular record or entry.
Currency attributes can only be single-select.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-currency#configuration)
Configuration
When creating currency attributes, you can specify two configuration properties:
  * `default_currency_code` - The [ISO4217](https://www.iso.org/iso-4217-currency-codes.html) currency code e.g. `USD` or `EUR`. All values for the attribute inherit this value.
  * `display_type` How the currency should be displayed across the app. See [MDN for more details](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat#currencydisplay).


Specifying configuration when creating a currency attribute
Copy
```
POST /v2/objects/:object/attributes HTTP/1.1
Authorization: Bearer <<oauth2>>
Content-Type: application/json
{
"title": "Amount owed",
"api_slug": "amount_owed",
"type": "currency",
"config": {
"currency": {
"default_currency_code": "USD",
"display_type": "symbol"
}
}
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-currency#reading-values)
Reading values
Currency attributes have two properties, `currency_code` (string) and `currency_value` (number). This attribute does not support null values.
Example: $499.00
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "currency",
  "currency_value": "499.00",
  "currency_code": "USD"
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-currency#writing-values)
Writing values
Currency values can be written using floating point numbers. We accept values with up to 4 decimal places of precision. You do not need to pass floating point numbers explicitly; we will automatically convert integers to their floating point equivalents.
Where possible, Attio will convert strings into numbers. For example, the string `"4.99"` will be parsed as the float `4.99`.
As currency attributes may only be single-select, you may always write values without wrapping in an array if preferred.
We also support writing currency values using an object with a single key, `currency_value`.
Using float
Using string
Using object
Copy
```
{
  "amount_owed": 4.99
}
```

It is not possible to specify the `currency_code` since this is inherited from the attribute.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-currency#filtering)
Filtering
Currency attribute values can be filtered by their value, using either JSON strings or numbers. You can filter for an exact value using the implicit syntax, or use the `$eq`,`$gt`,`$gte`,`$lt`,`$lte` operators with the explicit syntax.
Finding records with an exact currency value
Currency at least 500
Copy
```
{
  "filter": {
    "amount_owed": "399.00"
  }
}
```

Was this page helpful?
YesNo
[Checkbox](https://docs.attio.com/docs/attribute-types/attribute-types-checkbox)[Date](https://docs.attio.com/docs/attribute-types/attribute-types-date)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Configuration](https://docs.attio.com/docs/attribute-types/attribute-types-currency#configuration)
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-currency#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-currency#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-currency#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
