FireEyeiSight
=============

.. image:: ./assets/fireeyeisight.png
   :alt: FireEyeiSight logo

FireEyeiSight
-------------

.. rubric:: Details

===========================  ====================================================
Author                       Davide Arcuri and Andrea Garavaglia, LDO-CERT
Version                      1.0
License                      AGPL-V3
Website                      https://github.com/LDO-CERT/Cortex-Analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           domain, ip, hash, url
Service Homepage             `FireEyeiSight <https://intelligence.fireeye.com/>`_
===========================  ====================================================

.. rubric:: Description

Query domains, IPs, hashes and URLs on FireEye's iSIGHT threat intelligence service.

.. rubric:: Configuration

====  ===================================
Name  Description
key   API key for FireEye iSIGHT.
pwd   Password associated to the API key.
====  ===================================


.. rubric:: Additional details from the README file:


FireEyeiSight
^^^^^^^^^^^^^

`FireEyeiSight <https://intelligence.fireeye.com/>`_ adds context and priority to global threats before, during and after an attack. Data is gleaned from the adversarial underground, virtual network detection sensors and Mandiant IR investigations from the world’s largest breaches.

The analyzer comes in only one flavor.

Requirements
~~~~~~~~~~~~

You need a valid FireEye iSight subscription to use the analyzer.


* Provide your API key as a value for the ``key`` parameter.
* Provide your associated password as a value for ``pwd`` parameter.

