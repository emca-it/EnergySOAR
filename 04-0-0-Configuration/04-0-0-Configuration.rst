=================
Configuration
=================

Automation
------

Analyzers can only be configured using the Web interface and their associated configuration is stored in the underlying Logserver database. However, the Energy SOAR Automation application configuration is stored in the `/etc/cortex/application.conf` file.

Database
^^^^^^^^

Energy SOAR Automation by default utilize the Energy Logserver data node 7.8+ search engine to store persistent data.
This is prefered method used during non interactive instalation.

Energy SOAR Automation can also utilize the Elasticsearch 7.x search engine to store persistent data, but its use is not mandatory.
Elasticsearch is not part of the Energy SOAR Automation package. It must be installed and configured
as a standalone instance which can be located on the same machine.

Three settings are required to connect to Elasticsearch:
 * the base name of the index
 * the name of the cluster
 * the address(es) and port(s) of the Elasticsearch instance

The default settings are:

.. code-block::

    ### Elasticsearch
    search {
      # Name of the index
      index = automation
      # Name of the Elasticsearch cluster
      cluster = energysoar
      # Address of the Elasticsearch instance
      host = ["127.0.0.1:9300"]
      # Scroll keepalive
      keepalive = 1m
      # Size of the page for scroll
      pagesize = 50
      # Number of shards
      nbshards = 5
      # Number of replicas
      nbreplicas = 1
      # Arbitrary settings
      settings {
        # Maximum number of nested fields
        mapping.nested_fields.limit = 100
      }

      ### XPack SSL configuration
      # Username for XPack authentication
      #user = "" 
      # Password for XPack authentication
      #password =  ""
      # Enable SSL to connect to ElasticSearch
      ssl.enabled = false
      # Path to certificate authority file
      #ssl.ca = ""
      # Path to certificate file
      #ssl.certificate = "" 
      # Path to key file
      #ssl.key = "" 

      ### SearchGuard configuration
      # Path to JKS file containing client certificate
      #guard.keyStore.path = ""
      # Password of the keystore
      #guard.keyStore.password = "" 
      # Path to JKS file containing certificate authorities
      #guard.trustStore.path = ""
      ## Password of the truststore
      #guard.trustStore.password = "" 
      # Enforce hostname verification
      #guard.hostVerification = ""
      # If hostname verification is enabled specify if hostname should be resolved
      #guard.hostVerificationResolveHostname = "" 
    }

If you use a different configuration, please make sure to modify the parameters accordingly in the
`application.conf` file.

If multiple Elasticsearch nodes are used as a cluster, addresses of the master
nodes must be used for the `search.host` setting. All cluster nodes must use the
same cluster name:

.. code-block::

    search {
        host = ["node1:9300", "node2:9300"]
    }


Energy SOAR Automation uses the port 9300/tcp by default. Energy SOAR Automation cannot use the HTTP transport as of this writing (9200/tcp).

Energy SOAR Automation creates specific index schema (mapping) versions in Energy Logserver. Version numbers are
appended to the index base name (the 8th version of the schema uses the index
`automation_8` if `search.index = automation`). When too many documents are requested, it uses the
scroll feature: the results are retrieved through pagination. You can specify the size
of the page (`search.pagesize`) and how long pages are kept in Logserver
(`search.keepalive`) before purging.

XPack and SearchGuard are optional and exclusive. If Energy SOAR Automation finds a valid configuration for XPack, SearchGuard configuration is ignored.

Analyzers and Responders
^^^^^^^^^^^^^^^^^^^^^^^^


Energy SOAR Automation is able to run workers (analyzers and responders) installed locally or available as Docker image. Settings `analyzer.urls` and in `responder.urls` list paths or urls where Energy SOAR Automation looks for analyzers and responders. Theses settings accept:
1. a path to a directory that Energy SOAR Automation scans to locate workers
2. a path or an URL to a JSON file containing a JSON array of worker definitions

Worker definition is a JSON object that describe the worker, how to configure it and how to run it. If it contains a field "command", worker can be run using process runner (i.e. the command is executed). If it contains a field "dockerImage", worker can be run using docker runner (i.e. a container based on this image is started). If it contains both, the runner is chosen according to `job.runners` settings (`[docker, process]` by default).

