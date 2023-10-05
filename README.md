# A collection of my ansible playbooks and roles

##### This repo contains most of the playbooks and roles that i wrote for assignments, projects and other things.  
> I'm not a professional, so don't expect too much from this repo.  

## Requirements

- An **ansible controller** with ansible installed
- a node, **reachable over ssh from the controller** (with [pubkey authentication](https://www.ssh.com/ssh/copy-id)))
- usually, a working internet connection on the node

## Dependencies

- [ansible](https://https://www.ansible.com/)
- [openssh-server](https://www.openssh.com/)
- it probably also uses [python](https://www.python.org/) somewhere

## Tested using

- [kali linux 2020.1](https://) (as ansible controller)
- raspberry pi 3b+ (as node)

## Usage
### [Inventory](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)
After cloning this repo to the controller, making sure ansible is installed,  
and ensuring a working ssh connection to the node, start by making your own inventory file in the root of this repo.  

```bash
cd ansible
mkdir inventory
cd inventory
touch hosts
```  

Then, add the node to the inventory file, like so:  

```bash
[<group>]
<node> 
ansible_host=<ip> 
ansible_user=<user> 
ansible_ssh_private_key_file=<path to private key>
```

### [Playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)
After installing ansible, you can either run one of my playbooks using the following command:  

```bash
ansible-playbook <playbook>.yml
```  

Or you can go about creating your own playbook.  
A playbook should have the following structure:  

```yaml
---
- hosts: <group>
  become: yes # If you need root privileges
  roles:
    - <role> # If you want to use a role
  tasks:
    - name: <task> # Name of your task 
      <module>: <module options> # Module and options
```  


## Contributing

If you want to contribute to this repo, you can do so by forking the repo and making a pull request.  
Or just send me a message on [LinkedIn](https://www.linkedin.com/in/louis-declerck-student) or [GitHub](https://www.github.com/DeclerckLouis) :)  


## Author Information

Louis Declerck 2SNWB B
 - [GitHub](https://github.com/DeclerckLouis)
 - [LinkedIn](https://www.linkedin.com/in/louis-declerck-student)
 - [louis.declerck@student.howest.be](mailto:louis.declerck@student.howest.be)
