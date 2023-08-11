Fortiguard
==========

.. image:: ./assets/fortiguard.png
   :alt: logo

Fortiguard_URLCategory
----------------------

.. rubric:: Details

===========================  ================================================================
Author                       Eric Capuano
Version                      2.1
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           domain, url, fqdn
Service Homepage             `Fortiguard_URLCategory <https://www.fortiguard.com/webfilter>`_
===========================  ================================================================

.. rubric:: Description

Check the Fortiguard category of a URL, FQDN or a domain. Check the full available list at https://fortiguard.com/webfilter/categories

.. rubric:: Configuration

=====================  ============================================================
Name                   Description
malicious_categories   List of FortiGuard categories to be considered as malicious
suspicious_categories  List of FortiGuard categories to be considered as suspicious
=====================  ============================================================


.. rubric:: Additional details from the README file:


Fortiguard
^^^^^^^^^^

`Fortiguard <https://www.fortiguard.com/learnmore#wf>`_ is a web filtering service commonly used in organizations.

The analyzer comes in a single flavout that will return websense categorization for provided url or domain.

Requirements
~~~~~~~~~~~~

The analyzer returns just their categorization, you can customize which category must be considerd suspiciour or malicious adding them to ``suspicious_categories`` or ``malicious_categories`` variables.