For security reason, if worker definitions fetched from remote url (http/https) contain command, they are ignored.

You can control the number of simultaneous jobs that Energy SOAR Automation executes in parallel using the
`analyzer.fork-join-executor` configuration item. The value depends on the
number of CPU cores (`parallelism-factor` * nbCores), with a minimum
(`parallelism-min`) and a maximum (`parallelism-max`).

Similar settings can also be applied to responders.

.. code-block::

    analyzer {
      # Directory that holds analyzers
      urls = [
        "/path/to/default/analyzers",
        "/path/to/my/own/analyzers"
      ]

      fork-join-executor {
        # Min number of threads available for analyze
        parallelism-min = 2
        # Parallelism (threads) ... ceil(available processors * factor)
        parallelism-factor = 2.0
        # Max number of threads available for analyze
        parallelism-max = 4
      }
    }

    responder {
      # Directory that holds responders
      urls = [
        "/path/to/default/responders",
        "/path/to/my/own/responders"
      ]

      fork-join-executor {
        # Min number of threads available for analyze
        parallelism-min = 2
        # Parallelism (threads) ... ceil(available processors * factor)
        parallelism-factor = 2.0
        # Max number of threads available for analyze
        parallelism-max = 4
      }
    }

Authentication
^^^^^^^^^^^^^^

Like EnergySOAR Base, Energy SOAR Automation plugin supports local, LDAP, Active Directory (AD), X.509 SSO and/or API keys for authentication and OAuth2.

Please note that API keys can only be used to interact with the Energy SOAR Automation API (for example when Energy SOAR Base is interfaced with a Energy SOAR Automation instance, it must use an API key to authenticate to it). API keys cannot be used to authenticate to the Web UI. By default, Energy SOAR Automation relies on local credentials stored in Logserver.

Authentication methods are stored in the `auth.provider` parameter, which is
multi-valued. When a user logs in, each authentication method is tried in order
until one succeeds. If no authentication method works, an error is returned and
the user cannot log in.

The default values within the configuration file are:

.. code-block::

    auth {
      providers = [
        {name: session}
        {name: basic, realm: thehive}
        {name: local}
        {name: key}
      ]
    }

Details of each authentication method are explained below.

session
"""""""""
Authenticates HTTP requests using a cookie. This module manages cookie creation and expiration.

Configuration parameters:

- `inactivity` (duration): Maximum time of user inactivity before the session is closed.
- `warning` (duration): Time before expiration when TheHive returns a warning message.

local
""""""""
Creates a session if the provided login and password, or API key, is valid according to the local user database.

key
"""""""""
Authenticates HTTP requests using an API key provided in the authorization header. The format is "Authorization: Bearer xxx" (xxx is replaced by the API key). The key is searched using other authentication modules (currently, only the local authentication module can validate the key).

basic
"""""""""
Authenticates HTTP requests using the login and password provided in the authorization header using basic authentication format (Base64). Passwords are checked against the local user database.

Configuration parameters:

- `realm` (string): Name of the realm. Without this parameter, the browser does not ask to authenticate.

header
"""""""""
Authenticates HTTP requests using an HTTP header containing the user login. This is used to delegate authentication in a reverse proxy.

- `userHeader` (string): Name of the header that contains the user login.

ad
"""""""""
Uses Microsoft Active Directory to authenticate users.

- `winDomain` (string): Windows domain name (MYDOMAIN).
- `dnsDomain` (string): Windows domain name in DNS format (mydomain.local).
- `useSSL` (boolean): Use SSL to connect to domain controllers. The JVM trust store is used to validate the remote certificate (JAVA_OPTS="-Djavax.net.ssl.trustStore=/path/to/truststore.jks").
- `hosts` (list of string): Addresses of the domain controllers. If missing, `dnsDomain` is used.

ldap
"""""""""
Uses an LDAP directory server to authenticate users.

Configuration parameters:

