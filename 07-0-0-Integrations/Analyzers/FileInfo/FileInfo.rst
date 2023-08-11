FileInfo
========

FileInfo
--------

.. rubric:: Details

===========================  ===============
Author                       TheHive-Project
Version                      8.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           file
===========================  ===============

.. rubric:: Description

Parse files in several formats such as OLE and OpenXML to detect VBA macros, extract their source code, generate useful information on PE, PDF files...

.. rubric:: Configuration

===========================  ==================================================================================================================
Name                         Description
manalyze_enable              Wether to enable manalyze submodule or not.
manalyze_enable_docker       Use docker to run Manalyze. Can be used only if not using the docker image of FileInfo
manalyze_enable_binary       Use local binary to run Manalyze. Need to compile it before!
manalyze_binary_path         Path to the Manalyze binary that was compiled before. Keep the default value if using the docker image of FileInfo
floss_enable                 Enable the use of FireEye FLARE FLOSS
floss_binary_path            Path to the FLOSS binary.
floss_minimal_string_length  Length of strings must be in order to be considered.
===========================  ==================================================================================================================

