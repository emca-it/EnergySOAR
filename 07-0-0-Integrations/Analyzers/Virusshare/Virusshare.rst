Virusshare
==========

.. image:: ./assets/virusshare.png
   :alt: logo

Virusshare
----------

.. rubric:: Details

===========================  =================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/cortex-analyzers
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           hash, file
Service Homepage             `Virusshare <https://virusshare.com/>`_
===========================  =================================================

.. rubric:: Description

Search for MD5 hashes in Virusshare.com hash list

.. rubric:: Configuration

====  ==================================
Name  Description
path  Define the path to the stored data
====  ==================================


.. rubric:: Additional details from the README file:


VirusShare
^^^^^^^^^^

`VirusShare <https://virusshare.com/>`_ is a repository of malware samples to provide security researchers, incident responders, forensic analysts, and the morbidly curious access to samples of live malicious code.

The analyzer enables local searching for md5 hashes in Virusshare.com hash list. 

Requirements
~~~~~~~~~~~~


* Download the `VirusShare <https://virusshare.com/hashes>`_ hashlists. For convenience the ``getHashes.sh`` script is provided 
* In the analyzer parameters configure the ``path`` of downloaded hashlists folder.

