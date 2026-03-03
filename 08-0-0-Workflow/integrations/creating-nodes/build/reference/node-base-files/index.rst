Node base file
==============

The node base file contains the core code of your node. All nodes must have a base file. The contents of this file are different depending on whether you're building a declarative-style or programmatic-style node. For guidance on which style to use, refer to `Choose your node building approach </08-0-0-Workflow/integrations/creating-nodes/plan/choose-node-method.html>`_.

These documents give short code snippets to help understand the code structure and concepts. For full walk-throughs of building a node, including real-world code examples, refer to `Build a declarative-style node </08-0-0-Workflow/integrations/creating-nodes/build/declarative-style-node.html>`_ or `Build a programmatic-style node </08-0-0-Workflow/integrations/creating-nodes/build/programmatic-style-node.html>`_.

You can also explore the `n8n-nodes-starter <https://github.com/n8n-io/n8n-nodes-starter>`_ and n8n's own `nodes <https://github.com/n8n-io/n8n/tree/master/packages/nodes-base/nodes>`_ for a wider range of examples. The starter contains basic examples that you can build on. The n8n `Mattermost node <https://github.com/n8n-io/n8n/tree/master/packages/nodes-base/nodes/Mattermost>`_ is a good example of a more complex programmatic-style node, including versioning.

For all nodes, refer to the:

* `Structure of the node base file </08-0-0-Workflow/integrations/creating-nodes/build/reference/node-base-files/structure.html>`_
* `Standard parameters </08-0-0-Workflow/integrations/creating-nodes/build/reference/node-base-files/standard-parameters.html>`_

For declarative-style nodes, refer to the:

* `Declarative-style parameters </08-0-0-Workflow/integrations/creating-nodes/build/reference/node-base-files/declarative-style-parameters.html>`_

For programmatic-style nodes, refer to the:

* `Programmatic-style parameters </08-0-0-Workflow/integrations/creating-nodes/build/reference/node-base-files/programmatic-style-parameters.html>`_
* `Programmatic-style execute() method </08-0-0-Workflow/integrations/creating-nodes/build/reference/node-base-files/programmatic-style-execute-method.html>`_

.. toctree::
    :maxdepth: 1

    declarative-style-parameters
    programmatic-style-execute-method
    programmatic-style-parameters
    standard-parameters
    structure
