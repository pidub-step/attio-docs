---
title: Location - Attio Docs
url: https://docs.attio.com/docs/attribute-types/attribute-types-location
crawled_at: unknown
depth: 3
parent_url: https://docs.attio.com/docs/attribute-types/attribute-types-timestamp
---

# Location - Attio Docs

**Source:** [https://docs.attio.com/docs/attribute-types/attribute-types-location](https://docs.attio.com/docs/attribute-types/attribute-types-location)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Attribute types
Location
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
# Location
A physical location in the world
Location attributes model a physical location in the world. We store all location properties (address lines, postcode, country code, etc) on a single attribute value, rather than separate attributes. This means that when working with locations, updates must be atomic—every property must be specified, even if it is null.
You’ll find an example of this attribute as `primary_location` on both person and company objects.
Locations have the following properties:
  * `line_1` - the first line of the address, e.g. `"1 Infinite Loop"`
  * `line_2` - the second line of the address e.g. `"Block 1"`
  * `line_3`, `line_4`, same as above
  * `locality` - the town, neighbourhood or area, e.g. `"Cupertino"`
  * `region` - the state, county, province or region, e.g. `"CA"`
  * `postcode` - the postal or zip code, e.g. `"95014"`
  * `country_code` - the ISO 3166-1 alpha-2 country code, e.g. `US`
  * `latitude` - latitudinal coordinates, e.g. `"37.331741"`
  * `longitude` - longitudinal coordinates, e.g. `"-122.030333"`


There are some properties which are not presently shown in the Attio app but are captured by the API—for example, address lines or postcodes.
### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-location#reading-values)
Reading values
Depending on your use case, there are various properties of a location that might be relevant for you. The API will return the full object as structured data, without attempting to format it:
Example: Apple Headquarters
Copy
```
{
  "active_from": "2023-04-03T15:21:06.447000000Z",
  "active_until": null,
  "created_by_actor": {...},
  "attribute_type": "location",
  "line_1": "1 Infinite Loop",
  "line_2": null,
  "line_3": null,
  "line_4": null,
  "locality": "Cupertino",
  "region": "CA",
  "postcode": "95014",
  "country_code": "US",
  "latitude": "37.331741",
  "longitude": "-122.030333",
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-location#writing-values)
Writing values
When writing location values, Attio will intelligently parse strings into structured location data.
json
Copy
```
{
  "primary_location": "1 Infinite Loop, Cupertino, CA, 95014, US"
}
```

You may also specify each location property explicitly using an object value. When using the object syntax, we require that updates to a location attribute must specify a value for every attribute, even if it is `null`.
Using object
Copy
```
{
  "primary_location": {
    "line_1": "1 Infinite Loop",
    "line_2": null,
    "line_3": null,
    "line_4": null,
    "locality": "Cupertino",
    "region": "CA",
    "postcode": "95014",
    "country_code": "US",
    "latitude": "37.331741",
    "longitude": "-122.030333"
  }
}
```

### 
[​](https://docs.attio.com/docs/attribute-types/attribute-types-location#filtering)
Filtering
The properties `line_1`, `line_2`, `line_3`, `line_4`, `locality`, `region` and `postcode` can all be filtered by `$eq`, `$contains`, `$starts_with` and `$ends_with` operators.
The property `country_code` can be filtered by `$eq` and `$starts_with` operators.
People in Cupertino, California
...where locality contains "cuper"
Copy
```
{
  "filter": {
    "primary_location": {
       "locality": "Cupertino",
       "region": "CA",
       "country_code": "US"
    }
  }
}
```

It is not currently possible to filter by latitude/longitude.
Was this page helpful?
YesNo
[Interaction](https://docs.attio.com/docs/attribute-types/attribute-types-interaction)[(Personal) name](https://docs.attio.com/docs/attribute-types/attribute-types-personal-name)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Reading values](https://docs.attio.com/docs/attribute-types/attribute-types-location#reading-values)
  * [Writing values](https://docs.attio.com/docs/attribute-types/attribute-types-location#writing-values)
  * [Filtering](https://docs.attio.com/docs/attribute-types/attribute-types-location#filtering)


Assistant
Responses are generated using AI and may contain mistakes.
