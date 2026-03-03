---
title: Tools AI Agent node documentation
description: Learn how to use the Tools Agent of the AI Agent node in n8n. Follow technical documentation to integrate the Tools Agent into your workflows.
contentType: [integration, reference]
priority: critical
---

# Tools AI Agent node

The Tools Agent uses external [tools](/08-0-0-Workflow/glossary.rst#ai-tool) and APIs to perform actions and retrieve information. It can understand the capabilities of different tools and determine which tool to use depending on the task. This agent helps integrate LLMs with various external services and databases.

This agent has an enhanced ability to work with tools and can ensure a standard output format.

The Tools Agent implements [Langchain's tool calling](https://js.langchain.com/docs/concepts/tool_calling/) interface. This interface describes available tools and their schemas. The agent also has improved output parsing capabilities, as it passes the parser to the model as a formatting tool.

Refer to [AI Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/index.md) for more information on the AI Agent node itself.

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/use-with-chat-trigger.md

```

This agent supports the following chat models:

* [OpenAI Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatopenai/index.md)
* [Groq Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatgroq.md)
* [Mistral Cloud Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatmistralcloud.md)
* [Anthropic Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatanthropic.md)
* [Azure OpenAI Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatazureopenai.md)

## Available tools

The Tools Agent can use the following tools:

* [Call n8n Workflow](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolworkflow.md)
* [Code](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolcode.md)
* [HTTP Request](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolhttprequest.md)
* [Action Network](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.actionnetwork.md)
* [ActiveCampaign](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.activecampaign.md)
* [Affinity](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.affinity.md)
* [Agile CRM](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.agilecrm.md)
* [Airtable](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.airtable/index.md)
* [APITemplate.io](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.apitemplateio.md)
* [Asana](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.asana.md)
* [AWS Lambda](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.awslambda.md)
* [AWS S3](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.awss3.md)
* [AWS SES](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.awsses.md)
* [AWS Textract](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.awstextract.md)
* [AWS Transcribe](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.awstranscribe.md)
* [Baserow](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.baserow.md)
* [Bubble](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.bubble.md)
* [Calculator](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolcalculator.md)
* [ClickUp](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.clickup.md)
* [CoinGecko](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.coingecko.md)
* [Compression](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.compression.md)
* [Crypto](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.crypto.md)
* [DeepL](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.deepl.md)
* [DHL](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.dhl.md)
* [Discord](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.discord/index.md)
* [Dropbox](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.dropbox.md)
* [Elasticsearch](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.elasticsearch.md)
* [ERPNext](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.erpnext.md)
* [Facebook Graph API](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.facebookgraphapi.md)
* [FileMaker](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.filemaker.md)
* [Ghost](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.ghost.md)
* [Git](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.git.md)
* [GitHub](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.github.md)
* [GitLab](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gitlab.md)
* [Gmail](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/index.md)
* [Google Analytics](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleanalytics.md)
* [Google BigQuery](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlebigquery.md)
* [Google Calendar](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecalendar/index.md)
* [Google Chat](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlechat.md)
* [Google Cloud Firestore](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudfirestore.md)
* [Google Cloud Realtime Database](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudrealtimedatabase.md)
* [Google Contacts](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecontacts.md)
* [Google Docs](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googledocs.md)
* [Google Drive](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googledrive/index.md)
* [Google Sheets](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlesheets/index.md)
* [Google Slides](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleslides.md)
* [Google Tasks](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googletasks.md)
* [Google Translate](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googletranslate.md)
* [Google Workspace Admin](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gsuiteadmin.md)
* [Gotify](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gotify.md)
* [Grafana](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.grafana.md)
* [GraphQL](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.graphql.md)
* [Hacker News](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.hackernews.md)
* [Home Assistant](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.homeassistant.md)
* [HubSpot](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.hubspot.md)
* [Jenkins](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.jenkins.md)
* [Jira Software](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.jira.md)
* [JWT](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.jwt.md)
* [Kafka](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.kafka.md)
* [LDAP](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.ldap.md)
* [Line](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.line.md)
* [LinkedIn](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.linkedin.md)
* [Mailcheck](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mailcheck.md)
* [Mailgun](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mailgun.md)
* [Mattermost](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mattermost.md)
* [Mautic](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mautic.md)
* [Medium](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.medium.md)
* [Microsoft Excel 365](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsoftexcel.md)
* [Microsoft OneDrive](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsoftonedrive.md)
* [Microsoft Outlook](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsoftoutlook.md)
* [Microsoft SQL](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsoftsql.md)
* [Microsoft Teams](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsoftteams.md)
* [Microsoft To Do](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.microsofttodo.md)
* [Monday.com](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mondaycom.md)
* [MongoDB](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mongodb.md)
* [MQTT](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mqtt.md)
* [MySQL](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.mysql/index.md)
* [NASA](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.nasa.md)
* [Nextcloud](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.nextcloud.md)
* [NocoDB](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.nocodb.md)
* [Notion](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.notion/index.md)
* [Odoo](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.odoo.md)
* [OpenWeatherMap](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.openweathermap.md)
* [Pipedrive](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.pipedrive.md)
* [Postgres](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.postgres/index.md)
* [Pushover](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.pushover.md)
* [QuickBooks Online](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.quickbooks.md)
* [QuickChart](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.quickchart.md)
* [RabbitMQ](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.rabbitmq.md)
* [Reddit](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.reddit.md)
* [Redis](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.redis.md)
* [RocketChat](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.rocketchat.md)
* [S3](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.s3.md)
* [Salesforce](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.salesforce.md)
* [Send Email](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.sendemail.md)
* [SendGrid](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.sendgrid.md)
* [SerpApi (Google Search)](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolserpapi.md)
* [Shopify](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.shopify.md)
* [Slack](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.slack.md)
* [Spotify](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.spotify.md)
* [Stripe](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.stripe.md)
* [Supabase](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.supabase/index.md)
* [Telegram](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.telegram/index.md)
* [Todoist](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.todoist.md)
* [TOTP](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.totp.md)
* [Trello](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.trello.md)
* [Twilio](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.twilio.md)
* [urlscan.io](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.urlscanio.md)
* [Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolvectorstore.md)
* [Webflow](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.webflow.md)
* [Wikipedia](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolwikipedia.md)
* [Wolfram|Alpha](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolwolframalpha.md)
* [WooCommerce](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.woocommerce.md)
* [Wordpress](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.wordpress.md)
* [X (Formerly Twitter)](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.twitter.md)
* [YouTube](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.youtube.md)
* [Zendesk](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.zendesk.md)
* [Zoho CRM](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.zohocrm.md)
* [Zoom](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.zoom.md)

## Node parameters

Configure the Tools Agent using the following parameters.

### Prompt

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/prompt.md

```

### Require Specific Output Format

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/output-format.md

```

## Node options

Refine the Tools Agent node's behavior using these options:

### System Message 

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/system-message.md

```

### Max Iterations

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/max-iterations.md

```

### Return Intermediate Steps

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/return-intermediate-steps.md

```

<!-- vale off -->
### Automatically Passthrough Binary Images
<!-- vale on -->

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-root-nodes/binary-images.md

```

### Enable Streaming

When enabled, the AI Agent sends data back to the user in real-time as it generates the answer. This is useful for long-running generations. This is enabled by default.

```{info} Streaming requirements
For streaming to work, your workflow must use a trigger that supports streaming responses, such as the [Chat Trigger](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/index.md) or [Webhook](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.webhook/index.md) node with **Response Mode** set to **Streaming**.
```

## Templates and examples

Refer to the main AI Agent node's [Templates and examples](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/index.md#templates-and-examples) section.

## Dynamic parameters for tools with `$fromAI()`

To learn how to dynamically populate parameters for app node tools, refer to [Let AI specify tool parameters with `$fromAI()`](/08-0-0-Workflow/advanced-ai/examples/using-the-fromai-function.md).

## Human review for tool calls

You can require human approval before the AI Agent executes specific tools. This is useful for tools that perform sensitive actions like sending messages, modifying records, or deleting data.

To add a human review step:

1. Click the tool connector on the AI Agent node.
2. In the Tools Panel, find the **Human review** section.
3. Select your preferred approval channel (Chat, Slack, Telegram, and more) and configure it.
4. Connect the tools that require approval to the human review step.

When the AI wants to use a gated tool, the workflow pauses and sends an approval request through your chosen channel. The recipient can approve (tool executes) or deny (action canceled).

For detailed setup instructions and best practices, refer to [Human-in-the-loop for AI tool calls](/08-0-0-Workflow/advanced-ai/human-in-the-loop-tools.md).

## Common issues

For common questions or issues and suggested solutions, refer to [Common issues](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/common-issues.md).


