Hashdd
======

.. image:: ./assets/hashdd.png
   :alt: logo

Hashdd_Detail
-------------

.. rubric:: Details

===========================  ==========================================
Author                       iosonogio, dadokkio
Version                      2.0
License                      AGPLv3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  Yes
DataType Supported           hash
Service Homepage             `Hashdd_Detail <https://www.hashdd.com/>`_
===========================  ==========================================

.. rubric:: Description

Determine whether a hash is good or bad; if good then list what it is.

.. rubric:: Configuration

=======  ==================
Name     Description
api_key  API key for hashdd
=======  ==================


Hashdd_Status
-------------

.. rubric:: Details

===========================  ===================
Author                       iosonogio, dadokkio
Version                      2.0
License                      AGPLv3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           hash
===========================  ===================

.. rubric:: Description

Determine whether a hash is good or bad.

.. rubric:: Configuration

=======  ==================
Name     Description
api_key  API key for hashdd
=======  ==================


.. rubric:: Additional details from the README file:


Hashdd
^^^^^^

`Hashdd <https://www.hashdd.com/>`_  search engine for file hashes which automatically queries 3rd party services like VirusTotal and enriches the information provided based on the 3rd party data. 

The analyzer includes two flavors: Status and Detail. The first one is used to query hashdd without an API key for the threat level only. The latter produces additional meta information about the sample, but requires an API key.

Requirements
~~~~~~~~~~~~

A valid Hashdd API is necessary just for detail flavour, for status can still be added.


* Provide your API key as values for the ``key`` parameter.

