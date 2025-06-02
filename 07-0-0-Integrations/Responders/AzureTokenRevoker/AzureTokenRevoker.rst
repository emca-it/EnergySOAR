AzureTokenRevoker
=================

AzureTokenRevoker
-----------------

.. rubric:: Details

===========================  =======================
Author                       Daniel Weiner @dmweiner
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case
===========================  =======================

.. rubric:: Description

Revoke all Microsoft Azure authentication session tokens for a list of User Principal Names

.. rubric:: Configuration

=============  ===============================================================================================
Name           Description
redirect_uri   Azure AD Application URI (Example: https://login.microsoftonline.com/TENANTIDHERE/oauth2/token)
client_id      Client ID/Application ID of Azure AD Registered App
client_secret  Secret for Azure AD Registered Application
=============  ===============================================================================================

