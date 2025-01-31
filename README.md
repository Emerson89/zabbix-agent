## Instalation and update zabbix-agent 1/2 using ansible

![Badge](https://img.shields.io/badge/ansible-zabbix-red)

## Dependencies

- ansible-2.16.6

- python3.10

## Install dependencies

```bash
pip install -r requirements.txt 
```

## Support Operation Systems
- Amazon1/2
- CentOS6
- CentOS7
- CentOs8
- Rocky8
- Almalinux8
- Debian10
- Debian11 - less 4.4 below
- Ubuntu18
- Ubuntu20
- Ubuntu22

## Support version 7.0 Zabbix

## Variables

| Name | Description | Default | 
|------|-----------|---------|
| zabbix_version | Version zabbix-server | 4.4|
| zabbix_hostname | Hostname zabbix-agent | "{{ ansible_hostname }}" |
| zabbix_hostmetadata | hostmetadata for auto-registry | os-linux |
| zabbix_agent2_update | Update version agent2 | false |
| zabbix_agent2_install | Instalation zabbix-agent2 only **version 5.0** above | false | 
| zabbix_agent_update | Update version zabbix-agent 1 | false |
| zabbix_agent_install | Instalation zabbix-agent 1 | false | 
| zabbix_server_ip | IP server zabbix-server | 127.0.0.1| 
| porta_agent2 | Utilized port agent2 | 10052 |
| porta_agent | Utilized port agent | 10050 |

## Important
You must choose one or both of the variables **zabbix_agent_install** and **zabbix_agent2_install** by going to **true** for the installation process to be performed, entering the two will install the two types on different ports, if you only want to update the agent version use the variables **zabbix_agent_update** or **zabbix_agent2_update**:
  
  - 10050: **zabbix-agent** 
  - 10052: **zabbix-agent2**  
 
## Example inventory

```bash
[zabbix-agent]
172.16.33.10 ansible_ssh_private_key_file=./PATH/private_key ansible_user=vagrant
```

## Playbook example

```yaml
---
- name: Install Zabbix-agent
  hosts: all
  vars:
    zabbix_server_ip: 'IP-SERVER'
    zabbix_version: 4.4
    zabbix_agent_install or zabbix_agent2_install: true
    ### Variables of updates 
    zabbix_agent_update or zabbix_update2_install: true
  become: yes
  roles:
  - zabbix-agent
```
## Or pass the playbook execution as below:

```bash 
ansible-playbook -i hosts playbook.yml --extra-vars "zabbix_agent_install=true zabbix_version=5.0 zabbix_server_ip=127.0.0.1"

ansible-playbook -i hosts playbook.yml --extra-vars "zabbix_agent_update=true zabbix_version=5.4 zabbix_server_ip=127.0.0.1"
``` 

- setup

```bash
ansible -i hosts all -m setup |grep ansible_distribution
```

## License
![Badge](https://img.shields.io/badge/license-GPLv3-green)
