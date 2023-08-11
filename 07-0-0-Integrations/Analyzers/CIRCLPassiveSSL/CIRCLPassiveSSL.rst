CIRCLPassiveSSL
===============

.. image:: ./assets/pssl.png
   :alt: PSSL logo

CIRCLPassiveSSL
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
DataType Supported           ip, certificate_hash, hash
Service Homepage             `CIRCLPassiveSSL <https://www.circl.lu/services/passive-ssl/>`_
===========================  ===============================================================

.. rubric:: Description

Check CIRCL's Passive SSL for a given IP address or a X509 certificate hash.

.. rubric:: Configuration

========  ===========
Name      Description
user      Username
password  Password
========  ===========


.. rubric:: Additional details from the README file:


CIRCLPassiveSSL
^^^^^^^^^^^^^^^

Check `CIRCL's Passive SSL <https://www.circl.lu/services/passive-ssl/>`_
service for a given IP address or certificate hash.

This analyzer comes in only one flavor.

Requirements
~~~~~~~~~~~~

Access to CIRCL Passive SSL is allowed to partners including security
researchers or incident analysts worldwide. `Contact CIRCL <https://www.circl.lu/contact/>`_
if you would like access.

If the CIRCL positively answers your access request, you'll obtain a username
 and password which are needed to make the analyzer work.

Supply your username as the value for the ``user`` parameter and your password
as the value for the ``password`` parameter.