- `bindDN` (string): DN of the service account in LDAP. This account is used to search the user.
- `bindPW` (string): Password of the service account.
- `baseDN` (string): DN where the users are located.
- `filter` (string): Filter used to search the user. "{0}" is replaced by the user login. A valid filter is:
  (&(uid={0})(objectClass=posixAccount)).
- `useSSL` (boolean): Use SSL to connect to the LDAP server. The JVM trust store is used to validate the
  remote certificate (JAVA_OPTS="-Djavax.net.ssl.trustStore=/path/to/truststore.jks").
- `hosts` (list of string): Addresses of the LDAP servers.

oauth2
"""""""
Authenticates the user using an external OAuth2 authenticator server.

Configuration parameters:

- `clientId` (string): Client ID in the OAuth2 server.
- `clientSecret` (string): Client secret in the OAuth2 server.
- `redirectUri` (string): URL of the TheHive OAuth2 page (.../api/ssoLogin).
- `responseType` (string): Type of the response. Currently only "code" is accepted.
- `grantType` (string): Type of the grant. Currently only "authorization_code" is accepted.
- `authorizationUrl` (string): URL of the OAuth2 server.
- `authorizationHeader` (string): Prefix of the authorization header to get user info (Bearer, token, ...).
- `tokenUrl` (string): Token URL of the OAuth2 server.
- `userUrl` (string): URL to get user information in the OAuth2 server.
- `scope` (list of string): List of scopes.
- `userIdField` (string): Field that contains the ID of the user in user info.
- `organisationField` (string, optional): Field that contains the organisation name in user info.
- `defaultOrganisation` (string, optional): Default organisation used to log in if not present in user info.



Keycloak example
.. code-block::
  {
      name: oauth2
      clientId: "CLIENT_ID"
      clientSecret: "CLIENT_SECRET" # or empty
      redirectUri: "http://energysoar/api/ssoLogin"
      responseType: "code"
      grantType: "authorization_code"
      authorizationUrl: "http://KEYCLOAK/auth/realms/TENANT/protocol/openid-connect/auth"
      authorizationHeader: "Bearer"
      tokenUrl: "http://KEYCLOAK/auth/realms/TENANT/protocol/openid-connect/token"
      userUrl: "http://KEYCLOAK/auth/realms/TENANT/protocol/openid-connect/userinfo"
      scope: ["openid", "email"]
      userIdField: "email"
    }

User autocreation
""""""""""""""""""
To allow users to log in without previously creating them, enable autocreation by adding
`user.autoCreateOnSso=true` to the top level of your configuration.


OAuth2/OpenID Connect
^^^^^^^^^^^^^^^^^^^^^

To enable authentication using OAuth2/OpenID Connect, edit the `application.conf` file and supply the values of `auth.oauth2` according to your environment. In addition, you need to supply:

- `auth.sso.attributes.login`: name of the attribute containing the OAuth2 user's login in retreived user info (mandatory)
- `auth.sso.attributes.name`: name of the attribute containing the OAuth2 user's name in retreived user info (mandatory)
- `auth.sso.attributes.groups`: name of the attribute containing the OAuth2 user's groups (mandatory using groups mappings)
- `auth.sso.attributes.roles`: name of the attribute containing the OAuth2 user's roles in retreived user info (mandatory using simple mapping)


Performance
^^^^^^^^^^^

In order to increase Energy SOAR Automation performance, a cache is configured to prevent
repetitive database solicitation. Cache retention time can be configured for
users and organizations (default is 5 minutes). If a user is updated, the cache is
automatically invalidated.

Analyzer Results
^^^^^^^^^^^^^^^^

Analyzer results (job reports) can also be cached. If an analyzer is executed against the same observable,
the previous report can be returned without re-executing the analyzer. The cache is used only
if the second job occurs within `cache.job` (the default is 10 minutes).

.. code-block::

    cache {
      job = 10 minutes
      user = 5 minutes
      organization = 5 minutes
    }


.. note::
    The global `cache.job` value can be overridden for each analyzer in the analyzer configuration Web dialog.

