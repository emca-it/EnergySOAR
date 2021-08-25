# Energy SOAR installation guide #

## Install ##

Run as root in installation package directory
```bash
# ./install.sh -i
```

For a minimal architecture install
* TheHive
* Cortex
* Elasticsearch 7

Example installation
```bash
====> Do You wish to install the ENERGY SOAR TheHive, as well as the other TheHive dependencies? [y/n] y
[..]
====> Do You wish to install the ENERGY SOAR Cortex, as well as the other Cortex dependencies? [y/n] y
[..]
====> Do You wish to install the Elasticsearch 7? [y/n] y
[..]
====> Do You wish to initialize Cortex data? [y/n] y
[..]
====> Do You wish to initialize TheHive data? [y/n] y
[..]
```

Initialize Cortex data is needed to integrate with TheHive. During this step is created api user and configured in TheHive configuration.

Initialize TheHive data create sample users and test case/alert create.

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

