OpenCTI
=======

.. image:: ./assets/logo_opencti.png
   :alt: logo

OpenCTI_SearchExactObservable
-----------------------------

.. rubric:: Details

===========================  ========================================================================================================
Author                       ANSSI
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/TheHive-Project/Cortex-Analyzers/
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  No
DataType Supported           domain, ip, url, fqdn, uri_path, user-agent, hash, mail, mail_subject, registry, regexp, other, filename
Service Homepage             `OpenCTI_SearchExactObservable <https://www.opencti.io>`_
===========================  ========================================================================================================

.. rubric:: Description

Query multiple OpenCTI instances for a specific observable.

.. rubric:: Configuration

==========  =========================
Name        Description
name        Name of OpenCTI servers
url         URL of OpenCTI servers
key         API key for each server
cert_check  Verify server certificate
==========  =========================


OpenCTI_SearchObservables
-------------------------

.. rubric:: Details

===========================  ========================================================================================================
Author                       ANSSI
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/TheHive-Project/Cortex-Analyzers/
Requires Registration        Yes
Requires Subscription        No
Free Subscription Available  No
DataType Supported           domain, ip, url, fqdn, uri_path, user-agent, hash, mail, mail_subject, registry, regexp, other, filename
Service Homepage             `OpenCTI_SearchObservables <https://www.opencti.io>`_
===========================  ========================================================================================================

.. rubric:: Description

Query multiple OpenCTI instances for a list of observables matching a pattern.

.. rubric:: Configuration

==========  =========================
Name        Description
name        Name of OpenCTI servers
url         URL of OpenCTI servers
key         API key for each server
cert_check  Verify server certificate
==========  =========================


.. rubric:: Additional details from the README file:


`OpenCTI <https://www.opencti.io/en/>`_ is an open cyber threat intelligence platform which aims at providing a powerful knowledge management database with an enforced schema especially tailored for cyber threat intelligence and cyber operations and based on STIX 2.

The analyzer comes in only one flavor to look for an observable in the platform.
The analyzer comes in two flavors to search for an observable in the platform:


* OpenCTI\ ***SearchExactObservable**\ : returns an exact match only
* OpenCTI\ ***SearchObservables**\ : returns all observables containing the input data

Requirements
~~~~~~~~~~~~

The OpenCTI analyzer requires you to have access to one or several `OpenCTI <https://www.opencti.io/en/>`_
 instances. You can also deploy your own instance.
 instances in version 4. You can also deploy your own instance.

Three parameters are required for each instance to make the analyzer work:


* ``url`` : URL of the instance, e.g. "https://demo.opencti.io"

