# zabbix-templates

Use with UserParameter in Zabbix Agent 2

# cat /etc/zabbix/zabbix_agent2.d/userparameter_hugepage.conf

UserParameter=mem.huge.page[*],cat /proc/meminfo | grep /$1 | awk '{ print $$2 }'

UserParameter=memmb.huge.page[*],numastat -m | grep /$1 | awk '{ print int($$4) }'
