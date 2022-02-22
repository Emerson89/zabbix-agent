## Provision zabbix-agent 1 e 2 using ansible

![Badge](https://img.shields.io/badge/ansible-zabbix-red)

## Dependencies
![Badge](https://img.shields.io/badge/ansible-2.9.10-blue)

## This recipe accepts the following distros
- Amazon1/2
- CentOS6
- CentOS7
- CentOs8
- Debian7
- Debian9
- Debian10
- Ubuntu16
- Ubuntu18
- Ubuntu20

## Edit the inventory file

## Playbook example
```
---
- name: Install Zabbix-agent
  hosts: all
  vars:
    zabbix_server_ip: 'SERVER'
    zabbix_version: 4.4
  become: yes
  roles:
  - zabbix-agent
```
``` 
ansible-playbook -i hosts playbook.yml
``` 
## License
![Badge](https://img.shields.io/badge/license-GPLv3-green)
