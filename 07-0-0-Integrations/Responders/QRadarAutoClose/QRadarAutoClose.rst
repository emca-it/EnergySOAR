QRadarAutoClose
===============

QRadar_Auto_Closing_Offense
---------------------------

.. rubric:: Details

===========================  ==============
Author                       Florian Perret
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case
===========================  ==============

.. rubric:: Description

Closing the QRadar Offense associated to your case in one clic !

.. rubric:: Configuration

==============  =======================================================================================================
Name            Description
QRadar_API_Key  A QRadar API key with sufficent rights to close an offense
QRadar_Url      URL of your QRadar API, must be accessible from Cortex server. eg: myqradar.myorg.com/api/siem/offenses
Cert_Path       If you need a certificate to authentificate to your QRadar API, please provide the path here
==============  =======================================================================================================


.. rubric:: Additional details from the README file:


Simple responder to close a QRadar Offense through a simple clic !

If you need to change the customfield which contain the QRadar Offense ID, change the "externalReferences" from QRadarAutoClose.py line 15.
Be careful this have to be fulfill with the "Internal Reference" of the customfield, not it's name !

