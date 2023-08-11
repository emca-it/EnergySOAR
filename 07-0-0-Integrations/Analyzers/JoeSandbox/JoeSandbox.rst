JoeSandbox
==========

JoeSandbox_File_Analysis_Inet
-----------------------------

.. rubric:: Details

===========================  ========
Author                       CERT-BDF
Version                      3.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file
===========================  ========

.. rubric:: Description

Joe Sandbox file analysis with Internet access.

.. rubric:: Configuration

===============  =============================
Name             Description
url              URL of JoeSandbox service
key              API key
analysistimeout  Analysis timeout (seconds)
networktimeout   Network timeout (second)
HTML_report      Download HTML report
images           Allow images in the report
observables      Creat observables form report
===============  =============================


JoeSandbox_File_Analysis_Noinet
-------------------------------

.. rubric:: Details

===========================  ========
Author                       CERT-BDF
Version                      3.0
License                      AGPL-V3
Requires Registration        Yes
Requires Subscription        Yes
Free Subscription Available  No
DataType Supported           file
===========================  ========

.. rubric:: Description

Joe Sandbox file analysis without Internet access.

.. rubric:: Configuration

===============  =============================
Name             Description
url              URL of JoeSandbox service
key              API key
analysistimeout  Analysis timeout (seconds)
networktimeout   Network timeout (second)
HTML_report      Download HTML report
images           Allow images in the report
observables      Creat observables form report
===============  =============================


JoeSandbox_Url_Analysis
-----------------------

.. rubric:: Details

===========================  ========
Author                       CERT-BDF
Version                      2.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           url
===========================  ========

.. rubric:: Description

Joe Sandbox URL analysis.

.. rubric:: Configuration

===============  ==========================
Name             Description
url              URL of JoeSandbox service
key              API key
analysistimeout  Analysis timeout (seconds)
networktimeout   Network timeout (second)
===============  ==========================


.. rubric:: Additional details from the README file:


Joe SandBox
^^^^^^^^^^^

With the version 3.0 this analyzer allow you to have:


* the HTML report as an observable
* the screenshot from Joe Sandbox in the analysis report
* IP and URL as observable

This analyzer has 3 flavors:


* URL analysis
* File analysis inet
* File analysis noinet

