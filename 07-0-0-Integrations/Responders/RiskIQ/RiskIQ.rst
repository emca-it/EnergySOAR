RiskIQ
======

RiskIQ_PushArtifactToProject
----------------------------

.. rubric:: Details

===========================  =====================
Author                       RiskIQ
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  =====================

.. rubric:: Description

Push a case to a RiskIQ Illuminate project.

.. rubric:: Configuration

====================  =============================================================================================================================
Name                  Description
username              API username of the RiskIQ Illuminate or PassiveTotal account (usually an email address)
api_key               API key of the RiskIQ Illuminate or PassiveTotal account
project_visibility    Visiblity for new RiskIQ Illuminate projects (analyst, team, or public).
project_prefix        Prefix to add when auto-generating project names from case names.
thehive_artifact_tag  Tag to apply to artifact in TheHive when is has been pushed to a RiskIQ Illuminate Project (leave blank to skip tagging).
riq_artifact_tag      Tag to apply to artifact in RiskIQ Illuminate when is has been pushed to an Illuminate Project (leave blank to skip tagging).
====================  =============================================================================================================================

