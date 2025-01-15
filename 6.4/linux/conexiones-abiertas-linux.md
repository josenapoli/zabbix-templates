Requerimientos:

Instalar agente de zabbix en el servidor linux.

Damos permisos al usuario zabbix para ejecutar un comando:

> nano /etc/sudoers.d/zabbix-agent

zabbix ALL = NOPASSWD: /usr/local/bin/count_close_wait.sh

> chmod 440 /etc/sudoers.d/zabbix-agent

Script que va a ejecutar el usuario zabbix:

> nano /usr/local/bin/count_close_wait.sh

#!/bin/bash

netstat -putona | grep CLOSE_WAIT | wc -l

> chmod +x /usr/local/bin/count_close_wait.sh
