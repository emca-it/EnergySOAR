MSDefenderOffice365
===================

.. image:: ./assets/MicrosoftDefenderForOffice365_logo.png
   :alt: logo

MSDefenderOffice365_block
-------------------------

.. rubric:: Details

===========================  =======================================================================================================================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           thehive:case_artifact
Service Homepage             `MSDefenderOffice365_block <https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/defender-for-office-365?view=o365-worldwide>`_
===========================  =======================================================================================================================================================

.. rubric:: Description

Add entries to the Tenant Allow/Block List in the Microsoft 365 Defender

.. rubric:: Configuration

=====================  ===========================================================================================
Name                   Description
certificate_base64     Base64-encoded PFX certificate to be used for certificate-based authentication.
certificate_password   Password for the certificate used to authenticate
app_id                 The application ID of the service principal that's used in certificate based authentication
organization           Tenant ID. Example: something.onmicrosoft.com
block_expiration_days  How many days out should we set the expiration? A value <= 0 means to set no expiration.
=====================  ===========================================================================================


MSDefenderOffice365_unblock
---------------------------

.. rubric:: Details

===========================  =========================================================================================================================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           thehive:case_artifact
Service Homepage             `MSDefenderOffice365_unblock <https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/defender-for-office-365?view=o365-worldwide>`_
===========================  =========================================================================================================================================================

.. rubric:: Description

Add entries to the Tenant Allow/Block List in the Microsoft 365 Defender

.. rubric:: Configuration

====================  ===========================================================================================
Name                  Description
certificate_base64    Base64-encoded PFX certificate to be used for certificate-based authentication.
certificate_password  Password for the certificate used to authenticate
app_id                The application ID of the service principal that's used in certificate based authentication
organization          Tenant ID. Example: something.onmicrosoft.com
====================  ===========================================================================================


.. rubric:: Additional details from the README file:


Microsoft Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools. Defender for Office 365 includes:


* Threat protection policies: Define threat-protection policies to set the appropriate level of protection for your organization.
* Reports: View real-time reports to monitor Defender for Office 365 performance in your organization.
* Threat investigation and response capabilities: Use leading-edge tools to investigate, understand, simulate, and prevent threats.
* Automated investigation and response capabilities: Save time and effort investigating and mitigating threats.

This responder implements support for the Tenant Allow/Block List which is used during mail flow for incoming messages to manually override the Microsoft 365 filtering verdicts. An observable with dataType 'mail' is used to block/unblock a sender, while dataType 'domain' is used to block/unblock a domain.

You can also block or unblock multiple entries at once by using a multi-line observable with one entry per line.

The configuration allows you to specify the number of days for a block entry to live before expiration with a value of 0 meaning no expiration.

For further reference on this capability, see the Microsoft documentation `Allow or block emails using the Tenant Allow/Block List <https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/allow-block-email-spoof?view=o365-worldwide>`_.

