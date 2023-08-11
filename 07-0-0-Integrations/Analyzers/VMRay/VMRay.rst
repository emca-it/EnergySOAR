VMRay
=====

VMRay
-----

.. rubric:: Details

===========================  =================================================
Author                       Nils Kuhnert, CERT-Bund
Version                      4.1
License                      AGPL-V3
Website                      https://github.com/BSI-CERT-Bund/cortex-analyzers
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           hash, file, url
===========================  =================================================

.. rubric:: Description

VMRay Sandbox file and URL analysis.

.. rubric:: Configuration

=======================  ===============================================================================================================================================================================================================================================================================
Name                     Description
url                      Define the URL of the service
key                      Define the API key
certverify               Verify certificates
certpath                 Path to certificate file, in case of self-signed etc.
verdict_only             If set to true, only the verdict (or the score for VMRay versions < 4.0) will be added as labels.
query_retry_wait         The amount of seconds to wait before trying to fetch the results.
recursive_sample_limit   The maximum amount of recursive samples which will be analyzed. 0 disables recursion.
reanalyze                If set to true, known samples will be re-analyzed on submission. This is enabled by default.
shareable                If set to true, the hash of the sample will be shared with VirusTotal if the TLP level is white or green.
archive_password         The password that will be used to extract archives.
archive_compound_sample  If set to true, files inside archives are treated as a single, compound sample. Otherwise, each file is treated as its own sample.
max_jobs                 Limits the amount of jobs that can be created by jobrules for a submission.
enable_reputation        If set to true, reputation lookups will be performed for submitted samples and analysis artifacts (file hash and URL lookups) by the VMRay cloud reputation service and additional third party services. The user analyzer setting is used as default value for this parameter.
enable_whois             If set to true, domains seen during analyses are queried with external WHOIS service. The user analyzer setting is used as default value for this parameter.
analyzer_mode            Specifies which types of analyzers will be used for analyzing this sample. Supported strings are 'reputation', 'reputation_static', 'reputation_static_dynamic', 'static_dynamic', and 'static'. The user analyzer setting is used as default value for this parameter.
known_malicious          If set to true, triage will be used to pre-filter known malicious samples by results of reputation lookup (if allowed) and static analysis. The user analyzer setting is used as default value for this parameter.
known_benign             If set to true, triage will be used to pre-filter known benign samples by results of reputation lookup (if allowed) and static analysis. The user analyzer setting is used as default value for this parameter.
tags                     Tags to attach to the sample.
timeout                  Analysis timeout in seconds.
net_scheme_name          Name of the network schema.
=======================  ===============================================================================================================================================================================================================================================================================

