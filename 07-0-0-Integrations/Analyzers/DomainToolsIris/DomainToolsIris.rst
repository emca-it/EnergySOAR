DomainToolsIris
===============

.. image:: ./assets/domaintools_logo.png
   :alt: logo

DomainToolsIris_Investigate
---------------------------

.. rubric:: Details

===========================  ============================================================
Author                       DomainTools
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain
Service Homepage             `DomainToolsIris_Investigate <https://www.domaintools.com>`_
===========================  ============================================================

.. rubric:: Description

Use DomainTools Iris API to investigate a domain.

.. rubric:: Configuration

=====================  ================================
Name                   Description
username               DomainTools Iris API credentials
key                    DomainTools Iris API credentials
pivot_count_threshold  Pivot count threshold.
=====================  ================================


DomainToolsIris_Pivot
---------------------

.. rubric:: Details

===========================  ======================================================
Author                       DomainTools
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           hash, ip, mail
Service Homepage             `DomainToolsIris_Pivot <https://www.domaintools.com>`_
===========================  ======================================================

.. rubric:: Description

Use DomainTools Iris API to pivot on ssl_hash, ip, or email.

.. rubric:: Configuration

========  ================================
Name      Description
username  DomainTools Iris API credentials
key       DomainTools Iris API credentials
========  ================================


.. rubric:: Additional details from the README file:


 Look up domain names, IP addresses, e-mail addresses, and SSL hashes using the popular
 `DomainTools Iris <https://www.domaintools.com/resources/api-documentation/iris-investigate/>`_ service API.

 The analyzer comes in 2 flavors:


* DomainToolsIris\ ***Investigate**\ : Use DomainTools Iris API to investigate a domain.
* DomainToolsIris\ ***Pivot**\ : Use DomainTools Iris API to pivot on ssl_hash, ip, or email.

Requirements
~~~~~~~~~~~~

 You need a `valid DomainTools API integration subscription <https://www.domaintools.com/products/api-integration/>`_ to use the analyzer:


* Provide your username as a value for the ``username`` parameter and API key as
  a value for the ``key`` parameter.
* Set the ``pivot_count_threshold`` parameter to highlight any item below that value as being of interest in the
  report's template.

