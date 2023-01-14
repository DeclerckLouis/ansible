# autofs

Ansible role to install and configure autofs.

## Requirements

None.

## Role Variables

Many. See defaults/main.yml

## Dependencies

None.

## Install this roles as submodule of an existing GIT repository

`git submodule add https://git.sekoya.org/mb/autofs.git roles/autofs`

## Example Playbook

    - hosts: servers
      roles:
         - autofs


    - hosts: servers
      roles:
         - role: autofs
           when: autofs_mounts is defined


    - hosts: servers
      roles:
         - { role: autofs, when: autofs_mounts is defined }

## License

GPLv3

## Author Information

http://www.sekoya.org
