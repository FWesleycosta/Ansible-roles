System Commons Role
===================

This Ansible role performs basic hardening of a Linux system. It installs essential packages, adds a user to the sudo group, creates a `wheel` group for sudoers management, sets a custom MOTD, and ensures the system is up-to-date and free of unnecessary packages.

## Requirements

This role is compatible with Debian/Ubuntu-based systems. Ensure that Ansible is configured and the target hosts are accessible.

## Tasks Overview

- **Install Sudo Package**: Ensures that the `sudo` package is installed on the system, allowing for privilege escalation.
- **Add User to Sudoers**: Adds the current user to the sudo group to grant administrative privileges.
- **Install Required Packages**: Installs a list of essential packages, including Git, Curl, Vim, OpenSSH Server, Python3, Pip, and Auditd.
- **Update Package Cache**: Ensures the package cache is up-to-date, with a cache validity time of 3600 seconds.
- **Upgrade All Packages**: Upgrades all system packages to the latest available versions, including phased updates.
- **Auto Remove Unnecessary Packages**: Cleans up the system by removing unnecessary packages and clearing the package cache.
- **Create Sudoers Management Group**: Creates a `wheel` group to manage sudoers, providing additional flexibility in access control.
- **Add Custom MOTD**: Sets a custom Message of the Day (MOTD) to display a warning message for unauthorized access. The message informs users that connections are logged, monitored, and audited, emphasizing the importance of authorized access only.

## Example Playbook

Here is an example of how to use this role:

```yaml
- hosts: servers
  roles:
    - { role: commons, tags: commons }
```

License
-------
MIT License

Author Information
------------------
This role was created in 2024 by [Francisco Wesley](https://github.com/FWesleycosta).