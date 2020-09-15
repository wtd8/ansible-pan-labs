Role Name
=========

Collects information from AWS Site-to-Site VPN in order to configure the Palo Alto firewall

Requirements
------------

Required Modules:
ec2_vpc_vpn_info
xml_output

Role Variables
--------------

aws_region -> Used from aws_vars

The following variables are generate dynamically and used in the palo_site_to_site playbook
vpn_connection_id
aws_peer_ip_value
tunnel_ip
ike_dh_group
ike_authentication
ike_encryption
ike_lifetime
ike_preshared_key
ipsec_encryption


Dependencies
------------

boto
boto3
python >= 2.6

Palo Galaxy Collection


Example Playbook
----------------

Role used with AWS VPN build

  roles:
    - role: PaloAltoNetworks.paloaltonetworks
    - aws_initial_checks
    - { role: aws_vpn_setup, when: aws_vpn_state | length == 0 }
    - aws_vpn_info
    - palo_site_site_vpn
    - { role: palo_configure_bgp, when: bgp == 'true' } 
    - palo_add_rules


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
