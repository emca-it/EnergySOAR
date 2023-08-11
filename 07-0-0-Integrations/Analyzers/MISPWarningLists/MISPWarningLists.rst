MISPWarningLists
================

.. image:: ./assets/misp.png
   :alt: logo

MISPWarningLists
----------------

.. rubric:: Details

===========================  ===============================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      2.0
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/misp-warninglists-analyzer
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           ip, hash, domain, fqdn, url
Service Homepage             `MISPWarningLists <https://github.com/MISP/misp-warninglists>`_
===========================  ===============================================================

.. rubric:: Description

Check IoCs/Observables against MISP Warninglists to filter false positives.

.. rubric:: Configuration

====  ============================
Name  Description
path  path to Warninglists folder
conn  sqlalchemy connection string
====  ============================


.. rubric:: Additional details from the README file:


MISPWarningLists
^^^^^^^^^^^^^^^^

`MISPWarningLists <https://github.com/MISP/misp-warninglists>`_ are lists of well-known indicators that can be associated to potential false positives, errors or mistakes.

The analyzer comes in a single flavour that will check observables against MISP Warninglists to filter false positives.

Requirements
~~~~~~~~~~~~

Option 1 low performances:


* Clone  the `MISPWarningLists <https://github.com/MISP/misp-warninglists>`_ GitHub repository.
* In the analyzer parameters configure the ``path`` of WarningLists folder.

Option 2 high performances:


* Clone  the `MISPWarningLists <https://github.com/MISP/misp-warninglists>`_ GitHub repository.
* Install `PostgreSQL <https://www.postgresql.org/>`_ database.
* Set ``conn_string`` and ``warninglists_path``  located inside script ``warninglists_create_db.py``  and run it in order to parse all MISPWarningLists and insert into PostgreSQL.
* In the analyzer parameters configure the ``conn`` to DB (for example: postgresql+psycopg2://user:password@localhost:5432/warninglists').

