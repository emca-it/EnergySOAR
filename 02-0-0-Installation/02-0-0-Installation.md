# Energy SOAR installation guide #

## Install ##

Run as root in inallation package directory
```bash
# ./install.sh -i
```

For a minimal architecture install
* TheHive
* Cortex
* Elasticsearch 7

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
```

Initialize Cortex data is needed to integrate with TheHive.

Initialize TheHive data create sample users and test case/alert create.