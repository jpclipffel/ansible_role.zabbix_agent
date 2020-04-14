# IaC / Ansible / Roles / Zabbix agent

Deploys Zabbix agent on host and map hosts on the Zabbix server.

## Usage

Include the role in your playbook using the `include_role` module (do not specify the `file` attribute):

```yaml
include_role:
  name: zabbix-agent
```

### Installation methods

This role support the following installation methods:

|Method |Description|
|-------|-----------|
|Docker |Install Zabbix through the official Docker image<br>Docker is installed using the role `docker_base`|

### Suppported hosts

This role **have only bee tested on Linux**

---

## Tags

|Tag|Description|
|----|-----------|
|`setup`|Install, configure and start the Zabbix agent|
|`teardown`|Disable and stop the Zabbix agent|
|`remove`|Uninstall the Zabbix agent|

## Variables

Role's variable are prefixed with the role name `zabbix_agent_`. For full variables list, please check `defaults/main.yml`

|Variable|Type|Required|Default|Description|
|--------|----|--------|-------|-----------|
|`zabbix_agent_server_host`|`string`, IPv4, hostname|No|`zabbix_agent_server_host`|Zabbix server|
|`zabbix_agent_container`|`string`|No|`zabbix/zabbix-agent2`|Zabbix agent's Docker image name|
|`zabbix_agent_container_version`|`string`|No|`latest`|Zabbix agent's Docker image version|


## Templates

|Template|Description|
|--------|-----------|
|`zabbix-agent.service.j2`|`systemd` unit file|
