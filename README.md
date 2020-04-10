# mylab-node-ansible
Ansible roles to configure an already provisioned node (server)


## Installing

```
# cd /etc/ansible/roles
# git clone https://github.com/troppens/mylab-node-ansible.git mylab_node
```


## Usage

Use desired roles in your playbook.

```
- hosts: 10.1.1.20
  roles:
    - mylab_node/ssh
    - mylab_node/chrony
    - mylab_node/timezone
    - mylab_node/git
```


## Roles

### mylab_node/ssh
* Disable strict host key checking

### mylab_node/chrony
* Allow to step clock (good for virtual machines) 

### mylabnode/timezone
* Set timezone Europe/Berlin (hard coded) 

### mylab_node/git
* Install Git packages
