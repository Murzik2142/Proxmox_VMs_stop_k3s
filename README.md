Proxmox_VMs_stop_k3s
=========

The task stop VMs vmid in Proxmox

Requirements
------------

Proxmox 8.2.4+\
ansible 3.1.2+\
ansible-galaxy 2.16.11+\
Not tested on earlier versions

Role Variables
--------------
```
# defaults file for Proxmox_VMs_stop_k3s
proxmox_api_host: "127.0.0.1"
proxmox_api_user: "root@pam"
proxmox_api_password: "password"
proxmox_node: "pve" 
# server
vm_count_server: 1
vm_server_id: 100
# worker
vm_count_worker: 2
vm_worker_id: 200
```
Dependencies
------------

Dependencies are absent

Example Playbook
----------------

```
# ansible-playbook -i inventory.yml playbook-VMs-stop-k3s.yaml
- name: Stop VMs in Proxmox
  hosts: proxmox
  vars:
    proxmox_api_host: "proxmox1.home.local"
    proxmox_api_user: "root@pam"
    proxmox_api_password: "11111111"
    proxmox_node: "proxmox1"
    # server
    vm_count_server: 3
    vm_server_id: 201
    # worker
    vm_count_worker: 3
    vm_worker_id: 301
  roles:
    - Proxmox_VMs_stop_k3s
```

License
-------

BSD-3-Clause

Author Information
------------------

Murzabaev Marat (murzik2142@gmail.com)
