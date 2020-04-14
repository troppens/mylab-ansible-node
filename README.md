# mylab-node-ansible
Ansible roles to configure an already provisioned node (server)


## Installing

```
# cd /etc/ansible/roles
# git clone https://github.com/troppens/mylab-node-ansible.git mylab_node
```


## Usage

Configure default entities:
```
- hosts: nodes
  roles:
    - mylab_node
```

Configure all entities:
```
- hosts: nodes
  vars:
    - mylab_node_entities: "{{ mylab_node_entities_all }}"
  roles:
    - mylab_node
```

Configure ssh, chronyd and timezone only:
```
- hosts: nodes
  vars:
    - mylab_node_entities:
      - ssh
      - chronyd
      - timezone
  roles:
    - mylab_node
```

Customize Git settings:
```
- hosts: nodes
  vars:
    - mylab_node_entities: "{{ mylab_node_entities_all }}"
    - mylab_node_git_user_name: "Erika Mustermann"
    - mylab_node_git_user_email: "erika@example.com"
  roles:
    - mylab_node
```


## Variables

### mylab_node_entities
* Specify which entities to configure. See [defaults](defaults/main.yml) for defaults entities.

### mylab_node_entities_all
* List of all entities which can be configured. See [defaults](defaults/main.yml) for all entities. 

### mylab_node_git_user_name
* Git user name. See [defaults](defaults/main.yml) for default.

### mylab_node_git_user_email
* Git user email. See [defaults](defaults/main.yml) for default.

### mylab_node_git_credential_cache_timeout
* Git credential cache timeout. See [defaults](defaults/main.yml) for default.


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
* Set global user name
* Set global user email
* Set git to use the credential memory cache
