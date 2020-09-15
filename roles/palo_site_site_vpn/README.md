Role Name
=========

Role configures Palo Alto firewall for VPN connectivity based on automated discovery of remote IPSec/IKE attributes

Requirements
------------

The below requirements are needed on the host that executes the Palo Alto modules.

boto
boto3
python >= 2.6

To execute role these modules are required:
panos_ike_crypto_profile
panos_ike_gateway
panos_ipsec_profile
panos_tunnel
panos_ipsec_tunne

Role Variables
--------------

Example Static Variables
ike_interface: 'ethernet1/2'
tunnel_if_name: 'tunnel.100'
tunnel_mtu: '1427'
vr_name: 'default'
destination_zone_name: 'AWS'
tunnel_name: 'AWS_Tunnel_1'

All variables not listed above are pulled from querying AWS tunnel configuration. 

provider: -> Set in secrets.yml
state: -> Absent or Present
dh_group: -> Dynamically from AWS
authentication: -> Dynamically from AWS
encryption: -> Dynamically from AWS
lifetime_seconds:-> Dynamically from AWS
interface: -> Dynamically from AWS
peer_ip_value: -> Dynamically from AWS
pre_shared_key: -> Dynamically from AWS
ikev2_crypto_profile: -> Dynamically from AWS
esp_authentication: -> Dynamically from AWS
esp_encryption: -> Dynamically from AWS
if_name: -> Palo Alto Interface
ip: -> Dynamically from AWS
mtu:  -> Dynamically from AWS
vr_name: -> Palo Alto virtual router name
name: -> Name of VPN Tunnel on Palo Alto
tunnel_interface: -> tunnel.xxx format


Dependencies
------------

boto
boto3
python >= 2.6

Palo Galaxy Collection

Example Playbook
----------------

  roles:
    - palo_site_site_vpn

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
