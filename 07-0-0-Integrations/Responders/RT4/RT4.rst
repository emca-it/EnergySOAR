RT4
===

RT4-CreateTicket
----------------

.. rubric:: Details

===========================  ==============================================================================
Author                       Michael Davis, REN-ISAC
Version                      1.0
License                      MIT
Website                      https://github.com/TheHive-Project/Cortex-Analyzers/tree/master/responders/RT4
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case_artifact, energysoar:alert, energysoar:case
===========================  ==============================================================================

.. rubric:: Description

Energy SOAR Automation to create a ticket in RT4 from Energy SOAR Base observables or alerts

.. rubric:: Configuration

===================  ====================================================================================================================================================
Name                 Description
server               RT4 Base URL, e.g., https://rt.domain.local
username             RT4 username for authentication
password             RT4 password for user account
Queue                Default queue in which to create new tickets
Owner                Default owner to assign newly created tickets (optional)
Status               Default ticket status to assign newly created tickets (optional)
custom_field_list    Name:Value of Custom Fields in RT to set on every ticket created (e.g.: 'How Reported:TheHive' sets CF.{How Reported} = Energy SOAR Base on every new ticket)
tag_to_template_map  Mapping table of tags to templates (e.g.: 'phishing:phish_letter' maps anything tagged as 'phishing' to the 'phish_letter' template)
thehive_cf_rtticket  Name of a case custom field in Energy SOAR Base in which RT ticket #s will be saved upon successful case-level Responder run (optional)
thehive_url          Energy SOAR Base Base URL, e.g., https://thehive.domain.local:9000 (optional: only needed to process Cases)
thehive_token        Energy SOAR Base API token for authentication (optional: only needed to process Cases)
===================  ====================================================================================================================================================


.. rubric:: Additional details from the README file:


Request Tracker 4 Energy SOAR Automation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Summary: Creates RT tickets from TheHive

Applies To: Case Observables (Artifacts), Alerts, Cases

Initial Responder Configuration
"""""""""""""""""""""""""""""""

The following need to be configured under **Organization --> Responders** prior to use:

``server`` - **Required** - RT4 base URL, e.g.: https://rt.domain.local

``username`` - **Required** - RT4 username for API authentication

``password`` - **Required** - RT4 password for user account above

``Queue`` - **Required** - Default queue in which to create new tickets (can be overriden by custom tag on observables)

``Owner`` - Default owner to assign newly created tickets (Optional - can be overriden by custom tags per observable)

``Status`` - Default status to assign newly created tickets (Optional - can be overriden by custom tags per observable)

``custom_field_list`` - Colon-separated Name:Value pairs of RT custom fields and values to set across all newly-created tickets (Optional - can be overriden by custom tags per observable) - adding a value of ``How Reported:TheHive`` would set the custom field named ``How Reported`` to ``TheHive`` on all newly created tickets

``tag_to_template_map`` - **Required** - Tags to Templates mapping (can be overriden by custom tag on observables). Should be colon-separated tag-to-template values. E.g.

``thehive_cf_rtticket`` - Name of a case custom field in Energy SOAR Base in which RT ticket #s will be saved upon successful case-level Responder run (Optional - Energy SOAR Base Custom Field should be of type 'String')

``thehive_url`` - Energy SOAR Base Base URL, e.g., https://thehive.domain.local:9000 (Optional - only needed to process Cases)

``thehive_token`` - Energy SOAR Base API token for authentication (Optional - only needed to process Cases)

.. code-block::


   phishing:phishing_generic
   spear_phishing:phishing_spear

Any observable with a ``phishing`` tag would be assigned the template named ``phishing_generic``. Any observale tagged ``spear_phishing`` would have its ticket created with a body from the ``phishing_spear`` template.

Workflow
""""""""


#. Set `Initial Responder Configuration <#Initial-Responder-Configuration>`_
#. `Create Template(s) <#Templates>`_
#. As new observables arrive, appropriately `tag <#Tags-to-Modify-RT4-Responder-Behavior>`_ them
#. Run the RT4-CreateTicket responder
#. When complete, the ticket(s) should be created and the ``thehive_cf_rtticket`` custom field on Energy SOAR Base cases (if present) should be populated with the URL to any created ticket

