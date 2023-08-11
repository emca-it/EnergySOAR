IVRE
====

.. image:: ./assets/ivre_logo.png
   :alt: Logo

IVRE
----

.. rubric:: Details

===========================  ================================================================================
Author                       Pierre Lalet
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           autonomous-system, certificate_hash, domain, fqdn, ip, network, port, user-agent
Service Homepage             `IVRE <https://ivre.rocks/>`_
===========================  ================================================================================

.. rubric:: Description

Fetch details from an IVRE instance.

.. rubric:: Configuration

==============  ====================================================================================================================================================
Name            Description
use_data        Use data from the data purpose (MaxMind)
use_passive     Use data from the passive purpose
use_scans       Use data from the scans (nmap) purpose
db_url          The URL of the IVRE database (e.g., mongodb://host/ivre or http://host/cgi); defaults to using IVRE's configuration
db_url_data     The URL of the IVRE database for the data purpose (e.g., maxmind:///usr/share/ivre/geoip or http://host/cgi); defaults to using IVRE's configuration
db_url_passive  The URL of the IVRE database for the passive purpose (e.g., mongodb://host/ivre or http://host/cgi); defaults to using IVRE's configuration
db_url_scans    The URL of the IVRE database for the scans (nmap) purpose (e.g., mongodb://host/ivre or http://host/cgi); defaults to using IVRE's configuration
==============  ====================================================================================================================================================


.. rubric:: Additional details from the README file:


IVRE
^^^^

Get intelligence from an `IVRE <https://ivre.rocks/>`_ instance.

Requirements
~~~~~~~~~~~~

You need an access to an IVRE instance. Unlike most analyzers, IVRE
does not exist as a public service but is an open-source tool: you
need to install and run your own instance. The repository is `on
GitHub <https://github.com/cea-sec/ivre>`_.

To learn more about IVRE (and its "purposes"), you can read the
documentation, particularly about `the
principles <https://doc.ivre.rocks/en/latest/overview/principles.html>`_\ ,
and some `use
cases <https://doc.ivre.rocks/en/latest/usage/use-cases.html>`_.

Supply the following parameters to the analyzer in order to use it:


* ``db_url`` (string): the IVRE instance database URL (format: same as IVRE's
  configuration; default: use IVRE's configuration)
* ``db_url_data`` (string): the IVRE instance database URL for the data purpose
  (idem)
* ``db_url_passive`` (string): the IVRE instance database URL for the passive purpose
  (idem)
* ``db_url_scans`` (string): the IVRE instance database URL for the scans purpose
  (idem)
* ``use_data`` (boolean): should the analyzer use the data purpose?
* ``use_passive`` (boolean): should the analyzer use the passive purpose?
* ``use_scans`` (boolean): should the analyzer use the scans purpose?

