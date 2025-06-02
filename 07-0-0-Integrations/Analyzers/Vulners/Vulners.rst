Vulners
=======

.. image:: ./assets/vulners_logo.png
   :alt: logo

Vulners_CVE
-----------

.. rubric:: Details

===========================  ====================================
Author                       Dmitry Uchakin, Vulners team
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  Yes
DataType Supported           cve
Service Homepage             `Vulners_CVE <https://vulners.com>`_
===========================  ====================================

.. rubric:: Description

Get information about CVE from powerful Vulners database.

.. rubric:: Configuration

====  ===================
Name  Description
key   API key for Vulners
====  ===================


Vulners_IOC
-----------

.. rubric:: Details

===========================  ====================================
Author                       Dmitry Uchakin, Vulners team
Version                      1.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  Yes
DataType Supported           url, domain, ip
Service Homepage             `Vulners_IOC <https://vulners.com>`_
===========================  ====================================

.. rubric:: Description

Get information from the RST Threat Feed, which integrated with Vulners, for a domain, url or an IP address.

.. rubric:: Configuration

====  ===================
Name  Description
key   API key for Vulners
====  ===================


.. rubric:: Additional details from the README file:


Vulners-analyzer
^^^^^^^^^^^^^^^^

This analyzer consists of 2 parts.


#. **Vulners_IOC**\ : As a result of collaboration between Vulners and RST Threat Feed, the idea was to send IOC analysis results through theHive analyzer: blog post
#. **Vulners_CVE**\ : Vulners have a strong vulnerability database. This data is useful if:
   "if the case (incident) is related to the exploitation of a vulnerability, then the analyst (manually / automatically) can add it to observables and quickly get all the basic information on it in order to continue analyzing the case."

Vulners API key required.

Setting up analyzer
~~~~~~~~~~~~~~~~~~~


* copy the folders "Vulners" analyzer & "Vulners" into your Cortex analyzer path
* install necessary python modules from the requirements.txt (\ **pip install -r requirements.txt**\ )
* restart Cortex to initialize the new Responder "\ **systemctl restart cortex**\ "

Get your Vulners api key: 
.. image:: assets/vulners_api.png
   :target: assets/vulners_api.png
   :alt: Vulners API


Add your Vulners API in Cortex settings: 
.. image:: assets/Cortex_settings.PNG
   :target: assets/Cortex_settings.PNG
   :alt: API key in Cortex


Add Observable type in Energy SOAR Base
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

By default theHive does not have a "cve" type to be observables, so we have to add it to Administrator Settings:


.. image:: assets/theHive_add_cve.png
   :target: assets/theHive_add_cve.png
   :alt: add observable
​

Run the Analyzer in Energy SOAR Base
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Network IOCs:
"""""""""""""

Short template:


.. image:: assets/ioc_short_template.png
   :target: assets/ioc_short_template.png
   :alt: Short IOC template


Long template:


.. image:: assets/ioc_long_template.png
   :target: assets/ioc_long_template.png
   :alt: Long IOC template



.. image:: assets/ioc_with_malware_family.PNG
   :target: assets/ioc_with_malware_family.PNG
   :alt: Long_IOC_threat_template


Vulnerabilities:
""""""""""""""""

Short template: 


.. image:: assets/cve_short_template.png
   :target: assets/cve_short_template.png
   :alt: Short CVE template


Long template:


.. image:: assets/cve_long_template.gif
   :target: assets/cve_long_template.gif
   :alt: Long CVE template


