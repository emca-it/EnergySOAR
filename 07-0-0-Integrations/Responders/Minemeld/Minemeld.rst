Minemeld
========

.. image:: ./assets/MM-logo.png
   :alt: logo

Minemeld
--------

.. rubric:: Details

===========================  ==========================================================
Author                       Wes Lambert, Security Onion Solutions
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
Service Homepage             `Minemeld <https://github.com/PaloAltoNetworks/minemeld>`_
===========================  ==========================================================

.. rubric:: Description

Submit indicator to Minemeld

.. rubric:: Configuration

=======================  ========================================================
Name                     Description
minemeld_url             URL for Minemeld instance
minemeld_user            User for Minemeld
minemeld_password        Password for Minemeld
minemeld_indicator_list  Name of indicator list to which indicators will be added
minemeld_share_level     Share level for indicator
minemeld_confidence      Confidence level for indicator
minemeld_ttl             TTL for indicator
=======================  ========================================================


.. rubric:: Additional details from the README file:


Palo Alto Minemeld
^^^^^^^^^^^^^^^^^^

This responder sends observables you select to a `Palo Alto Minemeld <https://www.paloaltonetworks.com/products/secure-the-network/subscriptions/minemeld>`_ instance.

Requirements
~~~~~~~~~~~~

The following options are required in the Palo Alto Minemeld Responder configuration:


* ``minemeld_url`` : URL of the Minemeld instance to which you will be posting indicators   
* ``minemeld_user``\ : user accessing the Minemeld instance
* ``minemeld_password``\ :  password for the user accessing the Minemeld instance
* ``minemeld_indicator_list``\ : name of Minemeld indicator list (already created in Minemeld)
* ``minemeld_share_level``\ : share level for indicators (defaults to ``red``\ )
* ``minemeld_confidence``\ : confidence level for indicators (defaults to ``100``\ )
* ``minemeld_ttl``\ : TTL for indicators (defaults to ``86400`` seconds)

