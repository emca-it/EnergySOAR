SentinelOne
===========

SentinelOne_DeepVisibility_DNSQuery
-----------------------------------

.. rubric:: Details

===========================  =================
Author                       Joe Vasquez
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           url, domain, fqdn
===========================  =================

.. rubric:: Description

Query Sentinel One Deep Visibility API v2.1 for hosts that have requested DNS lookups for a domain/URL/FQDN.

.. rubric:: Configuration

==============  ======================================================================================
Name            Description
s1_console_url  Console URL
s1_api_key      API Key, don't forget this will expire!
s1_account_id   Account ID
hours_ago       Number of hours ago for the fromDate of the query.  ToDate will be now. Default is 12.
==============  ======================================================================================

