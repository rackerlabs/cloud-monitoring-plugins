An ansible playbook to install Cloud Monitoring plugins on the localhost.   This guide will not go into how to install ansible or git for your system.

Default command:

```ansible-playbook -i hosts <playbook>```

## Available playbooks 
- holland_mysqldump.yml
- lsyncd_status.yml
- mysql_slave.yml
- port_check.yml

## Examples
| Name | Examples
| ---------- | -------- |
| holland_mysqldump | `holland_mysqldump.yml`
| lsyncd_status | `lsyncd_status.yml` 
| mysql_slave | `mysql_slave.yml`
| port_check | `port_check.yml -e port=8080` <br> `port_check.yml -e '{"host":"rackspace.com","port":"80"}'`

### Notification plan
*Note* the default notification plan is: npManaged. This is for "Managed Operations" customers. Notification plan change example:

`ansible-playbook -i hosts <playbook> -e '{"notification_plan":"npTechnicalContactsEmail"}'`


## Modifiers
You can edit the `group_vars/all` file if you want to change any of the defaults. Or you can change them via cli.
- Notification Plan will default to npManaged, but you can change it to npTechnicalContactsEmail or any notification plan that is created for the account.
Example: ```ansible-playbook -i hosts <playbook> -e '{"notification_plan":"npTechnicalContactsEmail"}'  

## References:
- [Rackspace Cloud Monitorin API - Agent Configuration File](https://developer.rackspace.com/docs/rackspace-monitoring/v1/tech-ref-info/server-side-agent-config-yaml/)
- [Github for Cloud Monitoring Agent Plugins](https://github.com/racker/rackspace-monitoring-agent-plugins-contrib)
