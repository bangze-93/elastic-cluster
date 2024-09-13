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
http://192.168.60.34:5601
![Screenshot from 2024-09-13 14-28-31](https://github.com/user-attachments/assets/cfbfc299-c1e6-45b6-aab0-9901dad0e73a)
![Screenshot from 2024-09-13 14-31-16](https://github.com/user-attachments/assets/87a51e0e-2c70-4ba8-a1e0-57a0299d1259)
![Screenshot from 2024-09-13 14-31-48](https://github.com/user-attachments/assets/1310130f-79cb-47ff-a77c-33637a16d588)

