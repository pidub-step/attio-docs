---
title: Design guidelines - Attio Docs
url: https://docs.attio.com/sdk/design-guidelines
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Design guidelines - Attio Docs

**Source:** [https://docs.attio.com/sdk/design-guidelines](https://docs.attio.com/sdk/design-guidelines)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Using the App SDK
Design guidelines
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Using the App SDK
  * [Introduction to the App SDK](https://docs.attio.com/sdk/introduction)
  * [Creating an app](https://docs.attio.com/sdk/creating-an-app)
  * [Sharing your app](https://docs.attio.com/sdk/sharing-your-app)
  * [Shipping updates](https://docs.attio.com/sdk/shipping-updates)
  * [Design guidelines](https://docs.attio.com/sdk/design-guidelines)


##### Actions
  * [RecordAction](https://docs.attio.com/sdk/actions/record-action)
  * [BulkRecordAction](https://docs.attio.com/sdk/actions/bulk-record-action)


##### Notifications
  * [Notifying the user](https://docs.attio.com/sdk/notifications/notifications)
  * [alert()](https://docs.attio.com/sdk/notifications/alert)
  * [confirm()](https://docs.attio.com/sdk/notifications/confirm)
  * [showToast()](https://docs.attio.com/sdk/notifications/show-toast)


##### Dialogs
  * [showDialog()](https://docs.attio.com/sdk/dialogs/show-dialog)


##### Components
  * [<Button />](https://docs.attio.com/sdk/components/button)
  * [<Checkbox />](https://docs.attio.com/sdk/components/checkbox)
  * [<Column />](https://docs.attio.com/sdk/components/column)
  * [<Combobox />](https://docs.attio.com/sdk/components/combobox)
  * [<Form />](https://docs.attio.com/sdk/components/form)
  * [<Link />](https://docs.attio.com/sdk/components/link)
  * [<NumberInput />](https://docs.attio.com/sdk/components/number-input)
  * [<Row />](https://docs.attio.com/sdk/components/row)
  * [<Section />](https://docs.attio.com/sdk/components/section)
  * [<SubmitButton />](https://docs.attio.com/sdk/components/submit-button)
  * [<TextBlock />](https://docs.attio.com/sdk/components/text-block)
  * [<TextInput />](https://docs.attio.com/sdk/components/text-input)
  * [<Toggle />](https://docs.attio.com/sdk/components/toggle)
  * [<Typography />](https://docs.attio.com/sdk/components/typography)
  * [<WithState />](https://docs.attio.com/sdk/components/with-state)


##### Forms
  * [Form schema](https://docs.attio.com/sdk/form-schema)


##### GraphQL
  * [Using GraphQL](https://docs.attio.com/sdk/graphql/graphql)
  * [runQuery()](https://docs.attio.com/sdk/graphql/run-query)


##### Hooks
  * [useAsyncCache()](https://docs.attio.com/sdk/hooks/use-async-cache)
  * [useForm()](https://docs.attio.com/sdk/hooks/use-form)
  * [useQuery()](https://docs.attio.com/sdk/hooks/use-query)


##### Server
  * [Server functions](https://docs.attio.com/sdk/server/server-functions)
  * [attioFetch()](https://docs.attio.com/sdk/server/attio-fetch)
  * Connections
  * Events
  * Webhooks


##### System
  * [platform](https://docs.attio.com/sdk/system/platform)


Using the App SDK
# Design guidelines
Icon and screenshot guidelines
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/icon-design-guidelines.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/icon-design-guidelines-dark.png)
## 
[​](https://docs.attio.com/sdk/design-guidelines#icon-guidelines)
Icon guidelines
When submitting an app to Attio, the icon you provide plays a crucial role in how your app is presented across different areas of the platform. To ensure a consistent and professional appearance, please adhere to the following specifications and best practices.
### 
[​](https://docs.attio.com/sdk/design-guidelines#general-specifications)
General Specifications
  * **Minimum Size:** 280px by 280px (ensures high-quality rendering on all screens, especially on retina displays).
  * **No Rounded Corners:** Attio automatically applies a **30% corner radius** based on the icon size.
  * **Format:** PNG (without transparency) for optimal display quality.
  * **Inset Outline:** Attio automatically adds a **10% opacity inset outline** to icons.


### 
[​](https://docs.attio.com/sdk/design-guidelines#corner-radius-reference)
**Corner Radius Reference**
For different icon sizes, use the following corner radii as a reference:
Icon Size | Corner Radius  
---|---  
1000px | 300px  
500px | 150px  
280px | 84px  
### 
[​](https://docs.attio.com/sdk/design-guidelines#icon-display-specifications)
Icon Display Specifications
Placement | Size  
---|---  
App Details Page | 230px by 144px  
App Store | 720px by 462px  
Action Buttons | 14px by 14px  
### 
[​](https://docs.attio.com/sdk/design-guidelines#additional-considerations)
Additional Considerations
  * **Consistency:** Ensure the icon remains visually clear and recognizable at both small and large sizes.
  * **Color Compatibility:** Make sure the icon is effective on both light and dark backgrounds within the platform.


* * *
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/images.png) ![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/images-dark.png)
## 
[​](https://docs.attio.com/sdk/design-guidelines#screenshot-guidelines)
Screenshot Guidelines
Screenshots are essential for showcasing your app on the Attio marketplace. To maintain high quality and consistency, please follow these specifications and best practices.
### 
[​](https://docs.attio.com/sdk/design-guidelines#general-specifications-2)
General Specifications
  * **Aspect Ratio:** 16:10
  * **Size:** 2220px by 1387px (ensures high-quality rendering on all screens).
  * **No Rounded Corners:** Attio applies the necessary corner radius automatically.


### 
[​](https://docs.attio.com/sdk/design-guidelines#screenshot-display-specifications)
Screenshot Display Specifications
Placement | Size | Corner Radius  
---|---|---  
Thumbnail Display | 230px by 144px | 12px  
Full-View Overlay | 720px by 462px | 16px  
Was this page helpful?
YesNo
[Shipping updates](https://docs.attio.com/sdk/shipping-updates)[RecordAction](https://docs.attio.com/sdk/actions/record-action)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
On this page
  * [Icon guidelines](https://docs.attio.com/sdk/design-guidelines#icon-guidelines)
  * [General Specifications](https://docs.attio.com/sdk/design-guidelines#general-specifications)
  * [Corner Radius Reference](https://docs.attio.com/sdk/design-guidelines#corner-radius-reference)
  * [Icon Display Specifications](https://docs.attio.com/sdk/design-guidelines#icon-display-specifications)
  * [Additional Considerations](https://docs.attio.com/sdk/design-guidelines#additional-considerations)
  * [Screenshot Guidelines](https://docs.attio.com/sdk/design-guidelines#screenshot-guidelines)
  * [General Specifications](https://docs.attio.com/sdk/design-guidelines#general-specifications-2)
  * [Screenshot Display Specifications](https://docs.attio.com/sdk/design-guidelines#screenshot-display-specifications)


Assistant
Responses are generated using AI and may contain mistakes.
