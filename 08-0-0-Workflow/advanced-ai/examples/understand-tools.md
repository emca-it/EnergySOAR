---
title: What's a tool in AI?
description: Understand tools in the context of AI. Learn what's special about tools in n8n.
contentType: explanation
---

# What's a tool in AI?

In AI, 'tools' has a specific meaning. Tools act like addons that your AI can use to access extra context or resources.

Here are a couple of other ways of expressing it:

> Tools are interfaces that an agent can use to interact with the world ([source](https://langchain-ai.github.io/langgraphjs/how-tos/tool-calling/))

<!--  -->

> We can think of these tools as being almost like functions that your AI model can call ([source](https://www.udemy.com/course/chatgpt-and-langchain-the-complete-developers-masterclass/))

## AI tools in n8n

n8n provides tool [sub-nodes](/08-0-0-Workflow/glossary.rst#sub-node-n8n) that you can connect to your [AI agent](/08-0-0-Workflow/glossary.rst#ai-agent). As well as providing some popular tools, such as [Wikipedia](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolwikipedia.md) and [SerpAPI](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolserpapi.md), n8n provides three especially powerful tools:

* [Call n8n Workflow Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolworkflow.md): use this to load any n8n workflow as a tool.
* [Custom Code Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolcode.md): write code that your agent can run.
* [HTTP Request Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolhttprequest.md): make calls to fetch a website or data from an API.

The next three examples highlight the Call n8n Workflow Tool:

- [Chat with Google Sheets](/08-0-0-Workflow/advanced-ai/examples/data-google-sheets.md)
- [Call an API to fetch data](/08-0-0-Workflow/advanced-ai/examples/api-workflow-tool.md)
- [Set up a human fallback](/08-0-0-Workflow/advanced-ai/examples/human-fallback.md)

You can also learn how to [let AI dynamically specify parameters for tools with the `$fromAI()` function](/08-0-0-Workflow/advanced-ai/examples/using-the-fromai-function.md).

