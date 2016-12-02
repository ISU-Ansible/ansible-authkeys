# Authorized Keys
Installs authorized_keys files for users.

## Variables

### Global Variables
No global variables are used in this role.

### Role Variables
- authkeys_public_keys
- authkeys_enabled

### User Variables
Users are encouraged to modify the role variables inside their group_vars folder.

## Tasks

### Description
This role does the following:

1. Creates the directory /\<user\>/.ssh
1. Creates the appropriate authorized key in /\<user\>/.ssh/authorized_keys

### Changed Files
- /\<user\>/.ssh/authorized_keys

### Installed Programs
No programs are installed

## Example

Authorized Keys playbook

    - name: Authorized Keys Ansible Playbook
      hosts: all
      user: root
      connection: smart

      vars:
        authkeys_public_keys:
          - username: 'root-authkey'
            destination: 'root'
            public_key: 'ssh-rsa root-key comment'
        authkeys_enabled:
          - 'root-authkey'

      roles:
        - authkeys
