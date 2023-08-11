MISP
====

.. image:: ./assets/misp.png
   :alt: logo

MISP
----

.. rubric:: Details

===========================  ========================================================================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      2.1
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/cortex-analyzers
Requires Registration        No
Requires Subscription        No
Free Subscription Available  Yes
DataType Supported           domain, ip, url, fqdn, uri_path, user-agent, hash, mail, mail_subject, registry, regexp, other, filename
Service Homepage             `MISP <https://www.misp-project.org/>`_
===========================  ========================================================================================================

.. rubric:: Description

Query multiple MISP instances for events containing an observable.

.. rubric:: Configuration

==========  =============================================================
Name        Description
name        Name of MISP servers
url         URL of MISP servers
key         API key for each server
cert_check  Verify server certificate
cert_path   Path to the CA on the system used to check server certificate
==========  =============================================================


.. rubric:: Additional details from the README file:


MISP
^^^^

`MISP <https://www.misp-project.org/>`_ A threat intelligence platform for gathering, sharing, storing and correlating Indicators of Compromise of targeted attacks, threat intelligence, financial fraud information, vulnerability information or even counter-terrorism information.

The analyzer comes in a single flavour that will return MISP additional information  for provided observable.

Requirements
~~~~~~~~~~~~

You need a valid MISP API integration to use the analyzer.


* Provide your API key as values for the ``key`` parameter.

