# mylab-node-ansible
Ansible roles to configure an already provisioned node (server)


## Installing

```
# cd /etc/ansible/roles
# git clone https://github.com/troppens/mylab-node-ansible.git mylab_node
```


## Usage

Add entities to configure to variable `mylab_node_tasks`.

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
    - mylab_node
```


## Variables

### mylab_node_tasks
* Specify which entities to configure


## Entities

### ssh
* Disable strict host key checking

### chronyd
* Allow to step clock (good for virtual machines)

### timezone
* Set timezone Europe/Berlin (hard coded)

### etc_hosts
* Copy local /mylab/config/etc_hosts to /etc/hosts

### git
* Install Git packages
