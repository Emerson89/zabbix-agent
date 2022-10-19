## Instalação e update zabbix-agent 1 e 2 usando ansible

![Badge](https://img.shields.io/badge/ansible-zabbix-red)

## Dependências
![Badge](https://img.shields.io/badge/ansible-2.9.10-blue)

## Esta receita aceita as seguintes distribuições
- Amazon1/2
- CentOS6
- CentOS7
- CentOs8
- Rocky8
- Debian10
- Ubuntu18
- Ubuntu20

## Habilitado para nova versão 6.0

## Variáveis

| Nome | Descrição | Default | 
|------|-----------|---------|
| zabbix_version | Versão zabbix-server | 4.4|
| zabbix_hostmetadata | hostmetadata para auto-registro | os-linux |
| zabbix_agent2_update | Será feita update de versão do agent2 | False |
| zabbix_agent2_install | Irá instalar zabbix-agent2 somente versão 5.0 acima | False | 
| zabbix_agent_update | Será feita update de versão do agentd | False |
| zabbix_agent_install | Irá instalar zabbix-agentd | False | 
| zabbix_server_ip | IP zabbix-server | 127.0.0.1| 
| porta_agent2 | porta utilizada agent2 | 10052 |
| porta_agent | porta utilizada agent | 10050 |

## Importante
 Deve se escolher uma ou as duas variaveis **zabbix_agent_install** e **zabbix_agent2_install** passando para **True** para que o processo de instalação seja realizado, inserindo as duas será instalado os dois tipos em portas diferentes, caso queira somente atualizar a versão do agent utilize as variáveis **zabbix_agent_update** ou **zabbix_agent2_update**:
  
  - 10050: **zabbix-agent** 
  - 10052: **zabbix-agent2**  
 
## Edite o arquivo de inventário

## Playbook example
```yaml
---
- name: Install Zabbix-agent
  hosts: all
  vars:
    zabbix_server_ip: 'IP-SERVER'
    zabbix_version: 4.4
    zabbix_agent_install ou zabbix_agent2_install: True
    ### Variáveis de atualização somente quando for atualizar 
    zabbix_agent_update ou zabbix_update2_install: True
  become: true
  roles:
  - zabbix-agent
```
## Ou passe na execução do playbook conforme abaixo:
``` 
ansible-playbook -i hosts playbook.yml --extra-vars "zabbix_agent_install=True zabbix_version=5.0 zabbix_server_ip=127.0.0.1"

ansible-playbook -i hosts playbook.yml --extra-vars "zabbix_agent_update=True zabbix_version=5.4 zabbix_server_ip=127.0.0.1"
``` 
## License
![Badge](https://img.shields.io/badge/license-GPLv3-green)
