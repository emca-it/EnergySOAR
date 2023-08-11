Gmail
=====

Gmail_BlockDomain
-----------------

.. rubric:: Details

===========================  ===================================
Author                       David Strassegger, @oscd_initiative
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  ===================================

.. rubric:: Description

Move emails from a given domain to trash

.. rubric:: Configuration

====================  ========================================
Name                  Description
thehive_url           URL for thehive instance
thehive_api_key       API key for TheHive instance
gmail_domain          Gsuite Domain
gmail_project_id      GCP Project ID
gmail_private_key_id  Service account private key id
gmail_private_key     Service Account private key (PEM Format)
gmail_client_email    Service Account E-Mail address
gmail_client_id       OAuth Client ID
====================  ========================================


Gmail_BlockSender
-----------------

.. rubric:: Details

===========================  ===================================
Author                       David Strassegger, @oscd_initiative
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  ===================================

.. rubric:: Description

Move emails from a given sender to trash

.. rubric:: Configuration

====================  ========================================
Name                  Description
thehive_url           URL for thehive instance
thehive_api_key       API key for TheHive instance
gmail_domain          Gsuite Domain
gmail_project_id      GCP Project ID
gmail_private_key_id  Service account private key id
gmail_private_key     Service Account private key (PEM Format)
gmail_client_email    Service Account E-Mail address
gmail_client_id       OAuth Client ID
====================  ========================================


Gmail_DeleteMessage
-------------------

.. rubric:: Details

===========================  ===================================
Author                       David Strassegger, @oscd_initiative
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  ===================================

.. rubric:: Description

Move a given message into the trash folder

.. rubric:: Configuration

====================  ========================================
Name                  Description
thehive_url           URL for thehive instance
thehive_api_key       API key for TheHive instance
gmail_domain          Gsuite Domain
gmail_project_id      GCP Project ID
gmail_private_key_id  Service account private key id
gmail_private_key     Service Account private key (PEM Format)
gmail_client_email    Service Account E-Mail address
gmail_client_id       OAuth Client ID
====================  ========================================


Gmail_UnblockDomain
-------------------

.. rubric:: Details

===========================  ===================================
Author                       David Strassegger, @oscd_initiative
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  ===================================

.. rubric:: Description

Remove a message filter for a given domain

.. rubric:: Configuration

====================  ========================================
Name                  Description
thehive_url           URL for thehive instance
thehive_api_key       API key for TheHive instance
gmail_domain          Gsuite Domain
gmail_project_id      GCP Project ID
gmail_private_key_id  Service account private key id
gmail_private_key     Service Account private key (PEM Format)
gmail_client_email    Service Account E-Mail address
gmail_client_id       OAuth Client ID
====================  ========================================


Gmail_UnblockSender
-------------------

.. rubric:: Details

===========================  ===================================
Author                       David Strassegger, @oscd_initiative
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  ===================================

.. rubric:: Description

Remove a message filter for a given sender

.. rubric:: Configuration

====================  ========================================
Name                  Description
thehive_url           URL for thehive instance
thehive_api_key       API key for TheHive instance
gmail_domain          Gsuite Domain
gmail_project_id      GCP Project ID
gmail_private_key_id  Service account private key id
gmail_private_key     Service Account private key (PEM Format)
gmail_client_email    Service Account E-Mail address
gmail_client_id       OAuth Client ID
====================  ========================================


.. rubric:: Additional details from the README file:


Gmail responder
^^^^^^^^^^^^^^^

This responder allows mailbox manipulation of Gsuite / Google Workspace accounts. The responder
can be used to implement message filters and delete message in a mailbox of a Gmail user.

**Usage:**


* You can block ``mail`` and ``domain`` observables
* Operations are carried out against all gmail addresses (dataType ``mail``\ ) in the case

  * Example: ``john.doe@gmail.com`` or ``peter.parker@custom.domain``
  * Custom domain can be set in the responder config

* The *message ID* of deleted messages is added as tag to the respective gmail address (dataType ``mail``\ )

  * Messages can only be deleted via Gmail query syntax (datatype ``other``\ ); this enables one to bulk delete a lot of messages

* The *filter ID* of a blocked ``domain`` or ``mail`` gets added as tag to respective gmail address (dataType ``mail``\ )
* All observables that get blocked/unblocked get a ``gmail:handled`` tag

**Constrains:**


* TheHive API key needs to provide **read** AND **write** permissions
* The Gmail user **MUST** be part of a Gsuite domain.
* Gsuite domain **MUST** have an *service account* enabled with domain-wide delegation.
* The *service account* **MUST** be configured with the following OAuth Scopes:

  * ``https://mail.google.com/``
  * ``https://www.googleapis.com/auth/gmail.settings.basic``

How to setup a Gmail service account
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The responder needs a Gmail *service account* with domain-wide delegation. The rough setup steps are:


#. enable a *service account* via GCP
#. enable Gmail API
#. get service account ``client_id`` (\ *oauth approval screens + domain-wide delegation needed*\ )
#. change to Gsuite Admin panel
#. add third party app (security->API controls) with ``client_id``
#. add domain-wide delegation with ``client_id``

A detailed guideline for a *service account* setup can be found in the `Google OAuth Python Client Docs <https://github.com/googleapis/google-api-python-client/blob/master/docs/oauth-server.md>`_.

