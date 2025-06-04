---
title: Creating an app - Attio Docs
url: https://docs.attio.com/sdk/creating-an-app
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# Creating an app - Attio Docs

**Source:** [https://docs.attio.com/sdk/creating-an-app](https://docs.attio.com/sdk/creating-an-app)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Using the App SDK
Creating an app
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
# Creating an app
Learn how to build your first app with the App SDK
1
Create a new app
Head over to our [Developer dashboard](https://build.attio.com) and sign in with your Attio account.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/build-attio-screenshot.png)![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/build-attio-screenshot-dark.png)
Then, create a developer account. You should set the name of your account to the name of your company or organization.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/developer-account-creation.png)![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/developer-account-creation-dark.png)
Once you’ve created a developer account, you’ll be able to create an app. Give it a unique name and hit create.
2
Develop your app
Now that you’ve created your app, lets download your apps starter code. You can do this by following the quickstart instructions in the developer dashboard’s app information tab.
Fire up your favourite terminal and enter the `npx attio init` command.
Now that’s complete all that’s left to do is start running your app locally. To do this run `npx attio dev` in the project directory.
It will ask you to choose a workspace to develop your app in. We recommend creating a separate workspace for development that isn’t your main production Attio workspace. Once you choose a workspace you will be redirected to install the app.
3
Install your app
You should have been redirected to install your app in the previous step. Hit install to do that.
If you closed your browser tab, you can also head over to the Workspace settings > Apps page to find and install this app.
4
Try out your app
Now that your app is installed lets take a look at the example action we’ve added to Attio.
Head over to any record page. Click the three dots overflow menu button and you should see your app’s name listed as an option.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/app-action-button.png)![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/app-action-button-dark.png)
Click it, and it will reveal a dialog.
Congratulations! Your app is now running inside Attio.
5
Make changes
Lets try editing the dialog code. Head over to `hello-world-dialog.tsx`. And try changing some of the code in the dialog.
Hit save. Head back to Attio, close your dialog and re-open it by clicking the action button again. You should see your changes live.
Well done! You’re now well on your way to building apps in Attio.
Was this page helpful?
YesNo
[Introduction to the App SDK](https://docs.attio.com/sdk/introduction)[Sharing your app](https://docs.attio.com/sdk/sharing-your-app)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
