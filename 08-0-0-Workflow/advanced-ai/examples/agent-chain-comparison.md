---
contentType: explanation
title: Agents vs chains
description: A workflow example that demonstrates key differences between agents and chains.
---

# Demonstration of key differences between agents and chains

In this workflow you can choose whether your chat query goes to an [agent](/08-0-0-Workflow/glossary.rst#ai-agent) or [chain](/08-0-0-Workflow/glossary.rst#ai-chain). It shows some of the ways that agents are more powerful than chains.

[[ workflowDemo("file:///08-0-0-Workflow/advanced-ai/examples/agents_vs_chains.json") ]]

## Key features

This workflow uses:

* [Chat Trigger](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/index.md): start your workflow and respond to user chat interactions. The node provides a customizable chat interface.
* [Switch node](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-base.switch.md): directs your query to either the agent or chain, depending on which you specify in your query. If you say "agent" it sends it to the agent. If you say "chain" it sends it to the chain.
* [Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/index.md): the Agent node interacts with other components of the workflow and makes decisions about what [tools](/08-0-0-Workflow/glossary.rst#ai-tool) to use.
* [Basic LLM Chain](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainllm.md): the Basic LLM Chain node supports chatting with a connected LLM, but doesn't support [memory](/08-0-0-Workflow/glossary.rst#ai-memory) or tools.


## Using the example

--8<-- "_snippets/examples-color-key.md"

