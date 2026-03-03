---
title: Gmail node documentation
description: Learn how to use the Gmail node in n8n. Follow technical documentation to integrate Gmail node into your workflows.
contentType: [integration, reference]
priority: high
---

# Gmail node

Use the Gmail node to automate work in Gmail, and integrate Gmail with other applications. n8n has built-in support for a wide range of Gmail features, including creating, updating, deleting, and getting drafts, messages, labels, thread.  

On this page, you'll find a list of operations the Gmail node supports and links to more resources.

```{note} Credentials
Refer to [Google credentials](/08-0-0-Workflow/integrations/builtin/credentials/google/index.md) for guidance on setting up authentication. 
```

```{include} ../../../../../_snippets/integrations/builtin/app-nodes/ai-tools.md

```

## Operations

* **Draft**
	* [**Create**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/draft-operations.md#create-a-draft) a draft
	* [**Delete**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/draft-operations.md#delete-a-draft) a draft
	* [**Get**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/draft-operations.md#get-a-draft) a draft
	* [**Get Many**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/draft-operations.md#get-many-drafts) drafts
* **Label**
	* [**Create**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/label-operations.md#create-a-label) a label
	* [**Delete**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/label-operations.md#delete-a-label) a label
	* [**Get**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/label-operations.md#get-a-label) a label
	* [**Get Many**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/label-operations.md#get-many-labels) labels
* **Message**
	* [**Add Label**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#add-label-to-a-message) to a message
	* [**Delete**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#delete-a-message) a message
	* [**Get**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#get-a-message) a message
	* [**Get Many**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#get-many-messages) messages
	* [**Mark as Read**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#mark-as-read)
	* [**Mark as Unread**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#mark-as-unread)
	* [**Remove Label**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#remove-label-from-a-message) from a message
	* [**Reply**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#reply-to-a-message) to a message
	* [**Send**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/message-operations.md#send-a-message) a message
* **Thread**
	* [**Add Label**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#add-label-to-a-thread) to a thread
	* [**Delete**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#delete-a-thread) a thread
	* [**Get**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#get-a-thread) a thread
	* [**Get Many**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#get-many-threads) threads
	* [**Remove Label**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#remove-label-from-a-thread) from thread
	* [**Reply**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#reply-to-a-message) to a message
	* [**Trash**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#trash-a-thread) a thread
	* [**Untrash**](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/thread-operations.md#untrash-a-thread) a thread

## Templates and examples
<!--
   see https://www.notion.so/n8n/Pull-in-templates-for-the-integrations-pages-37c716837b804d30a33b47475f6e3780
[[ templatesWidget(page.title, '[^']*') ]]
-->

## Related resources

Refer to Google's [Gmail API documentation](https://developers.google.com/gmail/api) for detailed information about the API that this node integrates with.

n8n provides a trigger node for Gmail. You can find the trigger node docs [here](/08-0-0-Workflow/integrations/builtin/trigger-nodes/n8n-nodes-base.gmailtrigger/index.md).

```{include} ../../../../../_snippets/integrations/builtin/app-nodes/operation-not-supported.md

```

## Common issues

For common errors or issues and suggested resolution steps, refer to [Common Issues](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/common-issues.md).


