Role Name
=========

Completes initial virtual or physical Palo Alto firewall configuration. Configures the following information
DNS
NTP
timezone
Panorama (true or false)
Login Banner
Domain Name
Administrators
SNMP


Requirements
------------

Required Ansible Modules
panos_mgtconfig
panos_administrator
panos_snmp_profile
panos_snmp_v2c_server


Role Variables
--------------
panorama (true or false)
dns_server_primary
dns_server_secondary
panorama_primary
panorama_secondary
ntp_server_primary
ntp_server_secondary
timezone
domain
snmp_version
snmp_profile_name
admin_username
admin_password
superuser: (yes or no)
login_banner
snmp_profile
snmp_server_name
snmp_manager
snmp_community


Dependencies
------------

boto
boto3
python >= 2.6

Palo Galaxy Collection

Example Playbook
----------------
  vars_files:
    - "vars/palo_initial_vars.yml"
    - "vars/secrets.yml"
  roles:
    - role: PaloAltoNetworks.paloaltonetworks
    - initial_palo_setup

License
-------

Content used by license from Sirius for internal Sirius and customer use.
BSD

Author Information
------------------

Written by Sirius Engineering

Rich Mallory
Sirius
Senior Solutions Architect
rich.mallory@siriuscom.com