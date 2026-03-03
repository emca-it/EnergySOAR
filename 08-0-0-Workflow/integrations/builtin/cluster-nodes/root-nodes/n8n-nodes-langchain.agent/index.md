---
title: AI Agent node documentation
description: Learn how to use the AI Agent node in n8n. Follow technical documentation to integrate AI Agent node into your workflows.
contentType: [integration, reference]
priority: critical
---

# AI Agent node

An [AI agent](/08-0-0-Workflow/glossary.rst#ai-agent) is an autonomous system that receives data, makes rational decisions, and acts within its environment to achieve specific goals. The AI agent's environment is everything the agent can access that isn't the agent itself. This agent uses external [tools](/08-0-0-Workflow/glossary.rst#ai-tool) and APIs to perform actions and retrieve information. It can understand the capabilities of different tools and determine which tool to use depending on the task. 

```{note} Connect a tool
You must connect at least one tool [sub-node](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/index.md) to an AI Agent node.
```

```{note} Agent type
Prior to version 1.82.0, the AI Agent had a setting for working as different agent types. This has now been removed and all AI Agent nodes work as a `Tools Agent` which was the recommended and most frequently used setting. If you're working with older versions of the AI Agent in workflows or templates, as long as they were set to 'Tools Agent', they should continue to behave as intended with the updated node.
```


## Templates and examples
<!--
   see https://www.notion.so/n8n/Pull-in-templates-for-the-integrations-pages-37c716837b804d30a33b47475f6e3780
[[ templatesWidget(page.title, '[^']*') ]]
-->

## Agent types

The AI Agent supports different agent types for specific use cases:

### Active agent types

* [Tools Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/tools-agent.md) - The default and recommended agent type. Uses external tools and APIs with enhanced tool-calling capabilities and standard output format support.
* [OpenAI Functions Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/openai-functions-agent.md) - Specialized agent for OpenAI function calling models. Requires the OpenAI Chat Model.
* [Plan and Execute Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/plan-execute-agent.md) - Creates a high-level plan first, then executes it step by step. Best for tasks requiring structured planning.

### Deprecated agent types

The following agent types were removed in February 2025:

* [Conversational Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/conversational-agent.md) (deprecated)
* [ReAct Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/react-agent.md) (deprecated)
* [SQL Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/sql-agent.md) (deprecated)

## Related resources

Refer to [LangChain's documentation on agents](https://js.langchain.com/docs/concepts/agents/) for more information about the service.

New to AI Agents? Read the [n8n blog introduction to AI agents](https://blog.n8n.io/ai-agents/).

```{include} ../../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-overview-link.md

```

## Common issues

For common errors or issues and suggested resolution steps, refer to [Common Issues](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/common-issues.md).




