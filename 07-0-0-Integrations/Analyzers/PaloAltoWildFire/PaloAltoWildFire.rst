PaloAltoWildFire
================

.. image:: ./assets/palo_alto_logo.png
   :alt: logo

PaloAltoWildFire
----------------

.. rubric:: Details

===========================  ================================================================================
Author                       Ignacio Rodriguez Paez, Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file, url, hash
Service Homepage             `PaloAltoWildFire <https://www.paloaltonetworks.com/network-security/wildfire>`_
===========================  ================================================================================

.. rubric:: Description

Run Palo Alto WildFire analysis on a file, hash, or URL

.. rubric:: Configuration

================  =================================================================================================================================================================================================================================
Name              Description
api_host          You can send requests to the WildFire global cloud (U.S., default option) or to the WildFire regional clouds that Palo Alto Networks owns and maintains. See the WildFire Public Cloud documentation for a list of valid servers.
key               API key for WildFire
polling_interval  Define time interval between two requests attempts for the report
================  =================================================================================================================================================================================================================================


.. rubric:: Additional details from the README file:


WildFire® is the industry's largest, most integrated cloud malware protection engine that utilizes patented machine learning models for real-time detection of previously unseen, targeted malware and advanced persistent threats, keeping your organization protected.

When you submit observables to WildFire, they are analyzed in a sandboxed environment using multiple techniques:


* Dynamic analysis observes the files as they execute
* Machine learning extracts unique feathres form each file
* Static analysis provides instant identification of malware variants
* Uses a custom hypervisor to prevent malware evasion techniques

This analyzer supports "file", "url", and "hash" observables to be submitted to WildFire and produces a nicely formatted report in TheHive with all the pertinent information.

Product website: https://www.paloaltonetworks.com/network-security/wildfire

