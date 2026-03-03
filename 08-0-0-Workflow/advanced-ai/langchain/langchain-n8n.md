---
contentType: explanation
title: LangChain concepts in n8n
description: How LangChain concepts map to n8n, and which n8n nodes to use.
---

# LangChain concepts in n8n

This page explains how LangChain concepts and features map to n8n nodes.

This page includes lists of the LangChain-focused nodes in n8n. You can use any n8n node in a workflow where you interact with LangChain, to link LangChain to other services. The LangChain features uses n8n's [Cluster nodes](/08-0-0-Workflow/integrations/builtin/cluster-nodes/index.md).

```{note}
n8n implements LangChain JS

This feature is n8n's implementation of [LangChain's JavaScript framework](https://js.langchain.com/docs/get_started/introduction).
```

## Trigger nodes

[Chat Trigger](/08-0-0-Workflow/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/index.md)

## Cluster nodes

--8<-- "_snippets/integrations/builtin/cluster-nodes/cluster-nodes-summary.md"

### Root nodes

Each cluster starts with one [root node](/08-0-0-Workflow/glossary.rst#root-node-n8n).

#### Chains

A [chain](/08-0-0-Workflow/glossary.rst#ai-chain) is a series of LLMs, and related tools, linked together to support functionality that can't be provided by a single LLM alone.

Available nodes:

* [Basic LLM Chain](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainllm.md)
* [Retrieval Q&A Chain](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainretrievalqa/index.md)
* [Summarization Chain](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainsummarization.md)
* [Sentiment Analysis](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.sentimentanalysis.md)
* [Text Classifier](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.text-classifier.md)

Learn more about [chaining in LangChain](https://js.langchain.com/docs/concepts/lcel).

#### Agents

> An [agent](/08-0-0-Workflow/glossary.rst#ai-agent){ data-preview} has access to a suite of tools, and determines which ones to use depending on the user input. Agents can use multiple tools, and use the output of one tool as the input to the next. [Source](https://github.com/langchain-ai/langchainjs/blob/def3a26c054575e1ed40b9062087e8c0a8899633/docs/core_docs/docs/modules/agents/index.mdx)

Available nodes:

* [Agent](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/index.md)

Learn more about [Agents in LangChain](https://js.langchain.com/docs/concepts/agents).

#### Vector stores

[Vector stores](/08-0-0-Workflow/glossary.rst#ai-vector-store) store embedded data, and perform vector searches on it.

* [Simple Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstoreinmemory.md)
* [PGVector Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstorepgvector.md)
* [Pinecone Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstorepinecone.md)
* [Qdrant Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstoreqdrant.md)
* [Supabase Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstoresupabase.md)
* [Zep Vector Store](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.vectorstorezep.md)

Learn more about [Vector stores in LangChain](https://js.langchain.com/docs/concepts/vectorstores/).

#### Miscellaneous

Utility nodes.

[LangChain Code](/08-0-0-Workflow/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.code.md): import LangChain. This means if there is functionality you need that n8n hasn't created a node for, you can still use it.

### Sub-nodes

Each root node can have one or more [sub-nodes](/08-0-0-Workflow/glossary.rst#sub-node-n8n) attached to it.

#### Document loaders

Document loaders add data to your chain as documents. The data source can be a file or web service.

Available nodes:

* [Default Document Loader](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.documentdefaultdataloader.md)
* [GitHub Document Loader](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.documentgithubloader.md)

Learn more about [Document loaders in LangChain](https://js.langchain.com/docs/concepts/document_loaders).

#### Language models

[LLMs (large language models)](/08-0-0-Workflow/glossary.rst#large-language-model-llm) are programs that analyze datasets. They're the key element of working with AI.

Available nodes:

* [Anthropic Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatanthropic.md)
* [AWS Bedrock Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatawsbedrock.md)
* [Cohere Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmcohere.md)
* [Hugging Face Inference Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmopenhuggingfaceinference.md)
* [Mistral Cloud Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatmistralcloud.md)
* [Ollama Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatollama/index.md)
* [Ollama Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmollama/index.md)
* [OpenAI Chat Model](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatopenai/index.md)

Learn more about [Language models in LangChain](https://js.langchain.com/docs/concepts/chat_models).

#### Memory

[Memory](/08-0-0-Workflow/glossary.rst#ai-memory) retains information about previous queries in a series of queries. For example, when a user interacts with a chat model, it's useful if your application can remember and call on the full conversation, not just the most recent query entered by the user.

Available nodes:

* [Motorhead](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memorymotorhead.md)
* [Redis Chat Memory](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memoryredischat.md)
* [Postgres Chat Memory](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memorypostgreschat.md) 
* [Simple Memory](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memorybufferwindow/index.md)
* [Xata](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memoryxata.md)
* [Zep](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memoryzep.md)

Learn more about [Memory in LangChain](https://langchain-ai.github.io/langgraphjs/concepts/memory/).

#### Output parsers

Output parsers take the text generated by an LLM and format it to match the structure you require.

Available nodes:

* [Auto-fixing Output Parser](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.outputparserautofixing.md)
* [Item List Output Parser](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.outputparseritemlist.md)
* [Structured Output Parser](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.outputparserstructured/index.md)

Learn more about [Output parsers in LangChain](https://js.langchain.com/docs/concepts/output_parsers/).

#### Retrievers


* [Contextual Compression Retriever](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.retrievercontextualcompression.md)
* [MultiQuery Retriever](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.retrievermultiquery.md)
* [Vector Store Retriever](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.retrievervectorstore.md)
* [Workflow Retriever](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.retrieverworkflow.md)


#### Text splitters

Text splitters break down data (documents), making it easier for the LLM to process the information and return accurate results.

Available nodes:

* [Character Text Splitter](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.textsplittercharactertextsplitter.md)
* [Recursive Character Text Splitter](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.textsplitterrecursivecharactertextsplitter.md)
* [Token Splitter](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.textsplittertokensplitter.md)

n8n's text splitter nodes implements parts of [LangChain's text_splitter API](https://js.langchain.com/docs/concepts/text_splitters/).

#### Tools

Utility [tools](/08-0-0-Workflow/glossary.rst#ai-tool).

* [Calculator](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolcalculator.md)
* [Code Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolcode.md)
* [SerpAPI](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolserpapi.md)
* [Think Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolthink.md)
* [Vector Store Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolvectorstore.md)
* [Wikipedia](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolwikipedia.md)
* [Wolfram|Alpha](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolwolframalpha.md)
* [Workflow Tool](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolworkflow.md)

#### Embeddings

> [Embeddings](/08-0-0-Workflow/glossary.rst#ai-embedding) capture the "relatedness" of text, images, video, or other types of information. ([source](https://supabase.com/docs/guides/ai/concepts))

Available nodes:


* [Embeddings AWS Bedrock](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingsawsbedrock.md)
* [Embeddings Cohere](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingscohere.md)
* [Embeddings Google PaLM](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingsgooglepalm.md)
* [Embeddings Hugging Face Inference](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingshuggingfaceinference.md)
* [Embeddings Mistral Cloud](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingsmistralcloud.md)
* [Embeddings Ollama](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingsollama.md)
* [Embeddings OpenAI](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingsopenai.md)

Learn more about [Text embeddings in LangChain](https://js.langchain.com/docs/concepts/embedding_models/).


#### Miscellaneous

* [Chat Memory Manager](/08-0-0-Workflow/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.memorymanager.md)




