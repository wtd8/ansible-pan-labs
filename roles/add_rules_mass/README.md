Role Name
=========

Role reads a csv file located in the files directory of this role. File name is rules.csv by default. Adds both address objects and listed rules to security policy.

Requirements
------------

No specific requirements for this role other than Palo Alto collection requirements listed in the main README for collection

Role Variables
--------------

Located in common_var.yml
existing_rule: 'All'
location: 'before'
Specifies where to in policies to start rules

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: localhost
  connection: local
  gather_facts: False
  
  - role: PaloAltoNetworks.paloaltonetworks
  - palo_add_rules_mass
    
License
-------

Content used by permission of Sirius for internal Sirius and customer use.
Can be modified freely
BSD

Author Information
------------------

Rich Mallory
Sirius 
Senior Solution Architect
rich.mallory@siriuscom.com
