# Energy SOAR installation guide #

## Install ##

Supported OSes:
- Red Hat Linux 7
- Red Hat Linux 8
- Centos Linux/Stream 7
- Centos Linux/Stream 8
- Oracle Linux 8

Run as root in installation package directory

For non-interactive (recommended):
```bash
# ./install.sh -n
```

For interactive:
```bash
# ./install.sh -i
```

For a minimal architecture install
* TheHive
* Cortex
* Elasticsearch 7
* Cassandra 4

Example *interactive* installation
```bash
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
```

Initialize Cortex data is needed to integrate with TheHive. During this step is created api user and configured in TheHive configuration.

Initialize TheHive data:
- create sample users
- create sample case/alert
- import Analyzer templates
- import MISP Taxonomoies
- configure Cortex plugin

Sample users

<table style="border: 1px solid #e1e4e5;">
    <tr style="border: 1px solid #e1e4e5;">
        <th style="border: 1px solid #e1e4e5;">User</th>
        <th style="border: 1px solid #e1e4e5;">Password</th>
    </tr>
    <tr style="border: 1px solid #e1e4e5;">
        <td style="border: 1px solid #e1e4e5;">admin</td>
        <td style="border: 1px solid #e1e4e5;">secret</td>
    </tr>
    <tr style="border: 1px solid #e1e4e5;">
        <td style="border: 1px solid #e1e4e5;">socadmin</td>
        <td style="border: 1px solid #e1e4e5;">socadmin</td>
    </tr>
    <tr style="border: 1px solid #e1e4e5;">
        <td style="border: 1px solid #e1e4e5;">socuser</td>
        <td style="border: 1px solid #e1e4e5;">socuser</td>
    </tr>
    <tr style="border: 1px solid #e1e4e5;">
        <td style="border: 1px solid #e1e4e5;">socro</td>
        <td style="border: 1px solid #e1e4e5;">socro</td>
    </tr>
</table>

