# Web app installation (cacti)

An [Ansible](https://www.ansible.com) role to install/configure [cacti](https://cacti.net)
Tested on [Ubuntu server 20.04.3 LTS](https://ubuntu.com/download/server)

## Requirements

- A good mood
- active internet connection
- ssh connection 
- apt package manager (default in ubuntu)

## Dependencies

None

## Example Playbook

```yaml
- hosts: ubuntus
  vars:
  roles:
    - web-application
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


## Process of making this role

1. I started making a playbook based on installation documentation from last years' SimLab assignment to install cacti on raspberry pi.
2. I watched more Jeff Geerling videos and read courseware, realised that a role is not a playbook, and adjusted what i had.
3. Found out i didn't have enough disk space on the pi to install cacti (after a few hours debugging why it wouldn't work)
4. Found an installation manual from cacti's support page, made for rpm based distro's, once again, adjusted what i had
5. It didn't work
6. Found a manual on openSUSE's wiki SPECIFICALLY to install cacti (without git and tarballs)
7. OpenSUSE apache config files were all over the place, didn't match with guide
8. Did the entire thing again for ubuntu
9. Finished