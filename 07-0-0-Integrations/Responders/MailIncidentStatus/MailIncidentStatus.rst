MailIncidentStatus
==================

MailIncidentStatus
------------------

.. rubric:: Details

===========================  ==============
Author                       Manuel Krucker
Version                      1.0
License                      AGPL-V3
Requires Registration        No
Requires Subscription        No
Free Subscription Available  No
DataType Supported           energysoar:case
===========================  ==============

.. rubric:: Description

Mail a detailed status information of an incident case. The mail is sent to recipients specified by tags prefixed with 'mail='. The responder respects tlp definitions. For tlp:amber mail addresse and for tlp:green mail domains must be pre-defined in the configuration. For tlp:red sending mails is denied. The responser also uses thehive4py to collect information about the status of the tasks of the incidents.

.. rubric:: Configuration

===========================  ============================================================================================================
Name                         Description
from                         email address from which the mail is send
smtp_host                    SMTP server used to send mail
smtp_port                    SMTP server port
smtp_user                    SMTP server user
smtp_pwd                     SMTP server password
mail_subject_prefix          Prefix of the mail subject
mail_html_style_tag_content  The css content of the style tag for the HTML mail body. Define table, th, hd, .first, and .second elements.
tlp_amber_mail_addresses     Mail addresses which are allowed to receive tlp:amber classified incidents
tlp_green_mail_domains       Mail domains which are allowed to receive tlp:green classified incidents
energysoar_url                  URL pointing to your Energy SOAR Base installation, e.g. 'http://127.0.0.1:9000'
energysoar_apikey               Energy SOAR Base API key which is used get tasks and other elements of the incident
===========================  ============================================================================================================

