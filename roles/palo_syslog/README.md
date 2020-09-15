Role Name
=========

Adds selected logging profiles, finds matching rules, and adds log forwarding profile.

Requirements
------------

PANOS module requirements

panos_log_forwarding_profile
panos_log_forwarding_profile_match_list
panos_security_rule_facts
panos_security_rule
panos_email_profile
panos_email_server
panos_syslog_profile
panos_syslog_server
panos_http_profile
panos_http_server
panos_snmp_profile
panos_snmp_v2c_server


Role Variables
--------------

All variables are static and should be set prior to execution
Leaving server profile name blank will result in that type of profile not being added

## Add Logging VARS - Name must be specified to be configured. Otherwise will be skipped
add_logging_profile: yes or no
enhanced_logging: true or false
log_forward_profile: Name of profile
match_list_name: 'forward_match_list'

# Syslog Vars
syslog_server_profile_name: Syslog server profile name
syslog_server_name: Syslog server name
syslog_server_ip: Syslog server IP address

# Email Vars
email_server_profile_name: Email server profile name
email_server_name: Email server name
email_from: From email address
email_to: To email address
email_gateway: Email gateway to use

# HTTP Vars
http_server_profile_name: HTTP profile name
http_server_name: HTTP server name
http_server_ip: HTTP server IP address
http_method: GET or PUT
http_username: HTTP username
http_password: HTTP password

#SNMP Vars
snmp_server_profile_name: SNMP server profile name
snmp_server_name: SNMP server name
snmp_manager_name: SNMP manager name
snmp_v2_community: SNMP v2 community (SNMPv3 can be supported as well)


log_type: logging type is one of traffic, threat, wildfire, url, data, gtp, tunnel, auth, sctp
filter_action: allow or deny
filter_zone: zone to log

address_object: Matching Palo Alto address object to filter, if blank log forward profile will be added to all security rules


Dependencies
------------

boto
boto3
python >= 2.6

Palo Galaxy Role

Example Playbook
----------------

Roles tasks

- { include_tasks: palo_add_syslog_server.yml, when: syslog_server_profile_name != '' } 
- { include_tasks: palo_add_email_server.yml, when: email_server_profile_name !=  '' }
- { include_tasks: palo_add_http_server.yml, when: http_server_profile_name !=  '' }
- { include_tasks: palo_add_snmp_server.yml, when: snmp_server_profile_name !=  '' } 
- { include_tasks: palo_find_matching_rules.yml, when: address_object !=  '' } 
- include_tasks: palo_add_logging.yml

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
