Inoitsu
=======

.. image:: ./assets/inoitsu_logo.png
   :alt: logo

Inoitsu
-------

.. rubric:: Details

===========================  ==============================================
Author                       Abdelkader Ben Ali
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  Yes
DataType Supported           mail
Service Homepage             `Inoitsu <https://www.hotsheet.com/inoitsu/>`_
===========================  ==============================================

.. rubric:: Description

Query Inoitsu for a compromised email address.

.. rubric:: Configuration

====  ===========
Name  Description
====  ===========


.. rubric:: Additional details from the README file:


Inoitsu-analyzer
================

This analyzer helps you investigate suspicious emails received from known or unknown senders to ensure that their email addresses aren't compromised.

No API key required.

If the email is compromised then it returns:


* Total breaches
* Most recent breach
* Breached data 
* Critical data
* Exposure rating: The comparative data exposure and risk rating assigned to this email address.

Testing Inoitsu analyzer (Cortex)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You need first to enable the analyzer.


.. image:: https://user-images.githubusercontent.com/37407314/92718622-f4079d00-f359-11ea-8124-0ee9ca565661.PNG
   :target: https://user-images.githubusercontent.com/37407314/92718622-f4079d00-f359-11ea-8124-0ee9ca565661.PNG
   :alt: enable analyzer


Navigate to Analyzers then run Inoitsu analyzer.


.. image:: https://user-images.githubusercontent.com/37407314/92719258-ce2ec800-f35a-11ea-9f82-f4ed9f4ab01e.PNG
   :target: https://user-images.githubusercontent.com/37407314/92719258-ce2ec800-f35a-11ea-9f82-f4ed9f4ab01e.PNG
   :alt: run analyzer


Test Inoitsu analyzer on a compromised email address.


.. image:: https://user-images.githubusercontent.com/37407314/92719758-8d837e80-f35b-11ea-8120-014a389955cd.PNG
   :target: https://user-images.githubusercontent.com/37407314/92719758-8d837e80-f35b-11ea-8120-014a389955cd.PNG
   :alt: report


Test Inoitsu analyzer on an uncompromised email address.


.. image:: https://user-images.githubusercontent.com/37407314/92720556-a9d3eb00-f35c-11ea-8157-911d85149ae4.PNG
   :target: https://user-images.githubusercontent.com/37407314/92720556-a9d3eb00-f35c-11ea-8157-911d85149ae4.PNG
   :alt: uncompromised


Testing Inoitsu analyzer (TheHive)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the observables section add emails to test.

Then select the emails that you want to analyze, select Inoitsu and click on Run selected analyzers.


.. image:: https://user-images.githubusercontent.com/37407314/92724230-2d440b00-f362-11ea-8115-21c91bf27d2d.PNG
   :target: https://user-images.githubusercontent.com/37407314/92724230-2d440b00-f362-11ea-8115-21c91bf27d2d.PNG
   :alt: thehive iocs



.. image:: https://user-images.githubusercontent.com/37407314/92725358-f2db6d80-f363-11ea-8e59-697e579a75aa.PNG
   :target: https://user-images.githubusercontent.com/37407314/92725358-f2db6d80-f363-11ea-8e59-697e579a75aa.PNG
   :alt: response


To view the report of the compromised email, click on ``Inoitsu:Compromised="True"``


.. image:: https://user-images.githubusercontent.com/37407314/92727316-d3920f80-f366-11ea-9e29-d2c21d286277.PNG
   :target: https://user-images.githubusercontent.com/37407314/92727316-d3920f80-f366-11ea-9e29-d2c21d286277.PNG
   :alt: analyzer report


To view the report of the uncompromised email, click on ``Inoitsu:Compromised="False"``


.. image:: https://user-images.githubusercontent.com/37407314/92727203-a5accb00-f366-11ea-875a-da30f01b6c4d.PNG
   :target: https://user-images.githubusercontent.com/37407314/92727203-a5accb00-f366-11ea-875a-da30f01b6c4d.PNG
   :alt: analyzer report 2


