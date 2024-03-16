# consul

Ansible role that installs consul in either server or client mode.


# Compatibility
The role was tested on the following platforms:
- Debian 12 (x86 & aarch64)
- AlmaLinux 9 (x86 & aarch64)
- Amazon Linux 2023 (x86 & aarch64)


# Prerequisites
1. Generate a consul key:
```sh
docker run -it --rm hashicorp/consul consul keygen
```
2. Use the command output to set variable `consul_key`.


# Usage

## server mode
```yaml
- name: server mode
  hosts: controlplane
  gather_facts: true
  vars:
    consul_key: qDOPBEr+/oUVeOFQOnVypxwDaHzLrD+lvjo5vCEBbZ0=
    consul_server_mode: true
    consul_servers: []
    consul_dc_name: "dc1"
    consul_domain: "consul"
    consul_log_level: "INFO"
    consul_enable_acl: false
    consul_raft_multiplier: 1
  tasks:
    - name: install haproxy
      ansible.builtin.import_role:
        name: haproxy
```

## client mode
```yaml
- name: client mode
  hosts: clients
  gather_facts: true
  vars:
    consul_key: qDOPBEr+/oUVeOFQOnVypxwDaHzLrD+lvjo5vCEBbZ0=
    consul_server_mode: false
    consul_servers: ["server:8301"]
    consul_dc_name: "dc1"
    consul_domain: "consul"
    consul_log_level: "INFO"
  tasks:
    - name: install haproxy
      ansible.builtin.import_role:
        name: haproxy
```
