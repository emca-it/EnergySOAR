Cylance
=======

.. image:: ./assets/cylance_logo.png
   :alt: logo

Cylance
-------

.. rubric:: Details

===========================  ========================================
Author                       Mikael Keri
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           hash
Service Homepage             `Cylance <https://www.blackberry.com/>`_
===========================  ========================================

.. rubric:: Description

Search for a specific hash, if there is a match, coresponding client information

.. rubric:: Configuration

==========  ==========================================================
Name        Description
ten_id      Tenant ID
app_id      App ID
app_secret  App Secret
region      Portal region, : NA, US, APN, JP, APS, AU, EU, GOV, SA, SP
==========  ==========================================================


.. rubric:: Additional details from the README file:


Cylance hashlookup
==================

Cylance hash lookup enables you to query possible infected clients of yours using a SHA256 hash. 
The response includes information about the matching sample(s) along with information about affected clients.

FAQ
===

Q: Why only SHA256
^^^^^^^^^^^^^^^^^^

Sadly, although the response data contains an MD5 hash, the API only allows you to query with a SHA256

