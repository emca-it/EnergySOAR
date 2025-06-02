LDAP
====

LDAP_ChangePWD
--------------

.. rubric:: Details

===========================  =======================================================
Author                       EMCA Software Sp. z o.o.
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact:mail, energysoar:case_artifact:other
===========================  =======================================================

.. rubric:: Description

Reset User Password (New pass have to be configured in responder configs, as Energy SOAR Base doen't support passing data on reponder invocation).

.. rubric:: Configuration

===========  ===========================================================
Name         Description
AD_Address   Example --> ldaps://ldaphost.example.com
AD_port      ldaps port. Example --> 636
username     Username of account that will query Active Directory server
password     Password of account that will query Active Directory server
base_DN      The base DN to use. Example --> dc=myorg,dc=com
NewPassword  The new Password to be changed to
VerifySSL    set to false to bypass SSL verification
===========  ===========================================================


LDAP_UnblockUser
----------------

.. rubric:: Details

===========================  =======================================================
Author                       EMCA Software Sp. z o.o.
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact:mail, energysoar:case_artifact:other
===========================  =======================================================

.. rubric:: Description

Unblock Normal Active Directory User

.. rubric:: Configuration

==========  ===========================================================
Name        Description
AD_Address  Example --> ldaps://ldaphost.example.com
AD_port     ldap port. Example --> 389 or 636
username    Username of account that will query Active Directory server
password    Password of account that will query Active Directory server
base_DN     The base DN to use. Example --> dc=myorg,dc=com
VerifySSL   set to false to bypass SSL verification
==========  ===========================================================


LDAP_BlockUser
--------------

.. rubric:: Details

===========================  =======================================================
Author                       EMCA Software Sp. z o.o.
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact:mail, energysoar:case_artifact:other
===========================  =======================================================

.. rubric:: Description

Block Normal Active Directory User

.. rubric:: Configuration

==========  ===========================================================
Name        Description
AD_Address  Example --> ldaps://ldaphost.example.com
AD_port     ldap port. Example --> 389 or 636
username    Username of account that will query Active Directory server
password    Password of account that will query Active Directory server
base_DN     The base DN to use. Example --> dc=myorg,dc=com
VerifySSL   set to false to bypass SSL verification
==========  ===========================================================


.. rubric:: Additional details from the README file:


This module provides responders for Energy SOAR Base Cortex to interface with LDAP services, enabling automated actions such as changing user passwords, locking and unlocking user accounts.

Responders Included:
^^^^^^^^^^^^^^^^^^^^


#. 
   **LDAP_ChangePWD**\ : This responder enables the automated reset or change of a user's password on an LDAP server. Note: This function requires the use of LDAPS (LDAP over SSL) for secure transmission of the new password.

#. 
   **LDAP_BlockUser**\ : This responder allows for the locking of a user's account in an LDAP directory.

#. 
   **LDAP_UnblockUser**\ : Similar to the block function, but this responder unlocks a user account in an LDAP directory.

Important Note:
^^^^^^^^^^^^^^^

For security and safety:


* Ensure that the credentials provided have the minimal necessary permissions.
* Regularly rotate the provided credentials.
* Always use LDAPS when transmitting sensitive information like passwords.

