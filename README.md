# Authorized Keys
Installs authorized_keys files for users.

## Variables

### Global Variables
No global variables are used in this role.

### Role Variables
- root_authkeys_source_dir, or
- root_authkeys

### User Variables
Users are encouraged to modify the role variables inside their group_vars folder.

## Tasks

### Description
This role does the following:

1. Creates the directory /root/.ssh
1. Copies {{ root_authkeys }} from {{ root_authkeys_source_dir }} to /root/.ssh/authorized_keys


### Changed Files
- /root/.ssh/authorized_keys

### Installed Programs
No programs are installed

## Example

Authorized Keys playbook

    - name: Authorized Keys Ansible Playbook
      hosts: all
      user: root
      connection: smart

      roles:
        - noipv6
