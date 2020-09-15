Role Name
=========

Palo Alto add security and NAT rules to allow access to AWS EC2 and/or other cloud based instances


Requirements
------------

Module Requirements
panos_security_rule
panos_nat_rule


Role Variables
--------------

NAT Rules:
    rule_name: -> NAT rule name
    source_zone: -> Generally internal zone
    destination_zone: -> Generally AWS zone or zone for tunnel
    source_ip: -> Internal IP ranges
    destination_ip: -> AWS range of addresses or single address
Security Rules:
    rule_name: -> Name the rule
    description: -> Variable
    source_zone: -> Generally internal zone
    destination_zone: -> Generally AWS zone or zone for tunnel
    application: ['any'] <- Can modify to specific service or application
    service: ['any']  ->  Can modify to specific service or application
    action: 'allow'  -> Must be allow
    location: 'top' -> Can modify location of rule to be added

Dependencies
------------

boto
boto3
python >= 2.6
Palo Galaxy Collection


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

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
