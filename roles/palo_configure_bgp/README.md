Role Name
=========

Configures basic BGP on Palo Alto firewall

Requirements
------------
The below requirements are needed on the host that executes the Palo Alto modules.

boto
boto3
python >= 2.6

To execute role these modules are required:
 panos_bgp
 panos_bgp_peer_group
 panos_bgp_peer
 panos_bgp_redistribute
 panos_redistribution

Role Variables
--------------

bgp: -> Configure or do not configure BGP
bgp_peergroup_name: -> Peer group name
bgp_remote_name: -> Name of remote peer
bgp_redistribute: Routes to redistribute (To redistribute multiple routes use advanced BGP)
redistribution_profile: -> Local name of redistribute profile
redistribution_routes: Routes types to redistribute

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