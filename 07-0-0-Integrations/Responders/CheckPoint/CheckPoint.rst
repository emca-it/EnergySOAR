CheckPoint
==========

CheckPoint_Lock
---------------

.. rubric:: Details

===========================  =====================
Author                       @dadokkio LDO-CERT
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  =====================

.. rubric:: Description

Lock ip on CheckPoint Gaia

.. rubric:: Configuration

===========  ===================================================
Name         Description
server       Checkpoint API server
username     CheckPoint username
password     CheckPoint password
group_name   CheckPoint group name ip will be added/removed from
exclusions   ip/subnet that cannot be locked or unlocked
added_tag    Tag added to observable when adding to FW
removed_tag  Tag added to observable when removing from FW
===========  ===================================================


CheckPoint_Unlock
-----------------

.. rubric:: Details

===========================  =====================
Author                       @dadokkio LDO-CERT
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           thehive:case_artifact
===========================  =====================

.. rubric:: Description

Unlock ip on CheckPoint Gaia

.. rubric:: Configuration

===========  ===================================================
Name         Description
server       Checkpoint API server
username     CheckPoint username
password     CheckPoint password
group_name   CheckPoint group name ip will be added/removed from
exclusions   ip/subnet that cannot be locked or unlocked
added_tag    Tag added to observable when adding to FW
removed_tag  Tag added to observable when removing from FW
===========  ===================================================


.. rubric:: Additional details from the README file:


CkeckPoint
^^^^^^^^^^

This responder permits you to add/remove selected observable from a specific group. 

Some notes:

.. code-block::

   - API must permit access from cortex machine.

   - First login from API must be manual because it needs fingerprint acceptance. This will generate a fingerprints.txt file that must be placed near to the analyzer python file.

   - It doesn't work in dockerized analyzer!

   - If group doesn't exists it'll be created [when blocking]. At the moment without any default rule.



Requirements
~~~~~~~~~~~~

The following options are required in CheckPoint Responder configuration:


* ``server`` : URL of CheckPoint instance 
* ``username``\ : user accessing CheckPoint instance
* ``password``\ :  password for the user accessing CheckPoint instance
* ``group_name``\ : name of the group ip will be added to or removed

