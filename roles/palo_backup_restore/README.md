Role Name
=========

Backup and/or restore Palo Alto firewall configuration

Requirements
------------

Module requirements for backup/restore

panos_import
panos_loadcfg

Ensure that the path set for configuration backup is writeable by awx user otherwise backup and job will fail
This is set by backup_path variable in backup_restore_vars.yml

Role Variables
--------------

panos_import, panos_loadcfg do not use provider login options

username: -> Login username for Palo Alto Firewall
password: Login password for Palo Alto Firewall
backup_path : roles/palo_backup_restore/files/ -> where the backup files will be stored
backup_configuration: -> true or false
palo_alto: -> IP address of host to backup
restore_file: -> Name of file to restore. Playbook will look in roles/palo_backup_restore/files/ by default

Backup files are store with firewall name and year, month, day, hour, and minute in filename in XML format

Dependencies
------------

boto
boto3
python >= 2.6

Palo Galaxy Role

Example Playbook
----------------

  vars_files:
    - "vars/backup_restore_vars.yml"
    - "vars/secrets.yml"
  roles:
    - palo_backup_restore
    
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
