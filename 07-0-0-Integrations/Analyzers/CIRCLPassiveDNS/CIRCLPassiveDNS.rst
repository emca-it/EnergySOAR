CIRCLPassiveDNS
===============

.. image:: ./assets/passivedns.png
   :alt: logo

CIRCLPassiveDNS
---------------

.. rubric:: Details

===========================  ===============================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/cortex-analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  Yes
DataType Supported           domain, url, ip
Service Homepage             `CIRCLPassiveDNS <https://www.circl.lu/services/passive-dns/>`_
===========================  ===============================================================

.. rubric:: Description

Check CIRCL's Passive DNS for a given domain or URL.

.. rubric:: Configuration

========  ===========
Name      Description
user      Username
password  Password
========  ===========


.. rubric:: Additional details from the README file:


CIRCLPassiveDNS
^^^^^^^^^^^^^^^

Check `CIRCL's Passive DNS <https://www.circl.lu/services/passive-dns/>`_ for a
 given domain.

This analyzer comes in only one flavor.

Requirements
~~~~~~~~~~~~

Access to CIRCL Passive DNS is only allowed to trusted partners in Luxembourg
and abroad. `Contact CIRCL <https://www.circl.lu/contact/>`_ if you would like
access. Include your affiliation and the foreseen use of the Passive DNS
data.

If the CIRCL positively answers your access request, you'll obtain a username
 and password which are needed to make the analyzer work.

supply your username as the value for the ``user`` parameter and your password
as the value for the ``password`` parameter.

