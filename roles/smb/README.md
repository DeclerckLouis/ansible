# Samba Server installation on a Raspberry Pi

An [Ansible](https://www.ansible.com) role to install/configure the [SMB](https://www.samba.org/) on a [Raspberry Pi](https://www.raspberrypi.org/).
  
Tested on [Debian GNU/Linux 11 (bullseye)](https://www.raspberrypi.com/software/)  
  
## How to use this role  
1. Ensure ssh connection to the pi.
2. Change the `smb_password` variable in `test.yml` to something else.
3. Change other variables if needed or desired.
4. Run `ansible-playbook test.yml`.
5. Enjoy your new samba server.

## Requirements

- active internet connection
- ssh connection to the pi
- When using a firewall, allow following traffic:
  - ssh (22)
  - dns (53)
  - http (80)
  - samba (139 & 445)
  
## Role default variables
- `smb_user`: user to create (default: `sambauser`)  
- `smb_password`: password for the user (default `Test123` (change this!))
- `smb_group`: group for the user (default: `sambagroup`)
- `smb_share`: name of the share (default: `share`)
- `smb_path`: path to the share (default: `/home/sambauser/share`)
- `smb_hosts_allow`: hosts that are allowed to access the share (default: `localhost`)
  
The `smb_user` and `smb_password` are used to create a new user and set a password for it.
This user is the owner of the share, and is meant for management purposes.  
  
The `smb_group` is the group the user is added to.  
**All users that need access to the share, need to be added to this group.**

The `smb_share`, `smb_path` and `smb_hosts_allow` are used in the `smb.conf` file.  
Instead of editing this file line per line, I added a template which gets loaded in.  
The template is the default configuration file, but with the new share added at the end.  
  
**warning:** The default configuration file is overwritten, so if you have any custom settings, make sure to add them to the template.  
  
*note:*
*All default variables can be overridden in the `vars/main.yml` file.*


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
