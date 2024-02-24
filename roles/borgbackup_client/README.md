# Borgbackup Client

This role will configure borg and borgmatic on the (source) host and create a corresponding borg repository
on `borgbackup_target_host`.

This is a fork of [fsi-ansible/borgbackup_client](https://gitlab.fachschaften.org/fsi-ansible/borgbackup_client) that is changed to work with Hetzner Storage Boxes.

The `borgbackup_target_host` should have the Storage Space mounted.
`borgbackup_target_ip` can than be set to the Storage Space for direct backups.

## Required Variables
- `borgbackup_target_host`: Inventory hostname of the borgbackup server aka target host
- `borgbackup_key`: Encryption key. Not required when `borgbackup_use_encryption` is false. 
- `borgbackup_source_dirs`: List of directories to back up.
- `borgbackup_pool`: Absolute path to folder holding all borg repositories on the target host.
   Can be set on both source or target, target will take precedence. 

## Optional Variables
- `borgbackup_target_ip`: Overrides the IP address of the target host used for generating
   the borgmatic config on the source host. Can also contain a port (yes).
   Useful e.g. if the target has a different hostnamefrom the internet.  
   Example: `foo.example.com`
- `borgbackup_target_port`: Overrides ssh port
- `borgbackup_use_encryption`: Disables encryption if set to false. Defaults to true. 