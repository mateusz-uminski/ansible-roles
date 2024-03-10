# docker

Ansible role that installs docker.

# Compatibility
The role was tested on the following platforms:
- Debian 12 (x86 & aarch64)
- AlmaLinux 9 (x86 & aarch64)
- Amazon Linux 2023 (x86 & aarch64)

# Usage

```yaml
- name: example
  hosts: all
  gather_facts: true
  tasks:
    - name: install docker
      ansible.builtin.import_role:
        name: docker
```
