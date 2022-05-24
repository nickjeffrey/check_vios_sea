# check_vios_sea
nagios check for IBM VIOS Shared Ethernet Adapter / Virtual Network Bridge

Nagios plugin for determining status of Shared Ethernet Adapter (SEA) on IBM VIOS.  This check will alert if the primary SEA fails over to the standby SEA.

# Requirements
perl, SSH key pair auth between nagios server and VIOS 

# Configuration
Add a section similar to the following to the services.cfg file:
```
    define service {
       use                             generic-service
       hostgroup_name                  all_vios
       service_description             VIOS SEA
       check_command                   check_by_ssh!/usr/local/nagios/libexec/check_vios_sea
       }
```

# Output
```
VIOS SEA OK - Shared Ethernet Adapter state is normal
```
