VirustotalDownloader
====================

Virustotal_Downloader
---------------------

.. rubric:: Details

===========================  =================================================
Author                       Mario Henkel @hariomenkel
Version                      0.1
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
Service Homepage             `Virustotal_Downloader <https://virustotal.com>`_
===========================  =================================================

.. rubric:: Description

Download a file from Virustotal by its hash

.. rubric:: Configuration

=================  ===============================================================================
Name               Description
virustotal_apikey  Virustotal API key which should be used to download files
energysoar_url        URL pointing to your Energy SOAR Base installation, e.g. 'http://127.0.0.1:9000'
energysoar_apikey     Energy SOAR Base API key which is used to add the downloaded file back to the alert/case
=================  ===============================================================================


.. rubric:: Additional details from the README file:


VirusTotalDownloader
^^^^^^^^^^^^^^^^^^^^

This responder comes in only 1 flavor that lets you download a sample of malware from VirusTotal by submitting a hash.

Requirements
~~~~~~~~~~~~

This responder need a valid Premium API key from VirusTotal as the ``virustotal_apikey`` parameter in the configuration. 
To add the sample in Observables in Energy SOAR Base, the responder also requires the URL of Energy SOAR Base as the ``thehive_url`` paramenter and a valid API key as the ``thehive_apikey`` parameter.

