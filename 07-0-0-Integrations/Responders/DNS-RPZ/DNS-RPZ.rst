DNS-RPZ
=======

DNS-RPZ
-------

.. rubric:: Details

===========================  =============================================================
Author                       Michael Hornung; Expeditors International of Washington, Inc.
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  =============================================================

.. rubric:: Description

Add a dynamic DNS entry to a Response Policy Zone, blackholing or redirecting a FQDN.

.. rubric:: Configuration

==============  =============================================================
Name            Description
bind_server     IP or FQDN of RPZ master BIND server
tsig_keyname    Name of TSIG key to access BIND server
tsig_keyval     TSIG key value to access BIND server
tsig_hashalg    TSIG hash algorithm to use
rpz_zonename    Fully qualified RPZ zone name (don't forget the trailing dot)
remediation_ip  IP to resolve RPZ names to
==============  =============================================================

