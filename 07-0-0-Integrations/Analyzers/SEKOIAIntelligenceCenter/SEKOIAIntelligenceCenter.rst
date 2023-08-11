SEKOIAIntelligenceCenter
========================

.. image:: ./assets/sekoia_logo.png
   :alt: logo

SEKOIAIntelligenceCenter_Context
--------------------------------

.. rubric:: Details

===========================  ========================================================
Author                       SEKOIA
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain, fqdn, url, hash, ip
Service Homepage             `SEKOIAIntelligenceCenter_Context <https://sekoia.io/>`_
===========================  ========================================================

.. rubric:: Description

Query the Intelligence Center to retrieve the context of an observable

.. rubric:: Configuration

=======  ===========================
Name     Description
api_key  Intelligence center API key
url      Intelligence center URL
=======  ===========================


SEKOIAIntelligenceCenter_Indicators
-----------------------------------

.. rubric:: Details

===========================  ===========================================================
Author                       SEKOIA
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain, fqdn, url, hash, ip
Service Homepage             `SEKOIAIntelligenceCenter_Indicators <https://sekoia.io/>`_
===========================  ===========================================================

.. rubric:: Description

Query the Intelligence Center to retrieve indicators

.. rubric:: Configuration

=======  ===========================
Name     Description
api_key  Intelligence center API key
url      Intelligence center URL
=======  ===========================


SEKOIAIntelligenceCenter_Observables
------------------------------------

.. rubric:: Details

===========================  ============================================================
Author                       SEKOIA
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain, fqdn, url, hash, ip
Service Homepage             `SEKOIAIntelligenceCenter_Observables <https://sekoia.io/>`_
===========================  ============================================================

.. rubric:: Description

Query the Intelligence Center to retrieve known observables

.. rubric:: Configuration

=======  ===========================
Name     Description
api_key  Intelligence center API key
url      Intelligence center URL
=======  ===========================


.. rubric:: Additional details from the README file:


 Get more context around domain names, IP adresses, urls and file hashes using the
 `SEKOIA.IO <https://sekoia.io>`_ Intelligence Database.

 The analyzer comes in 3 flavors:


* SEKOIAIntelligenceCenter\ ***Indicators**\ : Find indicators matching the observable provided.
* SEKOIAIntelligenceCenter\ ***Context**\ : Get indicators and their context for the observable provided.
* SEKOIAIntelligenceCenter\ ***Observables**\ : Query the Intelligence Center to retrieve known observables.

Requirements
~~~~~~~~~~~~

 You need an active `SEKOIA.IO Intelligence Center <https://sekoia.io/>`_ subscription to use the analyzer:


* Provide your API key as a value for the ``api_key`` parameter.

To get any help don't hesitate to contact support@sekoia.io.

