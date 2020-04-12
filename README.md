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
  vars:
    -mylab_node_tasks:
      -ssh
      -chrony
      -timezone
      -etc_hosts
      -git
  roles:
    - mylab_node/ssh
    - mylab_node/chrony
    - mylab_node/timezone
    - mylab_node/etc_hosts
    - mylab_node/git
```


## Variables

### mylab_node_tasks
* Specify which entities to configure


## Roles

### mylab_node/ssh
* Disable strict host key checking

### mylab_node/chrony
* Allow to step clock (good for virtual machines) 

### mylabnode/timezone
* Set timezone Europe/Berlin (hard coded) 

### mylab_node/etc_hosts
* Copy local /mylab/config/etc_hosts to /etc/hosts

### mylab_node/git
* Install Git packages
