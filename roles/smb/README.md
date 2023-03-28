# Samba Server installation on a Raspberry Pi

An [Ansible](https://www.ansible.com) role to install/configure the [SMB](https://www.samba.org/) on a [Raspberry Pi](https://www.raspberrypi.org/).
  
Tested on [Debian GNU/Linux 11 (bullseye)](https://www.raspberrypi.com/software/)  

## Requirements

- active internet connection
- ssh connection to the pi
- When using a firewall, allow following traffic:
  - ssh (22)
  - dns (53)
  - http (80)
  - samba (139 & 445)
  
## Role Variables
- `smb_user`: user to create (default: `sambauser`)
- `smb_password`: password for the user (default `Test123` (change this!))
- `smb_share`: name of the share (default: `share`)
- `smb_path`: path to the share (default: `/home/sambauser/share`)
- `smb_hosts_allow`: hosts that are allowed to access the share (default: `localhost`)


## Example Playbook

```yaml
- hosts: rasperrypi
  vars:
  roles:
    - smb
  tasks:
  become: true
```

## License

MIT

## Author Information

Louis Declerck 2SNWB B
 - [github](https://github.com/DeclerckLouis)
 - [linkedin](https://www.linkedin.com/in/louis-declerck-student)
 - [louis.declerck@student.howest.be](mailto:louis.declerck@student.howest.be)
