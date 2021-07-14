Energy SOAR installation guilde
=============
Install 
-------------

Run as root in inallation package directory
.. prompt:: bash $

    ./install.sh -i


For a minimal architecture install
* TheHive
* Cortex
* Elasticsearch 7

After instalation check service status

.. prompt:: bash $

    systemctl status thehive cortex n8n

If services are runing then open Cortex URL - `http://{IP}:9001`.

Click Update Database button

.. figure:: /media/02-00-00-db_update.png
    :align: center
    
    Click Update Database button

Create administrator account

![Create administrator account](/media/02-00-01-create_admin.png)

Login into Cortex

Create and copy the administrator's account API key.

![Create API key Energy SOAR](/media/01-00-02-api_create.png)

Click Reveal

![Reveal the API key](/media/01-00-01-api_methods.png)

Copy the API key

![Copy the API key](/media/01-00-00-api_key.png)

Edit TheHive configuration

.. prompt:: bash $

    vi /etc/thehive/application.conf

Add Cortex bridge settings 

.. code-block:: yml

    cortex {
    # Check job update time intervalcortex
    refreshDelay = 5 seconds
    # Maximum number of successive errors before give up
    maxRetryOnError = 3
    # Check remote Cortex status time interval
    statusCheckInterval = 1 minute
    baseUrl: "http://127.0.0.1:9001",
    adminkey: "${ADMIN_API_KEY}"
    adminlogin: "admin"
    adminpassword: "admin"
    }

Restart TheHive

.. prompt:: bash $

    systemctl restart thehive

Login into TheHive
Create User with org-admin role.
`[create_user_img]`

Create and copy the user's account API key.

Login into user account
Click Manage Plugins on the top menu. It should open window in new tab.

Logout

Login as Cortex administrator's account.

Create and copy the user's account API key.

![Create API key Energy SOAR](/media/01-00-02-api_create.png)

Click Reveal

![Reveal the API key](/media/01-00-01-api_methods.png)

Copy the API key

![Copy the API key](/media/01-00-00-api_key.png)

Edit TheHive configuration

.. prompt:: bash $

    vi /etc/thehive/application.conf

Add Cortex plugin settings 

.. code-block:: yml

    play.modules.enabled += org.thp.thehive.connector.cortex.CortexModule
    cortex {
    servers = [
        {
            name = local
            url = "http://12.0.0.1:9001"
            auth {
                type = "bearer"
                key = "${USER_API_KEY}"
            }
            # HTTP client configuration (SSL and proxy)
            wsConfig {}
            # List TheHive organisation which can use this Cortex server. All ("*") by default
            includedTheHiveOrganisations = ["*"]
            # List TheHive organisation which cannot use this Cortex server. None by default
            # excludedTheHiveOrganisations = []
        }
    ]
    }
