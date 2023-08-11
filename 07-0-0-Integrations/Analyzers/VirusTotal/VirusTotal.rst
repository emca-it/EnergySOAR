VirusTotal
==========

.. image:: ./assets/virustotal-logo.png
   :alt: logo

VirusTotal_DownloadSample
-------------------------

.. rubric:: Details

===========================  ==========================================================
Author                       LDO-CERT
Version                      3.1
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           hash
Service Homepage             `VirusTotal_DownloadSample <https://www.virustotal.com/>`_
===========================  ==========================================================

.. rubric:: Description

Use VirusTotal to download the original file for an hash.

.. rubric:: Configuration

====  ==============================
Name  Description
key   API private key for Virustotal
====  ==============================


VirusTotal_GetReport
--------------------

.. rubric:: Details

===========================  =====================================================
Author                       CERT-BDF, StrangeBee
Version                      3.1
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  No
DataType Supported           file, hash, domain, fqdn, ip, url
Service Homepage             `VirusTotal_GetReport <https://www.virustotal.com/>`_
===========================  =====================================================

.. rubric:: Description

Get the latest VirusTotal report for a file, hash, domain or an IP address.

.. rubric:: Configuration

==============================  =====================================================================================
Name                            Description
key                             API key for Virustotal
polling_interval                Define time interval between two requests attempts for the report
rescan_hash_older_than_days     Rescan hash observable if report is older than selected days
highlighted_antivirus           Add taxonomy if selected AV don't recognize observable
download_sample                 Download automatically sample as observable when looking for hash
download_sample_if_highlighted  Download automatically sample as observable if highlighted antivirus didn't recognize
==============================  =====================================================================================


VirusTotal_Rescan
-----------------

.. rubric:: Details

===========================  ==================================================
Author                       CERT-LDO
Version                      3.1
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           hash
Service Homepage             `VirusTotal_Rescan <https://www.virustotal.com/>`_
===========================  ==================================================

.. rubric:: Description

Use VirusTotal to run new analysis on hash.

.. rubric:: Configuration

==============================  =====================================================================================
Name                            Description
key                             API key for Virustotal
polling_interval                Define time interval between two requests attempts for the report
highlighted_antivirus           Add taxonomy if selected AV don't recognize observable
download_sample                 Download automatically sample as observable when looking for hash
download_sample_if_highlighted  Download automatically sample as observable if highlighted antivirus didn't recognize
==============================  =====================================================================================


VirusTotal_Scan
---------------

.. rubric:: Details

===========================  ================================================
Author                       CERT-BDF, StrangeBee
Version                      3.1
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  No
DataType Supported           file, url
Service Homepage             `VirusTotal_Scan <https://www.virustotal.com/>`_
===========================  ================================================

.. rubric:: Description

Use VirusTotal to scan a file or URL.

.. rubric:: Configuration

=====================  =================================================================
Name                   Description
key                    API key for Virustotal
polling_interval       Define time interval between two requests attempts for the report
highlighted_antivirus  Add taxonomy if selected AV don't recognize observable
=====================  =================================================================


.. rubric:: Additional details from the README file:


This analyzer let you run Virustotal services on several datatypes: 


* *file*
* *hash*
* *domain*
* *fqdn*
* *ip*
* *url*

The program uses `VirusTotal API v3 <https://developers.virustotal.com/v3.0/reference>`_.

Major improvements have been added with _VirusTotal_GetReport_ flavor. Now, with the classical scan results, the report can display: 


* A Summary: with qualitative informnation about the detection


.. image:: assets/virustotal-summary-report.png
   :target: assets/virustotal-summary-report.png
   :alt: 



* Crowdsourced YARA results with known Yara rules to detect the threat


.. image:: assets/virustotal-yara.png
   :target: assets/virustotal-yara.png
   :alt: 



* Contacted IP addresses, domains and URLs if any
* Crowdsourced IDS results with known IDS rules to detect the threat
* Sandbox verdict if any


.. image:: assets/virustotal-ids-sandbox-urls.png
   :target: assets/virustotal-ids-sandbox-urls.png
   :alt: 


Extracted Observables
~~~~~~~~~~~~~~~~~~~~~

Moreover, these domains, IP addresses, URLs as well as detection YARA and IDS rules reported are added to the extracted Observables, ready
to be imported and actioned in TheHive.


.. image:: assets/virustotal-extracted-observables.png
   :target: assets/virustotal-extracted-observables.png
   :alt: 


