Thunderstorm
============

.. image:: ./assets/thor_thunderstorm_logo.png
   :alt: logo

THOR_Thunderstorm_ScanSample
----------------------------

.. rubric:: Details

===========================  ====================================================================================
Author                       Florian Roth
Version                      0.3.1
License                      AGPL-V3
Website                      https://github.com/NextronSystems/Cortex-Analyzers
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file
Service Homepage             `THOR_Thunderstorm_ScanSample <https://www.nextron-systems.com/thor-thunderstorm/>`_
===========================  ====================================================================================

.. rubric:: Description

Submits sample to an on-premise THOR Thunderstorm web service and processes the scan result

.. rubric:: Configuration

=======================  ================================================
Name                     Description
thunderstorm_server      Thunderstorm Server
thunderstorm_port        Thunderstorm Port
thunderstorm_source      Source System
thunderstorm_ssl         Use an SSL encrypted HTTP connection
thunderstorm_ssl_verify  Verify the SSL certificate of the remote service
=======================  ================================================


.. rubric:: Additional details from the README file:


Thunderstorm
^^^^^^^^^^^^

The Thunderstorm analyzer submits a file sample to a local or public THOR Thunderstorm service and processes the scan result

Requirements
~~~~~~~~~~~~


* `ThunderstormAPI <https://github.com/NextronSystems/thunderstormAPI>`_

Scope
~~~~~

`THOR Thunderstorm <https://www.nextron-systems.com/thor-thunderstorm/>`_ is a web service version of the well-known scanner THOR. THOR focuses on APTs, hacking activity, traces of hacking activity and file anomalies like obfuscation techniques, suspicious PE packers or PE header anomalies.

Matches
~~~~~~~

The reports contain useful meta data and a list of matching rules. Each rule links to a related public report or states that the rules was based on internal research.

The reports include a total score and sub scores defined in the matching YARA rules. 

The score and level indicate the criticality of the finding.

Access to Thunderstorm
~~~~~~~~~~~~~~~~~~~~~~

THOR Thunderstorm is a high-speed, multi-threaded, caching scan service that is licensed and installed on-premise on the Linux system of your choice. Nextron systems offers access to test systems with the FQDN thunderstorm.nextron-systems.com `on request <https://www.nextron-systems.com/get-started/>`_.

