## Configuration

### `secret.conf` file
This file contains a secret that is used to define cookies used to manage the users session. As a result, one instance of TheHive should use a unique secret key.

**Example**
```
## Play secret key
play.http.secret.key="dgngu325mbnbc39cxas4l5kb24503836y2vsvsg465989fbsvop9d09ds6df6"
```

**Warrning**

In the case of a cluster of Energy SOAR nodes, all nodes should have the same secret.conf file with the same secret key. The secret is used to generate user sessions.

### Service

#### Listen address & port
By default the application listens on all interfaces and port 9000. This is possible to specify listen address and ports with following parameters in the application.conf file:

```
http.address=127.0.0.1
http.port=9000
```

#### Context
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

#### Manage content lengh
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

### Manage configuration files
Energy SOAR uses HOCON as configuration file format. This format gives enough flexibility to structure and organise the configuration of Energy SOAR.

#### TheHive
TheHive is delivered with following files, in the folder `/etc/thehive`:

logback.xml containing the log policy
secret.conf containing a secret key used to create sessions. This key should be unique per instance (in the case of a cluster, this key should be the same for all nodes of this cluster)
application.conf
HOCON file format let you organise the configuration to have separate files for each purpose. It is the possible to create a /etc/thehive/application.conf.d folder and have several files inside that will be included in the main file /etc/thehive/application.conf.

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