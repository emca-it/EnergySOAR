Energy SOAR installation guide
====

Install
----

Supported OSes:

- Oracle Linux 8
- Red Hat Linux 8 
- Centos Linux/Stream 8

.. tabs::

   .. tab:: Non-interactive
   
      .. warning::

         Run this command as root user in installation package directory
   
      .. code-block:: console
   
        # ./install.sh -n
         
      Non-interactive mode install this services and it's dependencies by default:

      * Energy SOAR Base
      * Energy SOAR Automation
      
      After service installation it load some sample data. 
      
      - create sample users
      - load analyzers template
      - configure Cortex integration
      - import MISP Taxonomies
      - load sample Playbooks
      - create Cortex database schema
   
   .. tab:: Interactive
   
      .. warning::

         Run this command as root user in installation package directory

      .. code-block:: console

        # ./install.sh -i

      Minimal single node architecture services:

      * Energy SOAR Base
      * Energy SOAR Automation

      Example *interactive* installation

      .. code-block:: console
   
         ====> Do You wish to install the ENERGY SOAR Base, as well as the other Energy SOAR Base dependencies? [y/n] y
         [..]
         ====> Do You wish to install the ENERGY SOAR Automation, as well as the other Energy SOAR Automation dependencies? [y/n] y
         [..]
         ====> Do You wish to initialize Energy SOAR Automation data? [y/n] y
         [..]
         ====> Do You wish to initialize Energy SOAR Base data? [y/n] y
         [..]
         

      .. note::
      
         Initialize Energy SOAR Automation data is needed to integrate with Energy SOAR Base. During this step is created api user and configured in Energy SOAR Base configuration.

      Initialize Energy SOAR Base data:

      - import MISP Taxonomies
      - create sample users
      - create sample case/alert
      - import Analyzer templates
      - configure Cortex plugin
         
.. table:: Sample users

   +------------------------------+-----------+
   | User                         | Password  |
   +==============================+===========+
   | `admin@energysoar.local`     | secret    |
   +------------------------------+-----------+
   | `socadmin@energysoar.local`  | socadmin  |
   +------------------------------+-----------+
   | `socuser@energysoar.local`   | socuser   |
   +------------------------------+-----------+
   | `socro@energysoar.local`     | socro     |
   +------------------------------+-----------+