Templates
"""""""""

Inside the ``./templates`` dir of the RT4 responder, you will need to create the templates for subjects and notification bodies that will be used on ticket creation. For the above example on an observable tagged to use the ``phishing_generic`` template, there should be a file inside ./templates/ called ``phishing_generic.j2`` (all templates should end in the .j2 extension since it uses Jinja2 templating)

The .j2 files should be formatted like so:

.. code-block::

   {% block Subject %}
   [SOC] ** Notification ** Phishing Site Targeting Your Organization
   {% endblock %}


   {% block Text %}
   Greetings,

   We have recently discovered a potential phishing site targeting employees at your organization:

   Domain(s):
   {{ indicator_list }}

   On behalf of the SOC,

   --
   soc@org.local
   24x7 Watch Desk
   https://www.org.local
   {% endblock %}

The mandatory blocks are ``Subject`` and ``Text`` inside which are the respective content for the ticket creation. You may reference any variables inside the template file which exist in the observable/artifact/alert/case for population of other data within the ticket notification (in the above case, ``indicator_list``\ ). Those variables should be inside double curly-braces as is the format for Jinja. Example data available in the `Observable Object Data <#Observable-Object-Data>`_ section.

Inside the jinja2 template, all block names are passed at RT ticket variables with their respective block values upon ticket creation. Therefore, any number of blocks corresponding to RT fields can also be assigned to further customize setting ticket variables at the template level.

*Example*\ : 

``{% block CF_Classification %}Phishing{% endblock %}``

Every ticket created from that template will have the RT custom field CF_Classification set to "Phishing" upon ticket creation.

Tags to Modify RT4 Responder Behavior
"""""""""""""""""""""""""""""""""""""

Set any of the following tags to modify behavior of the created ticket:

``rt4_set_requestor:customer@domain.local`` or ``contact:customer@domain.local`` - **Required** - This is the only tag that must be present. Without one of these, the ticket won't be created.

``rt4_set_cf_Classification:phishing`` - sets the CF.{Classification} = 'phishing' in RT ticket

``rt4_set_cc:staff@domain.local`` - adds staff@domain.local as Cc on ticket

``rt4_set_admincc:emp@domain.local`` - sets AdminCc of ticket to emp@domain.local

``rt4_set_owner:staff@domain.local`` - sets Owner of ticket to staff@domain.local (\ **must match person in RT or ticket creation will fail**\ )

``rt4_set_queue:Incident Reports`` - sets Queue of ticket created to *Incident Reports*

``rt4_set_subject:This is a test`` - overrides the Subject line from the template with *This is a test*

``rt4_set_status:Resolved`` - creates the ticket and then sets its status to *Resolved* (can also use any other ticket status in your RT instance)

``rt4_set_template:phishing_generic`` - overrides any default template from tag_to_template_map setting when constructing the body of the notification, in this case instructing the Responder to use the ``phishing_generic`` template

Ticket customization order
""""""""""""""""""""""""""

As already alluded to, there are 4 ways to customize ticket creation options:


#. Global level

   * Queue
   * Owner
   * Status
   * Custom Fields
   * Template 

#. Template level

   * All of the above except Template, plus:
   * Requestor/Cc/AdminCc

#. Case/Alert level

   * All RT options

#. Case artifact/observable level

   * All RT options

Greater numbered config options take precedence over smaller ones.

*Example:*

If a tag_to_template map at the Org Responder config in Cortex is set to map tags of ``phishing`` to the ``phishing_generic`` template, but a ``set_rt4_template:phishing_spear`` tag on the observable sets a different template, the observable tag takes precedence.

Observable Object Data
""""""""""""""""""""""

Observables are a custom dictionary in which their properties are stored. In addition to the ticket properties passed to RT, each observable is also tagged with its case/artifact info which makes available the following info in each observable:

.. code-block::

   "owner": "michael",
       "severity": 2,
       "_routing": "AWxyhvveZCXO8BqIWSLs",
       "flag": false,
       "updatedBy": "michael",
       "customFields": {
         "RTTicket": {
           "string": "http://192.168.0.2/Ticket/Display.html?id=141, http://192.168.0.2/Ticket/Display.html?id=142, http://192.168.0.2/Ticket/Display.html?id=143"
         }
       },
       "_type": "case",
       "description": "test",
       "title": "RT-testing",
       "tags": [
         "contact:requestor@domain.tld",
         "rt4:submitted"
       ],
       "createdAt": 1565289544365,
       "_parent": null,
       "createdBy": "michael",
       "caseId": 1,
       "tlp": 2,
       "metrics": {
         "seen_prior": 1
       },
       "_id": "AWxyhvveZCXO8BqIWSLs",
       "id": "AWxyhvveZCXO8BqIWSLs",
       "_version": 45,
       "startDate": 1565289480000,
       "pap": 2,
       "status": "Open",
       "updatedAt": 1570482005825,
       "indicator_list": [
         "malicious.baddomain.tld"
       ]

Those properties can all be referenced as variables in the jinja2 template as mentioned in the `Templates section <#Templates>`_.

