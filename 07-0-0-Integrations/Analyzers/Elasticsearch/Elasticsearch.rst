Elasticsearch
=============

Elasticsearch_Analysis
----------------------

.. rubric:: Details

===========================  =====================================
Author                       Nick Prokop
Version                      1.0
License                      MIT
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           url, domain, ip, hash, filename, fqdn
===========================  =====================================

.. rubric:: Description

Search for IoCs in Elasticsearch

.. rubric:: Configuration

=========  =================================================================================================
Name       Description
endpoints  Define the Elasticsearch endpoints
keys       Set the Elasticsearch api keys for each endpoint. Note: Use api key or basic auth, but not both.
users      Set the Elasticsearch users for each endpoint. Note: Use api key or basic auth, but not both.
passwords  Set the Elasticsearch passwords for each endpoint. Note: Use api key or basic auth, but not both.
kibana     Define the kibana address
dashboard  Set the kibana dashboard id that will be linked in the report
index      Define the Elasticsearch indices to use
field      Define the fields to query
size       Define the number of hits per index to return
verifyssl  Verify SSL certificate
cert_path  Path to the CA on the system used to check server certificate
=========  =================================================================================================

