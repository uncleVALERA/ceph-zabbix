# ceph-zabbix

A zabbix probe to get performance counters of ceph (Luminous 12.2+)


Installation
============

Install jq:
      sudo apt install jq

Copy the scripts, zabbix_agentd.conf.d into /etc/zabbix/

Check arguments: Server, Hostname, ListenIP in zabbix_agentd.conf

Finally in zabbix setup the discovery rule and related items you need.# ceph-zabbix
