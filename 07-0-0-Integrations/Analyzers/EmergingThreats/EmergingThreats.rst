EmergingThreats
===============

.. image:: ./assets/proofpoint.png
   :alt: logo

EmergingThreats_DomainInfo
--------------------------

.. rubric:: Details

===========================  ===================================================================
Author                       Davide Arcuri and Andrea Garavaglia, LDO-CERT
Version                      1.0
License                      AGPL-V3
Website                      https://github.com/dadokkio/Cortex-Analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain, fqdn
Service Homepage             `EmergingThreats_DomainInfo <https://threatintel.proofpoint.com/>`_
===========================  ===================================================================

.. rubric:: Description

Retrieve ET reputation, related malware, and IDS requests for a given domain.

.. rubric:: Configuration

====  ===========
Name  Description
key   API key
====  ===========


EmergingThreats_IPInfo
----------------------

.. rubric:: Details

===========================  ===============================================================
Author                       Davide Arcuri and Andrea Garavaglia, LDO-CERT
Version                      1.0
License                      AGPL-V3
Website                      https://github.com/dadokkio/Cortex-Analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           ip
Service Homepage             `EmergingThreats_IPInfo <https://threatintel.proofpoint.com/>`_
===========================  ===============================================================

.. rubric:: Description

Retrieve ET reputation, related malware, and IDS requests for a given IP address.

.. rubric:: Configuration

====  ===========
Name  Description
key   API key
====  ===========


EmergingThreats_MalwareInfo
---------------------------

.. rubric:: Details

===========================  ====================================================================
Author                       Davide Arcuri and Andrea Garavaglia, LDO-CERT
Version                      1.0
License                      AGPL-V3
Website                      https://github.com/dadokkio/Cortex-Analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file, hash
Service Homepage             `EmergingThreats_MalwareInfo <https://threatintel.proofpoint.com/>`_
===========================  ====================================================================

.. rubric:: Description

Retrieve ET details and info related to a malware hash.

.. rubric:: Configuration

====  ===========
Name  Description
key   API key
====  ===========


.. rubric:: Additional details from the README file:


EmergingThreats
^^^^^^^^^^^^^^^

`EmergingThreats <https://www.proofpoint.com/us/products/advanced-threat-protection/et-intelligence>`_ intelligence helps prevent attacks and reduce risk by helping you understand the historical context of where these threats originated, who is behind them, when have they attacked, what methods they used, and what they're after.

The analyzer is available in 3 flavors:


* EmergingThreats_DomainInfo: retrieve ET reputation, related malware, and IDS requests for a given domain.
* EmergingThreats_IPInfo: retrieve ET reputation, related malware, and IDS requests for a given IP address.
* EmergingThreats_MalwareInfo: retrieve ET details and info related to a malware hash.

Requirements
~~~~~~~~~~~~

You need a valid EmergingThreats API subscription to use the analyzer:


* Provide your API key as a value for the ``key`` parameter.

