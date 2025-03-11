# Deploy Zabbix server MySQL using docker, docker-compose

## Requirement:
| Requirement | status | Ref | 
| :--- | :--- | :--- |
| Docker | Installed | https://docs.docker.com/engine/install/ | 
| Docker-compose | Installed | https://docs.docker.com/compose/install/standalone/ |

## Replace environment variable definitions to match the deployment environment (File: docker-compose.yml)
| Key | Value | Describe | Example |
| :--- | :--- | :--- | :--- |
| MYSQL_ROOT_PASSWORD | PASSWORD_ROOT_MYSQL | Password Root Mysql | MYSQL_ROOT_PASSWORD: "mypassword" |
| TZ | TIMEZONE | Local timezone | TZ: "Asia/Ho_Chi_Minh" |
| PHP_TZ | TIMEZONE | PHP Local timezone <=> Local timezone | PHP_TZ: "Asia/Ho_Chi_Minh" |
| ZBX_SERVER | Declare zabbix server for zabbix-agent (include bridge gateway IP address) | ZBX_SERVER: "zabbix-server,192.168.10.1" |
| subnet | ZABBIX_NETWORK_IPAM_BLOCK | Network block allocate IP using for Zabbix and Dependency | subnet: "192.168.10.0/24" |
| gateway | ZABBIX_NETWORK_IPAM_GATEWAY | Bridge gateway IP address | gateway: "192.168.10.1" |


## Start zabbix-server
```
# docker-compose up -d
```
