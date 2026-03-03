---
title: Google credentials
description: Documentation for Google credentials. Use these credentials to authenticate Google in n8n, a workflow automation platform.
contentType: overview
---

# Google credentials

This section contains:

* [OAuth2 single service](/08-0-0-Workflow/integrations/builtin/credentials/google/oauth-single-service.md): Create an OAuth2 credential for a specific service node, such as the Gmail node.
* [OAuth2 generic](/08-0-0-Workflow/integrations/builtin/credentials/google/oauth-generic.md): Create an OAuth2 credential for use with [custom operations](/08-0-0-Workflow/integrations/custom-operations.md).
* [Service Account](/08-0-0-Workflow/integrations/builtin/credentials/google/service-account.md): Create a [Service Account](https://cloud.google.com/iam/docs/service-account-overview) credential for some specific service nodes.
* [Google PaLM and Gemini](/08-0-0-Workflow/integrations/builtin/credentials/googleai.md): Get a Google Gemini/Google PaLM API key.


## OAuth2 and Service Account

There are two authentication methods available for Google services nodes:

* [OAuth2](https://developers.google.com/identity/protocols/oauth2): Recommended because it's more widely available and easier to set up.
* [Service Account](https://cloud.google.com/iam/docs/understanding-service-accounts): Refer to the [Google documentation: Understanding service accounts](https://cloud.google.com/iam/docs/understanding-service-accounts) for guidance on when you need a service account.

```{include} ../../../../../_snippets/integrations/managed-google-oauth.md
```

## Compatible nodes

Once configured, you can use your credentials to authenticate the following nodes. Most nodes are compatible with OAuth2 authentication. Support for Service Account authentication is limited.


| Node | OAuth | Service Account |
| :--- | :---: | :-------------: |
| [Google Ads](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleads.md) | :white_check_mark: | :x: |
| [Gmail](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gmail/index.md) | :white_check_mark: | :warning: |
| [Google Analytics](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleanalytics.md) | :white_check_mark: | :x: |
| [Google BigQuery](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlebigquery.md) | :white_check_mark: | :white_check_mark: |
| [Google Books](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlebooks.md) | :white_check_mark: | :white_check_mark: |
| [Google Calendar](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecalendar/index.md) | :white_check_mark: | :x: |
| [Google Chat](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlechat.md) | :white_check_mark: | :white_check_mark: |
| [Google Cloud Storage](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudstorage.md) | :white_check_mark: | :x: |
| [Google Contacts](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecontacts.md) | :white_check_mark: | :x: |
| [Google Cloud Firestore](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudfirestore.md) | :white_check_mark: | :white_check_mark: |
| [Google Cloud Natural Language](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudnaturallanguage.md) | :white_check_mark: | :x: |
| [Google Cloud Realtime Database](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlecloudrealtimedatabase.md) | :white_check_mark: | :x: |
| [Google Docs](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googledocs.md) | :white_check_mark: | :white_check_mark: |
| [Google Drive](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googledrive/index.md) | :white_check_mark: | :white_check_mark: |
| [Google Drive Trigger](/08-0-0-Workflow/integrations/builtin/trigger-nodes/n8n-nodes-base.googledrivetrigger/index.md) | :white_check_mark: | :white_check_mark: |
| [Google Perspective](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleperspective.md) | :white_check_mark: | :x: |
| [Google Sheets](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googlesheets/index.md) | :white_check_mark: | :white_check_mark: |
| [Google Slides](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googleslides.md) | :white_check_mark: | :white_check_mark: |
| [Google Tasks](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googletasks.md) | :white_check_mark: | :x: |
| [Google Translate](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.googletranslate.md) | :white_check_mark: | :white_check_mark: |
| [Google Workspace Admin](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.gsuiteadmin.md) | :white_check_mark: | :x: |
| [YouTube](/08-0-0-Workflow/integrations/builtin/app-nodes/n8n-nodes-base.youtube.md) | :white_check_mark: | :x: |

```{warning} Gmail and Service Accounts
Google technically supports Service Accounts for use with Gmail, but it requires enabling domain-wide delegation, which Google discourages, and its behavior can be inconsistent.

n8n recommends using OAuth2 with the Gmail node.
```
