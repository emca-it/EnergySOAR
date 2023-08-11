Censys
======

.. image:: ./assets/censys.png
   :alt: Censys logo

Censys
------

.. rubric:: Details

===========================  ================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      1.0
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/censys-analyzer
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  Yes
DataType Supported           ip, hash, domain, other
Service Homepage             `Censys <https://censys.io/>`_
===========================  ================================================

.. rubric:: Description

Check IPs, certificate hashes or domains against censys.io.

.. rubric:: Configuration

====  ==============
Name  Description
uid   UID for Censys
key   API key
====  ==============


.. rubric:: Additional details from the README file:


Censys
^^^^^^

`Censys <https://censys.io/>`_ is a platform that helps information security practitioners discover, monitor, and analyze devices that are accessible from the Internet. Regularly probes every public IP address and popular domain names, curate and enrich the resulting data, and make it intelligible through an interactive search engine and API.

Requirements
~~~~~~~~~~~~

You need a valid Censys API integration subscription to use the analyzer.


* Provide your API uid as values for the ``uid`` parameter.
* Provide your API key as values for the ``key`` parameter.