.. note::

   It is possible to bypass the cache altogether (for example to get extra fresh results) through the API as explained in the `API Guide <../08-0-0-API/08-0-0-API.html#run>`_ or by setting the cache to *Custom* in the Energy SOAR Automation UI for each analyzer and specifying `0` as the number of minutes.

Streaming (a.k.a The Flow)
^^^^^^^^^^^^^^^^^^^^^^^^^

The user interface is automatically updated when data is changed in the
back-end. To do this, the back-end sends events to all the connected front-ends.
The mechanism used to notify the front-end is called long polling and its
settings are:

 * `refresh` : when there is no notification, close the connection after this
 duration (the default is 1 minute).
 * `cache` : before polling a session must be created, in order to make sure no
 event is lost between two polls. If there is no poll during the cache setting,
 the session is destroyed (the default is 15 minutes).
 * `nextItemMaxWait`, `globalMaxWait` : when an event occurs, it is not
 immediately sent to the front-ends. The back-end waits nextItemMaxWait and up
 to globalMaxWait in case another event can be included in the notification.
 This mechanism saves many HTTP requests.

The default values are:


.. code-block::

    ### Streaming
    stream.longpolling {
      # Maximum time a stream request waits for new element
      refresh = 1m
      # Lifetime of the stream session without request
      cache = 15m
      nextItemMaxWait = 500ms
      globalMaxWait = 1s
    }

Entity Size Limit
^^^^^^^^^^^^^^^^^

The Play framework used by Energy SOAR Automation sets the HTTP body size limit to 100KB by
default for textual content (json, xml, text, form data) and 10MB for file
uploads. This could be too small in some cases so you may want to change it with
the following settings in the `application.conf` file:

.. code-block::

   ### Max textual content length
   play.http.parser.maxMemoryBuffer=1M
   ### Max file size
   play.http.parser.maxDiskBuffer=1G


.. note::
   If you are using a NGINX reverse proxy in front of Energy SOAR Automation, be aware that it doesn't distinguish between text data and a file upload. So, you should also set the `client_max_body_size` parameter in your NGINX server configuration to the highest value among the two: file upload and text size as defined in Energy SOAR Automation `application.conf` file.

HTTPS
^^^^^

Enable HTTPS directly on Energy SOAR Automation is not supported anymore. You must install a reverse proxy in front of Energy SOAR Automation.
Below an example of NGINX configuration:

.. code-block::

    server {
        listen 443 ssl;
        server_name automation.example.com;

        ssl_certificate         /etc/energysoar/ssl/energysoar-automation_cert.pem;
        ssl_certificate_key     /etc/energysoar/ssl/energysoar-automation_key.pem;

        proxy_connect_timeout   600;
        proxy_send_timeout      600;
        proxy_read_timeout      600;
        send_timeout            600;
        client_max_body_size    2G;
        proxy_buffering off;
        client_header_buffer_size 8k;

        location / {
            add_header                  Strict-Transport-Security "max-age=31536000; includeSubDomains";
            proxy_pass                  http://127.0.0.1:9001/;
            proxy_http_version          1.1;
            proxy_set_header Connection "";
        }
    }

EnergySOAR Base
-------

`secret.conf` file
^^^^^^^^^^^^^^^^^^

This file contains a secret that is used to define cookies used to manage the users session. As a result, one instance of EnergySOAR Base should use a unique secret key.

**Example**


.. code-block::

    ## Play secret key
    play.http.secret.key="dgngu325mbnbc39cxas4l5kb24503836y2vsvsg465989fbsvop9d09ds6df6"

.. warning::

   In the case of a cluster of Energy SOAR nodes, all nodes should have the same secret.conf file with the same secret key. The secret is used to generate user sessions.


License
^^^^^^^

**License path**

License path is set in configuration file ` /etc/energysoar/application.conf.d/license.conf`. By default it is ` license.path: "/etc/energysoar/"`.

Listen address & port
^^^^^^^^^^^^^^^^^^^^^

By default the application listens on all interfaces and port 9000. This is possible to specify listen address and ports with following parameters in the application.conf file:

.. code-block::

    http.address=127.0.0.1
    http.port=9000

