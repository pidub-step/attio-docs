---
title: App Install – Sequence Diagram - Attio Docs
url: https://docs.attio.com/diagrams/app-install-sequence
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/sdk/introduction
---

# App Install – Sequence Diagram - Attio Docs

**Source:** [https://docs.attio.com/diagrams/app-install-sequence](https://docs.attio.com/diagrams/app-install-sequence)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
App Install – Sequence Diagram
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
`
Attio Server SDKEvent HandlerAcme Lead CheckerAttio UIAttio Server SDKEvent HandlerAcme Lead CheckerAttio UIUserClicks to install appPrompts to add connection to ALCLogs in (OAuth flow)Redirects back with auth tokenShows app is now installedFires 'connection-added' eventCalls createWebhookHandler()Returns webhook handler detailsRegisters webhookUser
`
Assistant
Responses are generated using AI and may contain mistakes.
