## Integrations
### Energy Logserver SIEM

**Create API key**

Create new (non-admin) user and generate API key.

![](/media/01-00-02-api_create.png)

Click Reveal

![](/media/01-00-01-api_methods.png)

Copy the API key

![](/media/01-00-00-api_key.png)

**Edit Alert**

Add configuration in the Alert service config.

```bash
# vi /opt/alert/config.yaml
```

```yaml
hive_connection:
  hive_host: <url>
  hive_port: 9000
  hive_apikey: <api_key>
```

Restart the Alert service

```bash
# systemctl restart alert
```

**Alert rule configuration**

Add in the alert rule configuration

```yaml
alert: hivealerter
hive_alert_config_type: classic
hive_alert_config:
  type: "AUDIT"
  source: "SIEM"
  severity: 2
  tags: ["ELS","audit"]
  tlp: 3
  status: "New"
  follow: True
hive_observable_data_mapping:
 - ip: "{match[src_ip]}"
   message: "Source IP address"
   tags: ["src: SIEM"]
 - domain: "{match[username]}"
   message: "Audit username"
   tags: ["src: SIEM"]
```
- 