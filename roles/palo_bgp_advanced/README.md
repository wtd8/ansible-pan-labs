Role Name
=========

Configures advanced BGP on Palo Alto firewall with more advanced features than standard BGP playbook.
 

Requirements
------------

panos_bgp
panos_bgp_peer_group
panos_bgp_peer
panos_redistribution
panos_bgp_redistribute

Role Variables
--------------

state: -> Present, Absent, Disabled, Enabled
bgp_peergroup_name: -> Name of Displayed Peergroup in Palo Alto
redistribution_profile: -> Name of redistribution profile
redistribution_routes: -> List any routes to redistribute. Any of 'static', 'connect', 'rip', 'ospf', or 'bgp'.
redistribution_filter: 
  - Prefix 1 to redistribute
  - Prefix 2 to redistribute
  - Prefix 3 to redistribute
  - <etc>
allow_redist_default_route: -> Allow redistribute default route to BGP.
as_format:  -> AS format '2-byte'/'4-byte'
enforce_first_as: -> Enforce First AS for EBGP.
graceful_restart_enable: -> Enable graceful restart.
install_route: -> Populate BGP learned route to global route table.
reject_default_route: -> Reject default route.
local_bgprouter_id:  ->  Local IP address to use for BGP
local_bgp_as:  ->  Local AS assigned to Palo Alto
bgp_peer_as:  ->  Remote AS number
peering_type:  -> eBGP or iBGP
local_interface:  -> Interface to allow BGP
local_ip:  ->  Local BGP peering IP
vr_name:  -> Name of Palo Alto virtual router
bgp_peers:
  - bgp_remote_name:  -> Name of peer 1
    bgp_peer_ip:
       -> IP address of peer 1
  - bgp_remote_name:  -> Name of peer 2
    bgp_peer_ip:
       -> IP address of peer 2

Dependencies
------------

Requirements listed in root README file. 

Example Playbook
----------------

- hosts: localhost
  connection: local
  gather_facts: False
  vars_files:
    - "vars/common_vars.yml"
    - "vars/secrets.yml"
    - "vars/advanced_bgp_vars.yml"
  roles:
    - role: PaloAltoNetworks.paloaltonetworks
    - palo_backup_restore_config
    
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
