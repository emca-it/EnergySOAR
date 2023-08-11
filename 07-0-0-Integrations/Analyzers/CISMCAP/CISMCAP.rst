CISMCAP
=======

.. image:: ./assets/cis_mcap_logo.png
   :alt: logo

CISMCAP
-------

.. rubric:: Details

===========================  ========================================================
Author                       Joe Lazaro
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  No
DataType Supported           ip, hash, url, domain, fqdn, file
Service Homepage             `CISMCAP <https://www.cisecurity.org/ms-isac/services>`_
===========================  ========================================================

.. rubric:: Description

Malicious Code Analysis Platform (MCAP) by the Center for Internet Security (CIS). Submit files for analysis or check feeds for known indicators of compromise for other data types.

.. rubric:: Configuration

======================  =====================================================================
Name                    Description
key                     API key
private_samples         Submitted samples will not be shared with other members of the portal
minimum_confidence      Restrict to IOCs with this confidence score or higher.
minimum_severity        Restrict to IOCs with this severity score or higher.
polling_interval        Interval (seconds) between requests for sample status.
max_sample_result_wait  Maximum time to retry requests for sample status.
======================  =====================================================================


.. rubric:: Additional details from the README file:


The Center for Internet Security, Inc. (CIS®) makes the connected world a safer place for people, businesses, and governments through our core competencies of collaboration and innovation. CIS is home to the Multi-State Information Sharing and Analysis Center® (MS-ISAC®), the trusted resource for cyber threat prevention, protection, response, and recovery for U.S. State, Local, Tribal, and Territorial government entities, and the Elections Infrastructure Information Sharing and Analysis Center® (EI-ISAC®), which supports the rapidly changing cybersecurity needs of U.S. elections offices.

Malicious Code Analysis Platform (MCAP) is a no-cost web-based sandbox which enables MS-ISAC and EI-ISAC members to submit suspicious files such as executables, DLLs, documents, quarantine files, and archives for analysis in a controlled and non-public fashion. The platform also enables users to perform threat analysis based on domain, IP address, URL, hashes, and various Indicators of Compromise (IOCs).

This analyzer allows you to submit a variety of observables to MCAP to analyze files or check feeds for known indicators of compromise for other data types.

To read more, visit https://www.cisecurity.org/ms-isac

