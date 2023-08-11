FireHOLBlocklists
=================

.. image:: ./assets/firehol.png
   :alt: logo

FireHOLBlocklists
-----------------

.. rubric:: Details

===========================  ===================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/cortex-analyzers
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           ip
Service Homepage             `FireHOLBlocklists <https://iplists.firehol.org/>`_
===========================  ===================================================

.. rubric:: Description

Check IP addresses against the FireHOL blocklists

.. rubric:: Configuration

=============  ==================
Name           Description
blocklistpath  Path to blocklists
=============  ==================


.. rubric:: Additional details from the README file:


FireJOLBlocklists
^^^^^^^^^^^^^^^^^

`FireJOLBlocklists <http://iplists.firehol.org/>`_ is a composition of other IP lists.
The objective is to create a blacklist that can be safe enough to be used on all systems, with a firewall, to block access entirely, from and to its listed IPs.

The analyzer comes in a single flavout that will return if provided ip is in block list and link to its report.

Requirements
~~~~~~~~~~~~

You need to clone original repo on the cortex machine [git clone https://github.com/firehol/blocklist-ipsets] and update relative path in ``blocklistpath`` variable.

