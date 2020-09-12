## Provision zabbix-agent using ansible

![Badge](https://img.shields.io/badge/ansible-zabbix-red)

## Dependencies
![Badge](https://img.shields.io/badge/ansible-2.9.10-blue)
![Badge](https://img.shields.io/badge/CentOS-7-blue)

## Edit the inventory file

## Playbook example
```
---
- name: Install Zabbix-agent
  hosts: all
  become: yes
  roles:
  - zabbix-agent
```
``` 
ansible-playbook -i hosts playbook.yml
``` 
## License
![Badge](https://img.shields.io/badge/license-GPLv3-green)
