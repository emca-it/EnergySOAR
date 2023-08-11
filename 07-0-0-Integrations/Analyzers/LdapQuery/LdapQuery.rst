LdapQuery
=========

Ldap_Query
----------

.. rubric:: Details

===========================  ==================================================================================
Author                       Florian Perret @cyber_pescadito
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/cyberpescadito/Cortex-Analyzers/tree/master/analyzers/LdapQuery
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           username, mail
===========================  ==================================================================================

.. rubric:: Description

Query your LDAP server to harvest informations about an user of your organization

.. rubric:: Configuration

================  =========================================================================================================================================
Name              Description
LDAP_address      Should contain the protocol. Eg: ldaps://myldap.myorg.com
LDAP_port         Should contain the ldap port. Eg: 389 or 636
LDAP_username     Usernae of the account that will be used to bind to LDAP server. The Account should have permissions to read ldap objects and attributes.
LDAP_password     Password of the account used to bind to LDAP server.
base_DN           The base DN to use in your LDAP. Eg: dc=myorg,dc=com
uid_search_field  Specify here the field to use when searching by username. Eg: uid or sAMAccountName
attributes        Specify here the attributes you want to harvest. Eg: mail
================  =========================================================================================================================================

