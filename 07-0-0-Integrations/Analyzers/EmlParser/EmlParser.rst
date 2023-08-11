EmlParser
=========

.. image:: ./assets/sb-logo.jpg
   :alt: StrangeBee logo

EmlParser
---------

.. rubric:: Details

===========================  =========================================
Author                       StrangeBee
Version                      2.1
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           file
Service Homepage             `EmlParser <https://www.strangebee.com>`_
===========================  =========================================

.. rubric:: Description

Parse and visualise EML email message. Submit a .eml formatted file and extract some useful information.

.. rubric:: Configuration

===================  =========================================================================================================================================================================================================================================
Name                 Description
email_visualisation  Enable email visualisation in report. This option requires the program `wkhtmltoimage` and installation of `wkhtmltopdf` package on the system. Docker image has this program installed. Refer to the documentation for more information.
wkhtmltoimage_path   Path of wkhtmltoimage program on the system. This program is required to generate visualisation of the message as it seen in mail client program. If using Docker image, use default configuration.
===================  =========================================================================================================================================================================================================================================


.. rubric:: Additional details from the README file:


This Analyzer allows you to view the content of an email without opening it in a dedicated application.

This programs gathers headers, message content, files, gives access to the raw message and extracts following observables: 


* email addresses from headers
* IP addresses and hostnames from headers
* URLs found in plain text and html content
* filenames and Files attached

Extracted observables are enriched with tags giving context.

Email visualisation
^^^^^^^^^^^^^^^^^^^

An option permits to get an overview of the HTML rendered email. The program creates a screenshot of html parts of the message, inline and attachment parts.
By default, this option is **not** enabled. To proceed, the Analyzer requires the program ``wkhtmltoimage`` beeing installed on the system. 

When enabled, the Analyzer tries to render the html included in the email. If it fails, a dedicated message is displayed.


.. image:: ./assets/emlparser-extracted-observables.png
   :target: ./assets/emlparser-extracted-observables.png
   :alt: 


Requirements
^^^^^^^^^^^^

``wkhtmltopdf`` program is required to enable visualisation. DEB and RPM packages exist.
Once installed, in Cortex, configure the Analyzer accordingly :


* set the parameter ``email_visualisation`` to true.
* If needed, replace the default value of the ``wkhtmltoimage`` program path in the parameter ``wkhtmltoimage_path`` (the default value suits the docker image of the Analyzer).

