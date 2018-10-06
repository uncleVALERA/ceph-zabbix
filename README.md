# ceph-zabbix

A zabbix probe to get performance counters of ceph (Luminous 12.2+)


Installation
============

Install jq:
      sudo apt install jq zabbix-sender

Copy the scripts, zabbix_agentd.conf.d into /etc/zabbix/

Check arguments: Server, Hostname, ListenIP in zabbix_agentd.conf

#Check permission for read user zabbix /etc/ceph/<{$CLUSTER_NAME}>.client.admin.keyring

Configuration
=============

Create user zabbix for CEPH:
ceph auth add client.zabbix  mon 'allow r'  mgr 'allow r'  osd 'allow r'

Export key to custom path because default path /etc/pve/priv/ in Proxmox is not accessible:
ceph auth get client.zabbix -o /etc/ceph/ceph.client.zabbix.keyring

Check permission:
su - zabbix -s /bin/bash
ceph --user zabbix --keyring=/etc/ceph/ceph.client.zabbix.keyring  -s

Finally in zabbix setup the discovery rule and related items you need.# ceph-zabbix

