## Configuration

### Cortex

As described in the section above, Analyzers can only be configured using the Web interface and their associated configuration is stored in the underlying Elasticsearch database. However, the Cortex appplication configuration is stored in the `/etc/cortex/application.conf` file.

#### Database

Cortex relies on the Elasticsearch 7.x search engine to store all persistent data.
Elasticsearch is not part of the Cortex package. It must be installed and configured
as a standalone instance which can be located on the same machine.

Three settings are required to connect to Elasticsearch:
 * the base name of the index
 * the name of the cluster
 * the address(es) and port(s) of the Elasticsearch instance

The default settings are:
```
### Elasticsearch
search {
  # Name of the index
  index = cortex
  # Name of the Elasticsearch cluster
  cluster = hive
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
```

If you use a different configuration, please make sure to modify the parameters accordingly in the
`application.conf` file.

If multiple Elasticsearch nodes are used as a cluster, addresses of the master
nodes must be used for the `search.host` setting. All cluster nodes must use the
same cluster name:

```
search {
    host = ["node1:9300", "node2:9300"]
   ...
```

Cortex uses the [TCP transport](https://www.elastic.co/guide/en/elasticsearch/reference/5.6/modules-network.html#_transport_and_http_protocols)
port (9300/tcp by default). Cortex cannot use the HTTP transport as of this writing (9200/tcp).

Cortex creates specific index schema (mapping) versions in Elasticsearch. Version numbers are
appended to the index base name (the 8th version of the schema uses the index
`cortex_8` if `search.index = cortex`). When too many documents are requested, it uses the
[scroll](https://www.elastic.co/guide/en/elasticsearch/reference/5.6/search-request-scroll.html)
feature: the results are retrieved through pagination. You can specify the size
of the page (`search.pagesize`) and how long pages are kept in Elasticsearch
(`search.keepalive`) before purging.

XPack and SearchGuard are optional and exclusive. If Cortex finds a valid configuration for XPack, SearchGuard configuration is ignored.

#### Analyzers and Responders
Cortex is able to run workers (analyzers and responders) installed locally or available as Docker image. Settings `analyzer.urls` and in `responder.urls` list paths or urls where Cortex looks for analyzers and responders. Theses settings accept:
1. a path to a directory that Cortex scans to locate workers
1. a path or an URL to a JSON file containing a JSON array of worker definitions

Worker definition is a JSON object that describe the worker, how to configure it and how to run it. If it contains a field "command", worker can be run using process runner (i.e. the command is executed). If it contains a field "dockerImage", worker can be run using docker runner (i.e. a container based on this image is started). If it contains both, the runner is chosen according to `job.runners` settings (`[docker, process]` by default).

For security reason, if worker definitions fetched from remote url (http/https) contain command, they are ignored.

You can control the number of simultaneous jobs that Cortex executes in parallel using the
`analyzer.fork-join-executor` configuration item. The value depends on the
number of CPU cores (`parallelism-factor` * nbCores), with a minimum
(`parallelism-min`) and a maximum (`parallelism-max`).

Similar settings can also be applied to responders.

```
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
```

#### Authentication
Like TheHive, Cortex supports local, LDAP, Active Directory (AD), X.509 SSO and/or API keys for authentication and OAuth2.

Please note that API keys can only be used to interact with the Cortex API (for example when TheHive is interfaced with a Cortex instance, it must use an API key to authenticate to it). API keys cannot be used to authenticate to the Web UI. By default, Cortex relies on local credentials stored in Elasticsearch.

Authentication methods are stored in the `auth.provider` parameter, which is
multi-valued. When a user logs in, each authentication method is tried in order
until one succeeds. If no authentication method works, an error is returned and
the user cannot log in.

The default values within the configuration file are:
```
auth {
	# "provider" parameter contains authentication provider. It can be multi-valued (useful for migration)
	# available auth types are:
	# services.LocalAuthSrv : passwords are stored in user entity (in Elasticsearch). No configuration is required.
	# ad : use ActiveDirectory to authenticate users. Configuration is under "auth.ad" key
	# ldap : use LDAP to authenticate users. Configuration is under "auth.ldap" key
  # oauth2 : use OAuth/OIDC to authenticate users. Configuration is under "auth.oauth2" and "auth.sso" keys
	provider = [local]

  # By default, basic authentication is disabled. You can enable it by setting "method.basic" to true.
  method.basic = false

	ad {
		# The name of the Microsoft Windows domain using the DNS format. This parameter is required.
		#domainFQDN = "mydomain.local"

    # Optionally you can specify the host names of the domain controllers. If not set, Cortex uses "domainFQDN".
    #serverNames = [ad1.mydomain.local, ad2.mydomain.local]

		# The Microsoft Windows domain name using the short format. This parameter is required.
		#domainName = "MYDOMAIN"

		# Use SSL to connect to the domain controller(s).
		#useSSL = true
	}

	ldap {
		# LDAP server name or address. Port can be specified (host:port). This parameter is required.
		#serverName = "ldap.mydomain.local:389"

    # If you have multiple ldap servers, use the multi-valued settings.
    #serverNames = [ldap1.mydomain.local, ldap2.mydomain.local]

		# Use SSL to connect to directory server
		#useSSL = true

		# Account to use to bind on LDAP server. This parameter is required.
		#bindDN = "cn=cortex,ou=services,dc=mydomain,dc=local"

		# Password of the binding account. This parameter is required.
		#bindPW = "***secret*password***"

		# Base DN to search users. This parameter is required.
		#baseDN = "ou=users,dc=mydomain,dc=local"

		# Filter to search user {0} is replaced by user name. This parameter is required.
		#filter = "(cn={0})"
	}

  oauth2 {
    # URL of the authorization server
    #clientId = "client-id"
    #clientSecret = "client-secret"
    #redirectUri = "https://my-cortex-instance.example/api/ssoLogin"
    #responseType = "code"
    #grantType = "authorization_code"

    # URL from where to get the access token
    #authorizationUrl = "https://auth-site.com/OAuth/Authorize"
    #tokenUrl = "https://auth-site.com/OAuth/Token"

    # The endpoint from which to obtain user details using the OAuth token, after successful login
    #userUrl = "https://auth-site.com/api/User"
    #scope = ["openid profile"]
  }

  # Single-Sign On
  sso {
    # Autocreate user in database?
    #autocreate = false

    # Autoupdate its profile and roles?
    #autoupdate = false

    # Autologin user using SSO?
    #autologin = false

    # Name of mapping class from user resource to backend user ('simple' or 'group')
    #mapper = group
    #attributes {
    #  login = "user"
    #  name = "name"
    #  groups = "groups"
    #  organization = "org"
    #}
    #defaultRoles = ["read"]
    #defaultOrganization = "csirt"
    #groups {
    #  # URL to retreive groups (leave empty if you are using OIDC)
    #  #url = "https://auth-site.com/api/Groups"
    #  # Group mappings, you can have multiple roles for each group: they are merged
    #  mappings {
    #    admin-profile-name = ["admin"]
    #    editor-profile-name = ["write"]
    #    reader-profile-name = ["read"]
    #  }
    #}

    #mapper = simple
    #attributes {
    #  login = "user"
    #  name = "name"
    #  roles = "roles"
    #  organization = "org"
    #}
    #defaultRoles = ["read"]
    #defaultOrganization = "csirt"
  }

}

### Maximum time between two requests without requesting authentication
session {
  warning = 5m
  inactivity = 1h
}
```

##### OAuth2/OpenID Connect

To enable authentication using OAuth2/OpenID Connect, edit the `application.conf` file and supply the values of `auth.oauth2` according to your environment. In addition, you need to supply:

- `auth.sso.attributes.login`: name of the attribute containing the OAuth2 user's login in retreived user info (mandatory)
- `auth.sso.attributes.name`: name of the attribute containing the OAuth2 user's name in retreived user info (mandatory)
- `auth.sso.attributes.groups`: name of the attribute containing the OAuth2 user's groups (mandatory using groups mappings)
- `auth.sso.attributes.roles`: name of the attribute containing the OAuth2 user's roles in retreived user info (mandatory using simple mapping)

###### Important notes


Authenticate the user using an external OAuth2 authenticator server. The configuration is:

- clientId (string) client ID in the OAuth2 server.
- clientSecret (string) client secret in the OAuth2 server.
- redirectUri (string) the url of TheHive AOuth2 page (.../api/ssoLogin).
- responseType (string) type of the response. Currently only "code" is accepted.
- grantType (string) type of the grant. Currently only "authorization_code" is accepted.
- authorizationUrl (string) the url of the OAuth2 server.
- authorizationHeader (string) prefix of the authorization header to get user info: Bearer, token, ...
- tokenUrl (string) the token url of the OAuth2 server.
- userUrl (string) the url to get user information in OAuth2 server.
- scope (list of string) list of scope.

**Example**

```
auth {
		
  provider = [local, oauth2]

  [..]

  sso {
    autocreate: false
    autoupdate: false
    mapper: "simple"
    attributes {
      login: "login"
      name: "name"
      roles: "role"
    }
    defaultRoles: ["read", "analyze"]
    defaultOrganization: "demo"
  }  
  oauth2 {
    name: oauth2
    clientId: "Client_ID"
    clientSecret: "Client_ID"
    redirectUri: "http://localhost:9001/api/ssoLogin"
    responseType: code
    grantType: "authorization_code"
    authorizationUrl: "https://github.com/login/oauth/authorize"
    authorizationHeader: "token"
    tokenUrl: "https://github.com/login/oauth/access_token"
    userUrl: "https://api.github.com/user"
    scope: ["user"]
  }

  [..]	
}
```


#### Cache
##### Performance
In order to increase Cortex performance, a cache is configured to prevent
repetitive database solicitation. Cache retention time can be configured for
users and organizations (default is 5 minutes). If a user is updated, the cache is
automatically invalidated.

##### Analyzer Results
Analyzer results (job reports) can also be cached. If an analyzer is executed against the same observable,
the previous report can be returned without re-executing the analyzer. The cache is used only
if the second job occurs within `cache.job` (the default is 10 minutes).
```
cache {
  job = 10 minutes
  user = 5 minutes
  organization = 5 minutes
}
```
**Note**: the global `cache.job` value can be overridden for each analyzer in the analyzer configuration Web dialog.

**Note**: it is possible to bypass the cache altogether (for example to get extra fresh results) through the API as explained in the [API Guide](../api/api-guide.md#run) or by setting the cache to *Custom* in the Cortex UI for each analyzer and specifying `0` as the number of minutes.

#### Streaming (a.k.a The Flow)
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
```
### Streaming
stream.longpolling {
  # Maximum time a stream request waits for new element
  refresh = 1m
  # Lifetime of the stream session without request
  cache = 15m
  nextItemMaxWait = 500ms
  globalMaxWait = 1s
}
```

##### Entity Size Limit
The Play framework used by Cortex sets the HTTP body size limit to 100KB by
default for textual content (json, xml, text, form data) and 10MB for file
uploads. This could be too small in some cases so you may want to change it with
the following settings in the `application.conf` file:

```
### Max textual content length
play.http.parser.maxMemoryBuffer=1M
### Max file size
play.http.parser.maxDiskBuffer=1G
```

**Note**: if you are using a NGINX reverse proxy in front of Cortex, be aware
that it doesn't distinguish between text data and a file upload. So, you should
also set the `client_max_body_size` parameter in your NGINX server configuration
to the highest value among the two: file upload and text size as defined in Cortex
`application.conf` file.

#### HTTPS
Enable HTTPS directly on Cortex is not supported anymore. You must install a reverse proxy in front of Cortex.
Below an example of NGINX configuration:
```
	server {
			listen 443 ssl;
			server_name cortex.example.com;

			ssl_certificate			ssl/cortex_cert.pem;
			ssl_certificate_key		ssl/cortex_key.pem;

			proxy_connect_timeout   600;
			proxy_send_timeout      600;
			proxy_read_timeout      600;
			send_timeout            600;
			client_max_body_size    2G;
			proxy_buffering off;
			client_header_buffer_size 8k;

			location / {
					add_header				          Strict-Transport-Security "max-age=31536000; includeSubDomains";
					proxy_pass                  http://127.0.0.1:9001/;
					proxy_http_version          1.1;
					proxy_set_header Connection "";
			}
	}
```

### TheHive

#### `secret.conf` file
This file contains a secret that is used to define cookies used to manage the users session. As a result, one instance of TheHive should use a unique secret key.

**Example**
```
## Play secret key
play.http.secret.key="dgngu325mbnbc39cxas4l5kb24503836y2vsvsg465989fbsvop9d09ds6df6"
```

**Warrning**

In the case of a cluster of Energy SOAR nodes, all nodes should have the same secret.conf file with the same secret key. The secret is used to generate user sessions.

#### Service

##### License

###### License path
License path is stored in configuration file ` /etc/thehive/application.conf.d/license.conf`. By default it is ` license.path: "/etc/thehive/"`.

##### Listen address & port
By default the application listens on all interfaces and port 9000. This is possible to specify listen address and ports with following parameters in the application.conf file:

```
http.address=127.0.0.1
http.port=9000
```

##### Context
If you are using a reverse proxy, and you want to specify a location (ex: /thehive), updating the configuration of TheHive is also required

**Example**

play.http.context: "/thehive"
Specific configuration for streams#
If you are using a reverse proxy like Nginx, you might receive error popups with the following message: StreamSrv 504 Gateway Time-Out.

You need to change default setting for long polling refresh, Set stream.longPolling.refresh accordingly.

**Example**
```
stream.longPolling.refresh: 45 seconds
```

##### Manage content lengh
Content length of text and files managed by the application are limited by default.


These values are set with default parameters:

```
# Max file size
play.http.parser.maxDiskBuffer: 128MB
```
```
# Max textual content length
play.http.parser.maxMemoryBuffer: 256kB
If you feel that these should be updated, edit /etc/thehive/application.conf file and update these parameters accordingly.
```

**Tip**

if you are using a NGINX reverse proxy in front of Energy SOAR, be aware that it doesn't distinguish between text data and a file upload.

So, you should also set the client_max_body_size parameter in your NGINX server configuration to the highest value among the two: file upload and text size defined in TheHive application.conf file.

#### Manage configuration files
Energy SOAR uses HOCON as configuration file format. This format gives enough flexibility to structure and organise the configuration of Energy SOAR.

TheHive is delivered with following files, in the folder `/etc/thehive`:

`logback.xml` containing the log policy

`secret.conf` containing a secret key used to create sessions. This key should be unique per instance (in the case of a cluster, this key should be the same for all nodes of this cluster)
`application.conf` 

HOCON file format let you organise the configuration to have separate files for each purpose. It is the possible to create a /etc/thehive/application.conf.d folder and have several files inside that will be included in the main file `/etc/thehive/application.conf`.

At the end, the following configuration structure is possible:

```
/etc/thehive
|-- application.conf
|-- application.conf.d
|   |-- secret.conf
|   |-- service.conf
|   |-- database.conf
|   |-- storage.conf
|   |-- cluster.conf
|   |-- authentication.conf
|   |-- cortex.conf
|   |-- misp.conf
|   `-- webhooks.conf
`-- logback.xml
```

And the content of `/etc/thehive/application.conf`:
```
## Include Play secret key
# More information on secret key at https://www.playframework.com/documentation/2.8.x/ApplicationSecret
include "/etc/thehive/application.conf.d/secret.conf"

## Service
include "/etc/thehive/application.conf.d/service.conf"

## Database
include "/etc/thehive/application.conf.d/database.conf"

## Storage
include "/etc/thehive/application.conf.d/storage.conf"

## Cluster
include "/etc/thehive/application.conf.d/cluster.conf"

## Authentication
include "/etc/thehive/application.conf.d/authentication.conf"

## Cortex
include "/etc/thehive/application.conf.d/cortex.conf"

## MISP
include "/etc/thehive/application.conf.d/misp.conf"

## Webhooks
include "/etc/thehive/application.conf.d/webhooks.conf"
```

### SSL
Energy SOAR instalation script create self-signed certificates. Those certificates are stored under `/etc/thehive/ssl/` directory.

You can setup your own path in `/etc/nginx/conf.d/energysoar.conf`.

```
    ssl_certificate     /etc/thehive/ssl/nginx-selfsigned.crt;
    ssl_certificate_key /etc/thehive/ssl/nginx-selfsigned.key;
```
