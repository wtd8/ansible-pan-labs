Role Name
=========

Sets up site-to-site VPN in AWS. When building VPN in AWS the Site-to-Site VPN may set in the pending state for sometime. The playbook will wait for 20 minutes. If it goes past 20 minutes playbook will timeout. If this occurs manually check the Site-to_site VPN in AWS and rerun playbook after VPN says "available". The playbook will detect and use the available VPN.


Requirements
------------

AWS Modules Required:
ec2_vpc_vgw
ec2_customer_gateway
ec2_vpc_vpn
ec2_vpc_route_table
ec2_vpc_vpn_info
ec2_vpc_route_table_info
ec2_vpc_vpn_info

Role Variables
--------------


Dependencies
------------

boto
boto3
python >= 2.6


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
