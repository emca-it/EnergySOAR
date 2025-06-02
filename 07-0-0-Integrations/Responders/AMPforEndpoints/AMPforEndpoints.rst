AMPforEndpoints
===============

AMPforEndpoints_IsolationStart
------------------------------

.. rubric:: Details

===========================  ================================
Author                       Cisco Security
Version                      1.0
License                      MIT
Website                      https://github.com/CiscoSecurity
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  ================================

.. rubric:: Description

Start host isolation for an AMP for Endpoints connector

.. rubric:: Configuration

===========  ===================================================================================
Name         Description
amp_cloud    FQDN of the AMP for Endpoints cloud to interact with
client_id    Client ID for AMP for Endpoints
api_key      API Key for AMP for Endpoints
unlock_code  Custom unlock code used to stop isolation from the endpoint (Maximum 24 characters)
===========  ===================================================================================


AMPforEndpoints_IsolationStop
-----------------------------

.. rubric:: Details

===========================  ================================
Author                       Cisco Security
Version                      1.0
License                      MIT
Website                      https://github.com/CiscoSecurity
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  ================================

.. rubric:: Description

Stop host isolation for an AMP for Endpoints connector

.. rubric:: Configuration

=========  ====================================================
Name       Description
amp_cloud  FQDN of the AMP for Endpoints cloud to interact with
client_id  Client ID for AMP for Endpoints
api_key    API Key for AMP for Endpoints
=========  ====================================================


AMPforEndpoints_MoveGUID
------------------------

.. rubric:: Details

===========================  ================================
Author                       Cisco Security
Version                      1.0
License                      MIT
Website                      https://github.com/CiscoSecurity
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  ================================

.. rubric:: Description

Move an AMP for Endpoints connector GUID to a different Group

.. rubric:: Configuration

==========  ======================================================================
Name        Description
amp_cloud   FQDN of the AMP for Endpoints cloud to interact with
client_id   Client ID for AMP for Endpoints
api_key     API Key for AMP for Endpoints
group_guid  AMP for Endpoints Group GUID for the group connectors will be moved to
==========  ======================================================================


AMPforEndpoints_SCDAdd
----------------------

.. rubric:: Details

===========================  ================================
Author                       Cisco Security
Version                      1.0
License                      MIT
Website                      https://github.com/CiscoSecurity
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  ================================

.. rubric:: Description

Add a SHA256 to an AMP for Endpoints Simple Custom Detection list

.. rubric:: Configuration

=========  ====================================================
Name       Description
amp_cloud  FQDN of the AMP for Endpoints cloud to interact with
client_id  Client ID for AMP for Endpoints
api_key    API Key for AMP for Endpoints
scd_guid   AMP for Endpoints Simple Custom Detection GUID
=========  ====================================================


AMPforEndpoints_SCDRemove
-------------------------

.. rubric:: Details

===========================  ================================
Author                       Cisco Security
Version                      1.0
License                      MIT
Website                      https://github.com/CiscoSecurity
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  ================================

.. rubric:: Description

Remove a SHA256 to an AMP for Endpoints Simple Custom Detection list

.. rubric:: Configuration

=========  ====================================================
Name       Description
amp_cloud  FQDN of the AMP for Endpoints cloud to interact with
client_id  Client ID for AMP for Endpoints
api_key    API Key for AMP for Endpoints
scd_guid   AMP for Endpoints Simple Custom Detection GUID
=========  ====================================================

