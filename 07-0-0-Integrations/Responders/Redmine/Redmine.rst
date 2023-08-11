Redmine
=======

Redmine_Issue
-------------

.. rubric:: Details

===========================  ===============================
Author                       Marc-André DOLL
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case, thehive:case_task
===========================  ===============================

.. rubric:: Description

Create a redmine issue from a case

.. rubric:: Configuration

===============  =============================================================================================================================
Name             Description
instance_name    Name of the Redmine instance
url              URL where to find the Redmine API
username         Username to log into Redmine
password         Password to log into Redmine
project_field    Name of the custom field containing the Redmine project to use when creating the issue
tracker_field    Name of the custom field containing the Redmine tracker to use when creating the issue
assignee_field   Name of the custom field containing the Redmine assignee to use when creating the issue
reference_field  Name of the case custom field in which to store the opened issue. If not defined, this information will not be stored
opening_status   Status used when opening a Redmine issue (if not defined here, will use the default opening status from the Redmine Workflow)
closing_task     Closing the task after successfully creating the Redmine issue
===============  =============================================================================================================================

