Energy SOAR installation guide
====

Install
----

Supported OSes:

- Red Hat Linux 8
- Centos Linux/Stream 8
- Oracle Linux 8

.. tabs::

   .. tab:: Non-interactive
   
      .. warning::

         Run this command as root user in installation package directory
   
      .. code-block:: console
   
         ./install.sh -n
         
      Non-interactive mode install this services by default:

      * TheHive
      * Cortex
      * Elasticsearch 7
      * Cassandra 4
      
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

         ./install.sh -i

      Minimal single node architecture services:

      * TheHive
      * Cortex
      * Elasticsearch 7
      * Cassandra 4

      Example *interactive* installation

      .. code-block:: console
   
         ====> Do You wish to install the ENERGY SOAR TheHive, as well as the other TheHive dependencies? [y/n] y
         [..]
         ====> Do You wish to install the ENERGY SOAR Cortex, as well as the other Cortex dependencies? [y/n] y
         [..]
         ====> Do You wish to install the Cassandra 4? [y/n] y
         [..]
         ====> Do You wish to install the Elasticsearch 7? [y/n] y
         [..]
         ====> Do You wish to initialize Cortex data? [y/n] y
         [..]
         ====> Do You wish to initialize TheHive data? [y/n] y
         [..]
         

      .. note::
      
         Initialize Cortex data is needed to integrate with TheHive. During this step is created api user and configured in TheHive configuration.

      Initialize TheHive data:

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


