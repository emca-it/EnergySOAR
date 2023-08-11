AnyRun
======

AnyRun_Sandbox_Analysis
-----------------------

.. rubric:: Details

===========================  =============================================
Author                       Andrea Garavaglia, Davide Arcuri, LDO-CERT
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file, url
Service Homepage             `AnyRun_Sandbox_Analysis <https://any.run/>`_
===========================  =============================================

.. rubric:: Description

Any.Run Sandbox file analysis

.. rubric:: Configuration

============  ==================================================================
Name          Description
token         API token
privacy_type  Define the privacy setting (Allowed values: public, bylink, owner)
verify_ssl    Verify SSL certificate
============  ==================================================================


.. rubric:: Additional details from the README file:


AnyRun
^^^^^^

`ANY.RUN <https://any.run/>`_ is a malware sandbox service in the cloud. By using this analyzer, an analyst can submit a suspicious file or URL to the service for analysis and get a report. The report can contain various information such as:


* Interactive access
* Research threats by filter in public submissions
* File and URL dynamic analysis
* Mitre ATT&CK mapping
* Detailed malware reports

Requirements
~~~~~~~~~~~~

You need a valid AnyRun API integration subscription to use the analyzer. Free plan does not provide API access.


* Provide your API token as a value for the ``token`` parameter.
* Define the privacy setting in ``privacy_type`` parameter.
* Set ``verify_ssl`` parameter as false if you connection requires it

