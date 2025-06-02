PaloAltoCortexXDR
=================

.. image:: ./assets/cortex_logo.png
   :alt: logo

PaloAltoCortexXDR_isolate
-------------------------

.. rubric:: Details

===========================  =================================================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
Service Homepage             `PaloAltoCortexXDR_isolate <https://www.paloaltonetworks.com/cortex/cortex-xdr>`_
===========================  =================================================================================

.. rubric:: Description

Isolate endpoints identified by hostname or IP list

.. rubric:: Configuration

================================  ================================================================================================================================================================================================================================================
Name                              Description
api_key                           API key
api_key_id                        API key ID
advanced_security                 Set True if the API key was generated with Advanced security level. False for a Standard security key.
api_host                          Fully qualified domain name for the API host. Example: api-example.xdr.us.paloaltonetworks.com
isolate_polling_interval          Interval, in seconds between requests for isolate or unisolate actions.
isolate_max_polling_retries       Maximum number of time to retry action status when the isolate or unisolate action is still in progress.
allow_multiple_isolation_targets  Allow the responder to send multiple targets for isolation/unisolation in one multi-line observable. Set to false as a safety mechanism to allow only a single endpoint to be affected while refusing requests to operate on multiple endpoints.
================================  ================================================================================================================================================================================================================================================


PaloAltoCortexXDR_scan
----------------------

.. rubric:: Details

===========================  ==============================================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
Service Homepage             `PaloAltoCortexXDR_scan <https://www.paloaltonetworks.com/cortex/cortex-xdr>`_
===========================  ==============================================================================

.. rubric:: Description

Scan endpoints identified by hostname or IP list

.. rubric:: Configuration

========================  ======================================================================================================
Name                      Description
api_key                   API key
api_key_id                API key ID
advanced_security         Set True if the API key was generated with Advanced security level. False for a Standard security key.
api_host                  Fully qualified domain name for the API host. Example: api-example.xdr.us.paloaltonetworks.com
scan_polling_interval     Interval, in seconds between requests for scan actions.
scan_max_polling_retries  Maximum number of time to retry action status when a scan action is still in progress.
========================  ======================================================================================================


PaloAltoCortexXDR_unisolate
---------------------------

.. rubric:: Details

===========================  ===================================================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
Service Homepage             `PaloAltoCortexXDR_unisolate <https://www.paloaltonetworks.com/cortex/cortex-xdr>`_
===========================  ===================================================================================

.. rubric:: Description

Unisolate endpoints identified by hostname or IP list

.. rubric:: Configuration

================================  ================================================================================================================================================================================================================================================
Name                              Description
api_key                           API key
api_key_id                        API key ID
advanced_security                 Set True if the API key was generated with Advanced security level. False for a Standard security key.
api_host                          Fully qualified domain name for the API host. Example: api-example.xdr.us.paloaltonetworks.com
isolate_polling_interval          Interval, in seconds between requests for isolate or unisolate actions.
isolate_max_polling_retries       Maximum number of time to retry action status when the isolate or unisolate action is still in progress.
allow_multiple_isolation_targets  Allow the responder to send multiple targets for isolation/unisolation in one multi-line observable. Set to false as a safety mechanism to allow only a single endpoint to be affected while refusing requests to operate on multiple endpoints.
================================  ================================================================================================================================================================================================================================================


.. rubric:: Additional details from the README file:


Palo Alto Cortex XDR: Extended Detection and Response

Cortex XDR is the industry’s first extended detection and response platform that integrates network, endpoint, cloud, and third-party data to stop sophisticated attacks. Cortex XDR has been designed from the ground up to help organizations secure their digital assets and users while simplifying operations. Using behavioral analytics, it identifies unknown and highly evasive threats targeting your network. Machine learning and AI models uncover threats from any source, including managed and unmanaged devices.

This responder interacts with the Cortex XDR API to support three actions:


* Isolate an endpoint from the network. Prevents a suspected compromised system from causing any further harm to the network.
* Unisolate an endpoint that was previously isolated.
* Scan: initial a full scan of an endpoint.

The responder operates on a 'fqdn' or 'ip' case artifact (observable) from TheHive. The value of the FQDN should be the endpoint name as it appears in the Cortex XDR console.

The responder accepts multiple inputs at once if your observable is multi-line value with one entry per line.

