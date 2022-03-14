## Integrations
### Energy Logserver SIEM
This integration send alerts from Energy Logserver SIEM to Energy SOAR.

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
  hive_host: https://<Energy_SOAR_IP>/base
  hive_apikey: <api_key>
```

Restart the Alert service

```bash
# systemctl restart alert
```

**Alert rule configuration**

Configure details in the alert rule configuration

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

**Custom message**

By default Energy Logserver SIEM send a json with all alert fields. You can customize your message using markdown.

For example:

```
alert_text: "## Summary\r\n
\r\n\r\n
|  |  |\r\n
|---|---|\r\n
| IP | {} |\r\n
| Rule | {} |\r\n
\r\n\r\n
Log: `{}`\r\n
Full log: \r\n
```\r\n
{}\r\n
```\r\n
"
alert_text_args:
  - data.srcip
  - rule.description
  - full_log
  - previous_output
```

Preview:
![](markdown_example.png)