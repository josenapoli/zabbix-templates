Requerimientos:

> nano /etc/sudoers.d/zabbix-agent

zabbix ALL = NOPASSWD: /usr/local/bin/count_close_wait.sh

> chmod 440 /etc/sudoers.d/zabbix-agent

> nano /usr/local/bin/count_close_wait.sh

#!/bin/bash

netstat -putona | grep CLOSE_WAIT | wc -l

> chmod +x /usr/local/bin/count_close_wait.sh
