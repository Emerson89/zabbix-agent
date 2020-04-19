##TESTE
# zabbix-agent via ansible

The installation was performed on localhost change your inventory file for installation on more hosts, there is a template file from zabbix_config enter the IP of zabbix_server.For installation on localhost follow below
Move the directories / playbooks and / roles to the / etc / ansible directory, the installation was done on localhost and edit the hosts inventory file.

#mv zabbix-agent/roles/ zabbix-agent/playbooks/ /etc/ansible

#vim hosts

[host]

127.0.0.1

# To test host communication
#ansible localhost -c local -m ping

# Run the file # playbook.yml found in the directory / playbooks
#ansible-playbook -c local playbooks / playbook.yml
