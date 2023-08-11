NERD
====

.. image:: ./assets/NERD_logo.png
   :alt: logo

NERD
----

.. rubric:: Details

===========================  =================================
Author                       Vaclav Bartos, CESNET
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  Yes
DataType Supported           ip
Service Homepage             `NERD <https://nerd.cesnet.cz/>`_
===========================  =================================

.. rubric:: Description

Get Reputation score and other basic information from Network Entity Reputation Database (NERD)

.. rubric:: Configuration

====  =============================
Name  Description
key   API key
url   Base URL of the NERD instance
====  =============================


.. rubric:: Additional details from the README file:


Nerd
^^^^

Project `Nerd <https://nerd.cesnet.cz/>`_ aims to build an extensive reputation database of known sources of cyber threats. That is, a list of known malicious IP addresses or other network entities (e.g. ASNs or domain names) together with all security-relevant information about each of them.

The analyzer comes in a single flavour that will return additional information categorization for provided ip.

Requirements
~~~~~~~~~~~~

You need a valid Nerd API integration subscription to use the analyzer.


* Provide your API key as values for the ``key`` parameter.
* Default url of NERD instance is provided for ``url`` parameter but you could override it.

