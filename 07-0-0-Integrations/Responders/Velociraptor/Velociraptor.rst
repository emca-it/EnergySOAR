Velociraptor
============

Velociraptor_Flow
-----------------

.. rubric:: Details

===========================  =====================
Author                       Wes Lambert
Version                      0.1
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact
===========================  =====================

.. rubric:: Description

Run Velociraptor flow

.. rubric:: Configuration

==========================  ========================================================================
Name                        Description
velociraptor_client_config  Path to API client config file
velociraptor_artifact       Artifact to collect
upload_flow_results         Upload the results of a flow as an observable
thehive_url                 URL pointing to your Energy SOAR Base installation, e.g. 'http://127.0.0.1:9000'
thehive_apikey              Energy SOAR Base API key (used to add the downloaded file back to the alert/case)
==========================  ========================================================================


.. rubric:: Additional details from the README file:

.. role:: raw-html-m2r(raw)
   :format: html


Velociraptor
^^^^^^^^^^^^

This responder can be used to run a flow for a Velociraptor artifact.  This could include gathering data, or performing initial response, as the artifact (or artifact "pack") could encompass any number of actions.  The responder can be run on an observable type of ``ip``\ , ``fqdn``\ , or ``other``\ , and will look for a matching client via the Velociraptor server.  If a client match is found for the last seen IP, or the hostname, the responder will kick off the flow, the results will be returned, and the client ID will be added as a tag to the case and the observable.

Requirements
~~~~~~~~~~~~

The following options are required in the Velociraptor Responder configuration:   


* ``velociraptor_client_config``\ : The path to the Velociraptor API client config.\ :raw-html-m2r:`<br>`
  (See the following for generating an API client config: https://www.velocidex.com/docs/user-interface/api/, and ensure the appropriate ACLs are granted to the API user).  
* ``velociraptor_artifact``\ : The name artifact you which to collect (as you would see it in the Velociraptor GUI).
* ``upload_flow_results``\ : Upload flow results to Energy SOAR Base case (bool).
* `thehive_url`: URL of your Energy SOAR Base installation (e.g. 'http://127.0.0.1:9000').
* ``thehive_apikey``\ : Energy SOAR Base API key used to add flow results/file(s) to a case.

