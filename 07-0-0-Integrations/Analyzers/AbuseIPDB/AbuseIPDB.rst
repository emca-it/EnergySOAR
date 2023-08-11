AbuseIPDB
=========

.. image:: ./assets/abuseipdb.png
   :alt: abuseipdb logo

AbuseIPDB
---------

.. rubric:: Details

===========================  =========================================
Author                       Matteo Lodi
Version                      1.0
License                      AGPL-v3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  Yes
DataType Supported           ip
Service Homepage             `AbuseIPDB <https://www.abuseipdb.com/>`_
===========================  =========================================

.. rubric:: Description

Determine whether an IP was reported or not as malicious by AbuseIPDB

.. rubric:: Configuration

====  =======================================
Name  Description
key   API key for AbuseIPDB
days  Check for IP Reports in the last X days
====  =======================================


.. rubric:: Additional details from the README file:


AbuseIPDB
^^^^^^^^^

`AbuseIPDB <https://www.abuseipdb.com/>`_ is a project dedicated to helping combat the spread of hackers, spammers, and abusive activity on the internet.

The analyzer comes in only one flavor.

Requirements
~~~~~~~~~~~~

You need a valid AbuseIPDB API integration subscription to use the analyzer:


* Provide your API key as a value for the ``key`` parameter.
* Set the ``days`` parameter to limit temporal range in search

