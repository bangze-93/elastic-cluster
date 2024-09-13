# Install Elastic 7.17 Cluster (Docker) using Ansible on Ubuntu 20 
### Adjust with your env
- ##### <i> ``` vars/all.yaml ``` </i> 
```
---
elastic_cluster_name: ES-Cluster
elastic_version: 7.17.24
elastic_pass: s0U+#]>0CX6)36+n
elastic_vol_dir: /opt/elastic
jvm_size: 1g
kibana_version: "{{ elastic_version }}"
kibana_vol_dir: /opt/kibana
time_zone: Asia/Jakarta
...
```
- ##### <i> ``` inventory/hosts ``` </i>
```
[elastic]
elastic01 ansible_host=192.168.60.31
elastic02 ansible_host=192.168.60.32
elastic03 ansible_host=192.168.60.33

[kibana]
kibana01 ansible_host=192.168.60.34

[all:vars]
ansible_user=user
ansible_ssh_pass=P4s5word
ansible_become_password=P4s5word
```
### Run playbook
```
ansible-playbook playbook.yaml
```
### Access Kibana