Context
^^^^^^^

If you are using a reverse proxy, and you want to specify a location (ex: /energysoar), updating the configuration of Energy SOAR Base is also required

**Example**

.. code-block::

   play.http.context: "/energysoar"
   
   
Specific configuration for streams
^^^^^^^

If you are using a reverse proxy like Nginx, you might receive error popups with the following message: `StreamSrv 504 Gateway Time-Out`.

You need to change default setting for long polling refresh, Set `stream.longPolling.refresh` accordingly.

**Example**

.. code-block::

    stream.longPolling.refresh: 45 seconds

Manage content lengh
^^^^^^^^^^^^^^^^^^^^

Content length of text and files managed by the application are limited by default.


These values are set with default parameters:

.. code-block::

   # Max file size
   play.http.parser.maxDiskBuffer: 128MB


.. code-block::

   # Max textual content length
   play.http.parser.maxMemoryBuffer: 256kB
    
If you feel that these should be updated, edit /etc/energysoar/application.conf file and update these parameters accordingly.

.. tip::

   If you are using a NGINX reverse proxy in front of Energy SOAR, be aware that it doesn't distinguish between text data and a file upload.

   So, you should also set the client_max_body_size parameter in your NGINX server configuration to the highest value among the two: file upload and text size defined in EnergySOAR Base application.conf file.

Manage configuration files
^^^^^^^^^^^^^^^^^^^^^^^^^^

Energy SOAR Base uses HOCON as configuration file format. This format gives enough flexibility to structure and organise the configuration of Energy SOAR Base.

Energy SOAR Base is delivered with following files, in the folder `/etc/energysoar`:

`logback.xml` containing the log policy

`secret.conf` containing a secret key used to create sessions. This key should be unique per instance (in the case of a cluster, this key should be the same for all nodes of this cluster)
`application.conf` 

HOCON file format let you organise the configuration to have separate files for each purpose. It is the possible to create a /etc/energysoar/application.conf.d folder and have several files inside that will be included in the main file `/etc/energysoar/application.conf`.

At the end, the following configuration structure is possible:

.. code-block::

   /etc/energysoar
   |-- application.conf
   |-- application.conf.d
   |   |-- secret.conf
   |   |-- service.conf
   |   |-- database.conf
   |   |-- storage.conf
   |   |-- cluster.conf
   |   |-- authentication.conf
   |   |-- automation.conf
   |   |-- misp.conf
   |   |-- webhooks.conf
   |-- logback.xml


And the content of `/etc/energysoar/application.conf`:

.. code-block::

    ## Include Play secret key
    # More information on secret key at https://www.playframework.com/documentation/2.8.x/ApplicationSecret
    include "/etc/energysoar/application.conf.d/secret.conf"

    ## Service
    include "/etc/energysoar/application.conf.d/service.conf"

    ## Database
    include "/etc/energysoar/application.conf.d/database.conf"

    ## Storage
    include "/etc/energysoar/application.conf.d/storage.conf"

    ## Cluster
    include "/etc/energysoar/application.conf.d/cluster.conf"

    ## Authentication
    include "/etc/energysoar/application.conf.d/authentication.conf"

    ## Energy SOAR Automation
    include "/etc/energysoar/application.conf.d/automation.conf"

    ## MISP
    include "/etc/energysoar/application.conf.d/misp.conf"

    ## Webhooks
    include "/etc/energysoar/application.conf.d/webhooks.conf"

SSL
----

Energy SOAR instalation script create self-signed certificates. Those certificates are stored under `/etc/energysoar/ssl/` directory.

You can setup your own path in `/etc/nginx/conf.d/energysoar.conf`.

.. code-block::

    ssl_certificate     /etc/energysoar/ssl/nginx-selfsigned.crt;
    ssl_certificate_key /etc/energysoar/ssl/nginx-selfsigned.key;


Change system language
----------------------

To change a system language you need ovverride provided jar files.

.. code-block::

    cp -R EnergySOAR_*/jar/* /opt

To get your language pack please `contact with us <https://energysoar.com/#contact>`_.
