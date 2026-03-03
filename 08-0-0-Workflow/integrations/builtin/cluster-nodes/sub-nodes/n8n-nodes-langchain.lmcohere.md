---
title: Cohere Model node documentation
description: Learn how to use the Cohere Model node in n8n. Follow technical documentation to integrate Cohere Model node into your workflows.
contentType: [integration, reference]
---

# Cohere Model node

Use the Cohere Model node to use Cohere's models.

On this page, you'll find the node parameters for the Cohere Model node, and links to more resources.

This node lacks tools support, so it won't work with the [AI Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/index.md) node. Instead, connect it with the [Basic LLM Chain](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainllm.md) node.

```{note} Credentials
You can find authentication information for this node [here](/08-0-0-Workflow/integrations/builtin/credentials/cohere.md).
```

```{include} ../../../../../_snippets/integrations/builtin/cluster-nodes/sub-node-expression-resolution.md

```

## Node Options

* **Maximum Number of Tokens**: Enter the maximum number of tokens used, which sets the completion length.
* **Sampling Temperature**: Use this option to control the randomness of the sampling process. A higher temperature creates more diverse sampling, but increases the risk of hallucinations.

## Templates and examples
<!--
   see https://www.notion.so/n8n/Pull-in-templates-for-the-integrations-pages-37c716837b804d30a33b47475f6e3780
[[ templatesWidget(page.title, '[^']*') ]]
-->

## Related resources

Refer to [LangChains's Cohere documentation](https://js.langchain.com/docs/integrations/llms/cohere/) for more information about the service.

```{include} ../../../../../_snippets/integrations/builtin/cluster-nodes/langchain-overview-link.md

```



