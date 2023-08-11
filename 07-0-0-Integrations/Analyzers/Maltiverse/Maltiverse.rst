Maltiverse
==========

.. image:: ./assets/maltiverse.png
   :alt: logo

Maltiverse_Report
-----------------

.. rubric:: Details

===========================  ====================================================
Author                       ottimo
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           hash, domain, ip, url
Service Homepage             `Maltiverse_Report <https://maltiverse.com/search>`_
===========================  ====================================================

.. rubric:: Description

Get the latest Maltiverse report for an hash, domain or an IP address.

.. rubric:: Configuration

================  =================================================================
Name              Description
polling_interval  Define time interval between two requests attempts for the report
api_key           Auth token to use when requesting data to Maltiverse
================  =================================================================


.. rubric:: Additional details from the README file:


Maltiverse
^^^^^^^^^^

This analyzer lets you query the free `Maltiverse <https://maltiverse.com/search>`_ Threat Intelligence platform for enrichment information about a particular hash, domain, ip or url.

The analyzer comes in a single flavour that will return Maltiverse additional information categorization for provided ip.

Requirements
~~~~~~~~~~~~

You can specify time interval between two requests attempts for the report with the ``polling_interval`` parameter.

