# ansible-roles

[![Docker](https://img.shields.io/badge/Docker-27.1.1-blue.svg)](https://www.docker.com/)
[![Ansible](https://img.shields.io/badge/Ansible-2.15.10-blue.svg)](https://www.ansible.com/)
[![Python](https://img.shields.io/badge/Python-3.9.6-blue.svg)](https://www.python.org/)
[![GitHub](https://img.shields.io/badge/GitHub-ansible--modules-blue.svg)]()
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)


## Description

This is repository contains custom Ansible roles that can be used to automate tasks in a Linux environment. The roles are written in language Yaml and can be used to perform various tasks, such as installing packages, managing users, and configuring services.

## Roles Overview

The following roles are available in this repository:

- **[Chrony](roles/chrony)**: Installs and configures the Chrony NTP service on a host machine.
- **[Commons](roles/commons)**: Performs basic hardening of a Linux system, including installing essential packages, adding a user to the sudo group, and setting a custom MOTD.
- **[Docker](roles/docker)**: Installs Docker on a host machine and configures Docker Compose and related settings.


## Requirements

To use these roles, you need to have Ansible installed on your system. You can install Ansible using the following command:

```bash
pip install ansible
```

You also need to have a basic understanding of Ansible and how to create playbooks to run the roles on your target hosts.


## How to Use

To use these roles, you need to have Ansible installed on your system. You can then create a playbook that includes the roles you want to run on your target hosts. For example, to run the `commons` role on a group of servers, you can create a playbook like this:

```yaml
- hosts: servers
  roles:
    - { role: commons, tags: commons }
```

You can then run the playbook using the `ansible-playbook` command:

```bash
ansible-playbook -i inventory playbook.yml
```

Replace `inventory` with the path to your inventory file and `playbook.yml` with the path to your playbook file.

### Example Create a inventory file

```bash
echo "[servers]" > inventory
echo "server1 ansible_host=xx.xx.xx.xx" >> inventory
echo "server2 ansible_host=xx.xx.xx.xx" >> inventory
```

### Example Create a playbook file

```bash
echo "- hosts: servers" > playbook.yml
echo "  roles:" >> playbook.yml
echo "    - { role: commons, tags: commons }" >> playbook.yml
```

