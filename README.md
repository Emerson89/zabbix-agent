## Provision zabbix-agent using ansible

![Badge](https://img.shields.io/badge/ansible-zabbix-red)

## Dependencies
![Badge](https://img.shields.io/badge/ansible-2.9.10-blue)
![Badge](https://img.shields.io/badge/CentOS-7-blue)

## This recipe accepts the following distros
- Amazon
- CentOS6
- CentOS7
- Debian7
- Debian9
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
  become: yes
  roles:
  - zabbix-agent
```
``` 
ansible-playbook -i hosts playbook.yml
``` 
## License
![Badge](https://img.shields.io/badge/license-GPLv3-green)
