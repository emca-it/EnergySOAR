ForcepointWebsensePing
======================

ForcepointWebsensePing
----------------------

.. rubric:: Details

===========================  ======================================================
Author                       Andrea Garavaglia, Davide Arcuri - LDO-CERT
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           url, ip, domain, fqdn
Service Homepage             `ForcepointWebsensePing <https://www.forcepoint.com>`_
===========================  ======================================================

.. rubric:: Description

Use ForcepointWebsensePing to determine which category a certain URL is assigned to.

.. rubric:: Configuration

=====================  ==============================================================
Name                   Description
hostname               Forcepoint remote Filtering Service
timeout                WebsensePing timeout-secs
path                   WebsensePing path
malicious_categories   List of Forcepoint categories to be considered as malicious
suspicious_categories  List of Forcepoint categories you would consider as suspicious
safe_categories        List of Forcepoint categories you would consider as safe
=====================  ==============================================================


.. rubric:: Additional details from the README file:


 Categorize domain names, URL, fqdn, IP addresses using the popular  `Forcepoint Master Database <https://www.forcepoint.com/it/product/feature/master-database-url-categories>`_ service .

Requirements
~~~~~~~~~~~~

 You need a `valid Forcepoint license <https://support.forcepoint.com/KBArticle?id=000016428#WebsensePing/>`_ to use the analyzer:


* Install WebsensePing on instance where you will run this analyzer
* Provide hostname of remote Filtering Service as a value for the ``hostname`` parameter and timeout as a value for the ``timeout`` parameter.

